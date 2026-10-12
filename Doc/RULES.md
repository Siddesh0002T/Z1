# Engineering Rules, Standards & Guidelines
## Creative Developer 3D Editorial Portfolio

---

## 1. Core Principles

1. **Aesthetic Excellence is Mandatory**: The portfolio must always look and feel like an award-winning (Awwwards Site of the Year / FWA of the Day) project. Sub-par, standard, or generic UI patterns are unacceptable.
2. **60 FPS Performance Standard**: Animations, canvas renders, and physics simulations must maintain 60 frames per second on standard hardware. Never sacrifice performance for unoptimized effects.
3. **Clean Teardown & Zero Memory Leaks**: WebGL textures, geometries, GSAP timelines, Lenis scrollers, and event listeners must be cleaned up on component unmount.

---

## 2. Next.js 16 & React 19 Rules

### 2.1 App Router & Client Components
- **Client Directives**: Any component utilizing hooks (`useState`, `useEffect`, `useRef`), browser APIs (`window`, `document`, `navigator`), GSAP, or WebGL canvases must declare `'use client';` at line 1.
- **Dynamic Imports for 3D & WebGL**: Always import Three.js, R3F canvases, physics engines, and custom cursor components dynamically with `{ ssr: false }`:
  ```tsx
  const CustomCursor = dynamic(() => import('@/components/ui/CustomCursor'), { ssr: false });
  const ExperienceCard = dynamic(() => import('@/components/3d/ExperienceCard'), { ssr: false });
  ```
- **React 19 Concurrency**: Avoid synchronous setState updates inside scroll scrub loops. Instead, drive visual modifications through direct DOM style updates (`gsap.set` or ref element styling) to prevent unnecessary React re-render cycles.

---

## 3. WebGL, Three.js & Rapier Physics Rules

### 3.1 Allocation and Render Loops
- **NEVER Instantiate in `useFrame`**: Never create `new THREE.Vector3()`, `new THREE.Matrix4()`, or new geometries/materials inside a `useFrame` callback or `requestAnimationFrame` loop.
  ```typescript
  // CORRECT: Instantiate reusable vectors at module scope or component ref
  const vec = useRef(new THREE.Vector3());
  
  useFrame(() => {
    // Mutate existing vector
    vec.current.set(x, y, z);
  });
  ```
- **Texture & Canvas Disposal**: When regenerating HTML5 canvas textures for the 3D card UV maps, ensure the previous texture is explicitly disposed:
  ```typescript
  useEffect(() => {
    return () => {
      cardTexture?.dispose();
    };
  }, [cardTexture]);
  ```

### 3.2 Rapier Physics Configurations
- **Damping Constraints**: All dynamic lanyard segments must specify both linear and angular damping (`angularDamping: 4, linearDamping: 4`) to prevent erratic jitter or infinite centrifugal oscillation.
- **Sleep Optimization**: Colliders and joints should enable sleeping (`canSleep: true`) when the badge reaches a resting equilibrium state.
- **Joint Hierarchy**: Always bind joints in top-down hierarchical order (Fixed anchor -> Node 1 -> Node 2 -> Card).

---

## 4. GSAP & ScrollTrigger Lifecycle Rules

### 4.1 Strict Lifecycle Cleanup
- Every `gsap.timeline()` or `ScrollTrigger.create()` must have an associated cleanup callback inside `useEffect`:
  ```typescript
  useEffect(() => {
    const st = ScrollTrigger.create({
      trigger: sectionRef.current,
      // ...
    });
    
    return () => {
      st.kill();
    };
  }, []);
  ```

### 4.2 Pinning & Layout Reflows
- **Use `anticipatePin: 1`**: When pinning full-screen sticky frames (`position: sticky` or GSAP `pin: true`), always set `anticipatePin: 1` to prevent jitter or white flashes on high refresh-rate monitors.
- **Avoid Layout Reads in Scrubs**: Never call `getBoundingClientRect()`, `offsetWidth`, or `offsetHeight` inside an `onUpdate` scrub callback. Pre-calculate dimensions during initialization or on resize events.
- **Resize Refresh**: Always bind `ScrollTrigger.refresh()` to window resize events when dealing with responsive layouts.

---

## 5. Styling & Design System Rules (Tailwind CSS v4)

### 5.1 CSS Custom Properties First
All global colors, fonts, and grid sizes must reference the CSS custom properties defined in `globals.css`:
- `--bg`: `#050505` (Deep luxury black)
- `--bg-2`: `#0a0a0a` (Elevated surface black)
- `--fg`: `#ffffff` (Primary white typography)
- `--fg-dim`: `rgba(255, 255, 255, 0.55)` (Secondary copy)
- `--fg-mute`: `rgba(255, 255, 255, 0.25)` (Tertiary labels)
- `--border`: `rgba(255, 255, 255, 0.06)` (Subtle glass border)
- `--border-hover`: `rgba(255, 255, 255, 0.18)` (Interactive border)

### 5.2 Strict Font Pairing Rules
1. **Display Typography**: Use `Bebas Neue` (fallback: `'Impact', sans-serif`) for monumental headlines, developer names, and section watermarks.
2. **Body Typography**: Use `Inter` (fallback: `'Space Grotesk', sans-serif`) for narrative paragraphs, descriptions, and feature lists.
3. **Monospace Typography**: Use `JetBrains Mono` (fallback: `monospace`) for code snippets, telemetry chips, timestamps, and terminal commands.

---

## 6. TypeScript & Code Quality Standards

1. **No Implicit or Untyped `any`**: All data structures (Projects, Skills, Education, Experience, Cursor States) must be strongly typed using interfaces declared in `src/types/index.ts`.
2. **Component File Naming**: PascalCase for React components (`ExperienceCard.tsx`, `HeroBackground.tsx`), camelCase for hooks and utilities (`useScramble.ts`, `ascii-utils.ts`).
3. **Single Responsibility**: Keep 3D scene code isolated in `src/components/3d/`, layout sections in `src/components/sections/`, and atomic reusable UI in `src/components/ui/`.

---

## 7. AI Agent Modification Guidelines

When an AI assistant or coding agent works on this codebase:
- **Do NOT delete 3D or physics interactions**: Always preserve the Rapier lanyard and Canvas scenes.
- **Do NOT introduce white or generic light-mode backgrounds**: The project is intentionally designed with an editorial cyberpunk dark aesthetic.
- **Always verify Next.js 16 compatibility**: Do not use deprecated React APIs or Next.js legacy page patterns.
- **Test responsive adaptations**: Ensure that when a 3D component is viewed on screens `< 768px`, touch event handlers and fallbacks engage gracefully.
