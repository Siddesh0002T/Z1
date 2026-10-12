# Technical Memory, Decision Records & Resolved Gotchas
## Creative Developer 3D Editorial Portfolio

---

## 1. Project Context & Environment

- **Primary Repository**: `e:/port/GSAP-Portfolio`
- **Active Dev Server**: `npm run dev` (Runs locally on `http://localhost:3000`)
- **Node & Package Tooling**: Next.js 16.2.10, React 19.2.4, TypeScript 5.x, Tailwind CSS v4.

---

## 2. Architecture Decision Records (ADRs)

### ADR-001: Next.js 16 & React 19 Client Hydration Strategy
- **Context**: The portfolio relies on browser-only primitives: WebGL contexts, Rapier WASM physics, Canvas 2D image processing, and window scroll listeners. Standard SSR causes hydration mismatch warnings or fatal errors (`window is not defined`).
- **Decision**: Use a client-first mounting pattern in `src/app/page.tsx`:
  - Provide a solid black fallback screen (`#050505`) until `mounted === true`.
  - Dynamically load Canvas components (`CustomCursor`, `HeroBackground`, 3D scenes) with `next/dynamic` and `{ ssr: false }`.
- **Outcome**: Zero SSR errors during development and production builds; instant black-screen initial paint followed by a smooth preloader reveal.

### ADR-002: GSAP ScrollTrigger Synchronized with Lenis Inertia
- **Context**: Native browser smooth scrolling conflicts with GSAP ScrollTrigger, resulting in jittery scrub animations and desynchronized pin triggers.
- **Decision**: Integrate **Lenis 1.3** and bind its update loop directly into `gsap.ticker`:
  ```typescript
  lenis.on('scroll', ScrollTrigger.update);
  gsap.ticker.add((time) => lenis.raf(time * 1000));
  gsap.ticker.lagSmoothing(0);
  ```
- **Outcome**: Buttery, momentum-damped scroll scrub across macOS, Windows, Linux, and mobile browsers without scroll jumping.

### ADR-003: WASM Rapier Physics for Interactive Credentials
- **Context**: Standard CSS or simple 2D spring animations fail to convey physical weight and realism for the developer's credentials.
- **Decision**: Implement `@react-three/rapier` inside an isolated Canvas:
  - Model a physical conference lanyard badge with 4 chained joint nodes (`useSphericalJoint`, `useRopeJoint`).
  - Constrain physics with linear/angular damping to prevent jitter.
- **Outcome**: Tactile, memorable interaction where visitors can physically tug, toss, and watch the credential card sway and settle naturally.

### ADR-004: In-Memory HTML5 Canvas to 3D Model UV Atlas
- **Context**: Loading custom 3D models or separate texture images for each job experience and education degree is bandwidth-heavy and hard to maintain.
- **Decision**: Render candidate details (role, company, date, bullets) onto a 2D HTML5 `<canvas>` at runtime and assign it as a `THREE.CanvasTexture` on the GLTF model's front UV region.
- **Outcome**: High-resolution typography rendered on the 3D card without loading extra image assets over the network.

### ADR-005: CSS 3D Perspective Z-Axis vs Pure WebGL for Projects
- **Context**: Implementing full project cards with live links, select text, and buttons entirely inside WebGL shaders is notoriously complex for accessibility and interaction.
- **Decision**: Build the projects flythrough section using native DOM elements placed inside a container with `perspective: 1200px` and `transform-style: preserve-3d`. Drive card Z positions via GSAP ScrollTrigger.
- **Outcome**: Full access to native HTML links, buttons, typography, and Framer Motion spring hovers while achieving a 3D camera flythrough effect.

---

## 3. Technical Gotchas & Solutions

### Gotcha 1: GSAP ScrollTrigger Pin Flashing on Windows / High Refresh Rates
- **Problem**: When scrubbing pinned sections on monitors running 120Hz/144Hz, pinned elements occasionally flickered or displayed tiny 1px micro-gaps.
- **Solution**: Set `anticipatePin: 1` on all major ScrollTrigger instances (`Hero.tsx`, `Projects.tsx`, `Experience.tsx`), and set `transformOrigin: 'bottom center'` with `will-change: transform`.

### Gotcha 2: MeshLine Dynamic Spline Re-allocation
- **Problem**: Calling `new MeshLineGeometry()` inside the `useFrame` render loop caused severe garbage collection spikes and dropped frame rates down to 25 FPS.
- **Solution**: Maintain a persistent `MeshLineGeometry` reference and update it in-place using `geometry.setPoints(curvePoints)` on each frame.

### Gotcha 3: Rapier Physics Joint Instability on Window Resize
- **Problem**: Resizing the browser window changed camera aspect ratios and caused Rapier joint anchors to snap violently.
- **Solution**: Normalize anchor coordinates using fixed world units and apply linear dampening (`damping: 4.0`) to absorb sudden displacement forces during window resize events.

### Gotcha 4: Next.js 16 Tailwind CSS v4 Migration
- **Problem**: Tailwind CSS v4 replaces the legacy `tailwind.config.js` with direct CSS `@import "tailwindcss";` and `@theme` blocks. Older plugins like `tailwind-scrollbar` are incompatible.
- **Solution**: Use native CSS variables (`--bg`, `--fg`, `--border`) directly in `:root` and custom WebKit scrollbar rules in `globals.css`.
