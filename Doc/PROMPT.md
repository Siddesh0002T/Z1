# Master AI Generation Prompts
## Creative, Responsive & Smooth 3D Developer Portfolio

This document contains production-ready, master-grade prompts designed to be copied and pasted directly into AI coding assistants (Antigravity, Cursor, Claude 3.7 Sonnet, Gemini 2.5 Pro, GPT-4o) to generate a complete, high-performance, Awwwards-tier creative developer portfolio from scratch.

---

## 📋 Table of Contents
1. [Master Prompt (All-In-One Execution)](#1-master-prompt-all-in-one-execution)
2. [Phase-by-Phase Modular Prompts](#2-phase-by-phase-modular-prompts)
   - [Phase 1: Project Setup, Dependencies & Design Tokens](#phase-1-project-setup-dependencies--design-tokens)
   - [Phase 2: Lenis Smooth Scrolling & Dynamic Glow Cursor](#phase-2-lenis-smooth-scrolling--dynamic-glow-cursor)
   - [Phase 3: Cinematic Preloader with Curtain Reveal](#phase-3-cinematic-preloader-with-curtain-reveal)
   - [Phase 4: Sticky 280vh Parallax Hero with Gliding Portrait](#phase-4-sticky-280vh-parallax-hero-with-gliding-portrait)
   - [Phase 5: Dual Infinite Opposing Marquee](#phase-5-dual-infinite-opposing-marquee)
   - [Phase 6: 3D Rapier Physics Interactive ID Lanyard Badge](#phase-6-3d-rapier-physics-interactive-id-lanyard-badge)
   - [Phase 7: CSS 3D Perspective Z-Axis Projects Flythrough](#phase-7-css-3d-perspective-z-axis-projects-flythrough)
   - [Phase 8: Interactive Skills Telemetry & Radar Dashboard](#phase-8-interactive-skills-telemetry--radar-dashboard)
   - [Phase 9: Interactive Three.js Starfield & Magnetic Contact](#phase-9-interactive-threejs-starfield--magnetic-contact)
   - [Phase 10: Mobile Touch Fallbacks, 60 FPS Polish & SEO](#phase-10-mobile-touch-fallbacks-60-fps-polish--seo)
3. [Configuration & Personalization Template](#3-configuration--personalization-template)

---

## 1. Master Prompt (All-In-One Execution)

```markdown
You are an elite Creative Technologist and Lead WebGL / Front-end Engineer. Your task is to build a world-class, Awwwards / FWA-tier personal portfolio website built with modern web technologies that looks mesmerizing, runs at a solid 60+ FPS, and feels tactile and responsive.

### 🛠️ Core Technology Stack
- Framework: Next.js 16 (App Router) with React 19 and TypeScript 5
- Styling: Tailwind CSS v4 (@tailwindcss/postcss) with pure CSS custom properties
- 3D & Physics Engine: Three.js r185, @react-three/fiber v9, @react-three/drei v10, @react-three/rapier v2, and meshline v3
- Motion & Animation: GSAP v3.15 (@gsap/react, ScrollTrigger), Framer Motion v12
- Smooth Scrolling: Lenis v1.3 synchronized directly to the GSAP internal ticker
- Iconography: Lucide React + custom inline SVGs

### 🎨 Visual Identity & Aesthetic Philosophy
- Style: High-Fashion Luxury Editorial Magazine meets Cyberpunk Terminal Diagnostics.
- Palette: 
  - Base: Deep Obsidian Black (`#050505`), Elevated Surface (`#0a0a0a`)
  - Typography: Pure White (`#ffffff`), Dimmed copy (`rgba(255,255,255,0.55)`), Muted (`rgba(255,255,255,0.25)`)
  - Neon Accents: Electric Cyan (`#00d4ff`), Matrix Green (`#00ff41`), Ultraviolet (`#bf5af2`)
  - Borders: Ultra-thin frosted glass (`rgba(255,255,255,0.06)` to `0.18`)
- Typography Hierarchy:
  - Display Headings: Bebas Neue (monumental, condensed, architectural uppercase)
  - Body & UI: Inter / Space Grotesk (high legibility, 1.85 line-height)
  - Telemetry & Code: JetBrains Mono (monospaced cybernetic telemetry)
- Multi-Layered Atmosphere:
  1. CSS Blueprint Grid (80px square cadence)
  2. Rotating SVG Radar concentric targeting rings
  3. HTML5 Canvas floating dust particle field
  4. Subtle procedural SVG fractal noise overlay (opacity 0.032)
  5. Radial gradient halo lighting behind center stage

### 📐 Section-by-Section Architecture

1. Client Hydration & SSR Safety (`src/app/page.tsx`):
   - Render a pure black screen until mounted.
   - Dynamically import all 3D canvas and cursor components with `{ ssr: false }`.
   - Initialize Lenis smooth scroll and synchronize with GSAP ScrollTrigger via `gsap.ticker`.

2. Cinematic Preloader (`LoadingScreen.tsx`):
   - Luxury boot screen with monogram logo fade & scale.
   - Smooth numeric counter interpolating from 0% to 100% with a hairline progress bar.
   - Curtain reveal: upon 100%, the overlay slides vertically up (`yPercent: -100`) using `power3.inOut`.

3. Custom Editorial Cursor (`CustomCursor.tsx`):
   - Dual-ring follower: pinpoint center dot + lerped outer aura ring.
   - Velocity-based particle trail emitting soft glow dots.
   - Contextual expansion on hover over links, buttons, and 3D canvases. Auto-disabled on mobile.

4. 280vh Sticky Parallax Hero (`Hero.tsx` & `HeroBackground.tsx`):
   - Pinned 100vh viewport inside a 280vh scroller.
   - Monumental name ('SIDDHESH') with split-letter spans that elevate and blur out on scroll scrub.
   - Cutout developer portrait centered at the bottom that glides to the left half (`-25vw`) as the user scrolls.
   - Right half reveals a sequenced 3-stage narrative:
     * Stage 1: Creative developer intro & skill chips.
     * Stage 2: Cyberpunk terminal block (`developer_profile.sh`) with system specs and stats (4+ Years, 30+ Projects).
     * Stage 3: Technical capabilities (Web Dev, Mobile Dev, Backend/DB).

5. Dual Infinite Marquee Dividers (`MarqueeDivider.tsx`):
   - Two opposing horizontal tickers with branded SVG badges (React, Next.js, Three.js, GSAP, TypeScript, Kotlin, Node.js).
   - Seamless loop without jump or layout shift.

6. 3D Rapier Physics Credentials (`ExperienceCard.tsx` & `EducationCard.tsx`):
   - 3D WebGL scene using `@react-three/fiber` and `@react-three/rapier`.
   - Physics-simulated lanyard badge: 4-segment joint chain (`useSphericalJoint`, `useRopeJoint`) and a dynamic card rigid body.
   - Dynamic In-Memory Canvas Texture: Generates an HTML5 canvas rendering candidate data (Role, Company, Dates, Skills) directly onto the GLTF model's front UV region at runtime.
   - Interactive mouse drag with realistic tension, elasticity, and return-to-rest physics.

7. CSS 3D Perspective Z-Axis Projects Flythrough (`Projects.tsx`):
   - Viewport with CSS `perspective: 1200px` and `transform-style: preserve-3d`.
   - Project cards spaced sequentially along the Z-axis (`initialZ = -i * 1600 - 800px`).
   - Cards travel forward toward the camera on scroll scrub, fading and blurring as they pass the camera plane (`Z > 200px`).
   - Spring 3D mouse tilt on card hover, direct GitHub repository and preview action buttons.

8. Interactive Matrix Skills Dashboard (`Skills.tsx`):
   - Categorized telemetry (Frontend, Fullstack, WebGL, Motion, Backend).
   - Animated SVG circular progress meters with percentage telemetry.
   - Water-drop accent motion and ambient glow shifting to match the active skill's brand color.

9. Starfield Particle Contact Portal & Editorial Footer (`Contact.tsx` & `Footer.tsx`):
   - Interactive Three.js particle starfield cloud reacting to pointer coordinates.
   - Magnetic spring physics buttons for GitHub, LinkedIn, Twitter/X, and Stack Overflow.
   - Live local time indicator (Nashik, India), copyright mark, and smooth back-to-top trigger.

### ⚡ Strict Performance & Engineering Constraints
- Maintain 60 FPS on standard desktop displays.
- Never instantiate objects (`new THREE.Vector3()`) inside `useFrame` or render loops.
- Clean up all GSAP timelines and ScrollTrigger instances on unmount (`st.kill()`, `tl.kill()`).
- Responsive fallbacks: disable hover effects and heavy physics joint simulations gracefully on screens `< 768px`.
```

---

## 2. Phase-by-Phase Modular Prompts

For incremental development, step-by-step pairing, or building individual features, execute these prompts sequentially:

### Phase 1: Project Setup, Dependencies & Design Tokens

```markdown
Create the foundation for an Awwwards-tier 3D Creative Developer Portfolio using Next.js 16 (App Router), React 19, TypeScript, and Tailwind CSS v4.

1. Configure `package.json` with the following dependencies:
   - "next": "16.2.10", "react": "19.2.4", "react-dom": "19.2.4", "typescript": "^5"
   - "three": "^0.185.1", "@types/three": "^0.185.0"
   - "@react-three/fiber": "^9.6.1", "@react-three/drei": "^10.7.7"
   - "@react-three/rapier": "^2.2.0", "meshline": "^3.3.1"
   - "gsap": "^3.15.0", "@gsap/react": "^2.1.2"
   - "framer-motion": "^12.42.2", "lenis": "^1.3.25"
   - "lucide-react": "^1.24.0", "tailwindcss": "^4", "@tailwindcss/postcss": "^4"

2. Build `src/app/globals.css` with the Editorial Cyberpunk theme tokens:
   - Root CSS properties:
     --bg: #050505; --bg-2: #0a0a0a; --fg: #ffffff;
     --fg-dim: rgba(255,255,255,0.55); --fg-mute: rgba(255,255,255,0.25);
     --border: rgba(255,255,255,0.06); --border-hover: rgba(255,255,255,0.18);
     --font-display: 'Bebas Neue', 'Impact', sans-serif;
     --font-body: 'Inter', sans-serif;
     --font-mono: 'JetBrains Mono', monospace;
   - Implement the blueprint grid (`80px` linear gradient) and animated SVG fractal noise overlay classes.

3. Configure `src/lib/gsap-config.ts` to safely register GSAP and ScrollTrigger on client environments.
```

### Phase 2: Lenis Smooth Scrolling & Dynamic Glow Cursor

```markdown
Implement the smooth scrolling engine and custom dynamic cursor:

1. Create `src/hooks/useLenis.ts`:
   - Initialize Lenis smooth scroll with easing `(t) => Math.min(1, 1.001 - Math.pow(2, -10 * t))`.
   - Bind Lenis directly to `gsap.ticker` via `gsap.ticker.add((time) => lenis.raf(time * 1000))` and sync with `ScrollTrigger.update`.
   - Ensure clean teardown on component unmount.

2. Create `src/components/ui/CustomCursor.tsx`:
   - Inner dot tracked immediately via requestAnimationFrame.
   - Outer ring smoothed with an exponential damping factor.
   - Particle trail system emitting small fading dots when the cursor moves above a velocity threshold.
   - Support hover states for `default`, `link`, `button`, and `image/3d`.
   - Auto-disable via matchMedia `(pointer: coarse)` for mobile and touch devices.
```

### Phase 3: Cinematic Preloader with Curtain Reveal

```markdown
Create `src/components/sections/LoadingScreen.tsx`:

1. Build a full-screen `#050505` black overlay fixed at `z-index: 9999`.
2. Choreograph the entrance sequence with GSAP:
   - 0.3s: Scale and fade in the initials monogram ("SM").
   - 0.85s: Slide up the subtitle "Creative Developer".
   - 1.4s to 2.6s: Animate a hairline progress bar from 0% to 100% while a numeric text counter ticks up smoothly.
3. Reveal Sequence:
   - When the counter reaches 100%, trigger a vertical curtain reveal animation: animate the entire overlay upward (`yPercent: -100`) using `duration: 1.0, ease: 'power3.inOut'`.
   - Fire an `onComplete()` callback to mount and fade in the main navigation and hero.
```

### Phase 4: Sticky 280vh Parallax Hero with Gliding Portrait

```markdown
Build `src/components/sections/Hero.tsx` and `HeroBackground.tsx`:

1. Background Layers (`HeroBackground.tsx`):
   - Layer 1: 80px CSS blueprint grid.
   - Layer 2: Rotating SVG concentric radar targeting circles.
   - Layer 3: HTML5 Canvas ambient dust particle field drifting continuously.
   - Layer 4: Radial gradient halo and floor ground glow.

2. Hero Structure:
   - Outer wrapper: `height: 280vh; background: #080808;`.
   - Inner sticky viewport: `position: sticky; top: 0; height: 100vh; overflow: hidden;`.
   - Top metadata bar: Tags (`Web Dev`, `Mobile Dev`, `Full Stack`), release date, and tech stack tags.

3. Typography & Portrait Scrub:
   - Giant developer name ("SIDDHESH") rendered in split letters. On scroll progress 0.0 to 0.3, letters elevate (`translateY: -140px`), stretch, and blur out.
   - High-res alpha cutout portrait centered at the bottom. As the user scrubs, it glides smoothly to the left half (`x: -25vw`).

4. Sequenced Narrative Panels:
   - Panel 1 (Progress 0.0 -> 0.25): Headline "Web & Mobile Developer", bio copy, and skill badges.
   - Panel 2 (Progress 0.32 -> 0.58): Retro cyberpunk terminal block `developer_profile.sh` with identity telemetry and animated stats (4+ Years Experience, 30+ Projects, 15+ Tech).
   - Panel 3 (Progress 0.68 -> 1.00): Three capability cards with custom geometric icons (Web Development, Mobile App Development, Backend & Database).
```

### Phase 5: Dual Infinite Opposing Marquee

```markdown
Create `src/components/sections/MarqueeDivider.tsx`:

1. Design a dual-stream horizontal marquee section with hairline borders.
2. Stream 1 scrolls infinitely to the left; Stream 2 scrolls infinitely to the right.
3. Include inline branded SVG logos for core skills: React, Next.js, TypeScript, Three.js, GSAP, Node.js, Python, Android, and Tailwind CSS.
4. Use seamless CSS keyframe animations (`@keyframes marquee`) or GSAP infinite loops without stutter or jump on repeat.
```

### Phase 6: 3D Rapier Physics Interactive ID Lanyard Badge

```markdown
Build the interactive 3D credentials system in `src/components/3d/ExperienceCard.tsx` and `src/components/sections/Experience.tsx`:

1. R3F & Rapier World:
   - Setup `@react-three/fiber` Canvas with `Physics` from `@react-three/rapier`.
   - Configure a fixed top anchor (`y: 0`) and 3 intermediate dynamic sphere colliders with `angularDamping: 4, linearDamping: 4`.
   - Connect the chain using `useSphericalJoint` and `useRopeJoint` to anchor a cuboid `RigidBody` representing the conference badge.
   - Render the fabric strap using `meshline` with a repeating woven texture (`/lanyard.png`).

2. Dynamic In-Memory Canvas Texture:
   - Load base model `/card.glb` using `useGLTF`.
   - In `useMemo`, extract the base image texture from the card material.
   - Create an in-memory HTML5 `<canvas>` and draw the developer's credentials: Role, Company, Date, and Description directly onto the front face UV coordinates (`[0, 0, 0.5, 0.755]`).
   - Assign the result as a `THREE.CanvasTexture` so credentials update dynamically without requiring external image requests.

3. Interaction:
   - Support cursor dragging: visitors can pull and fling the badge with spring tension and physics momentum.
   - Integrate with GSAP ScrollTrigger so cards transition between job roles as the user scrolls.
```

### Phase 7: CSS 3D Perspective Z-Axis Projects Flythrough

```markdown
Create `src/components/sections/Projects.tsx`:

1. Viewport Setup:
   - Outer wrapper with `height: 500vh` to provide ample scroll track travel.
   - Pinned sticky container with CSS `perspective: 1200px` and `transform-style: preserve-3d`.

2. 3D Z-Axis Positioning:
   - Position project cards sequentially along the Z-axis: `initialZ = -i * 1600 - 800px`.
   - Hook into GSAP ScrollTrigger scrub: cards advance forward toward the camera as the user scrolls.
   - When a card passes the camera plane (`Z > 200px`), smoothly fade out (`opacity: 1 - (z - 200)/400`) and apply blur (`blur: (z - 200)/20px`).

3. Card Interaction:
   - Apply Framer Motion 3D tilt tracking mouse pointer offsets on hover.
   - Display project title, tagline, tech stack tags, live preview URL, and GitHub repository links.
```

### Phase 8: Interactive Skills Telemetry & Radar Dashboard

```markdown
Build `src/components/sections/Skills.tsx`:

1. Categorized Matrix:
   - Group skills by category: Frontend, Fullstack, WebGL, Motion, Backend.
   - Render detailed metrics for key skills: React (95%), Next.js (90%), Three.js (85%), GSAP (92%), TypeScript (94%), Node.js (88%), Python (82%).

2. Visual Telemetry:
   - Animated SVG circular gauges showing progress percentages.
   - Detailed technical descriptions of architectural competencies.
   - Animated water-drop indicator and dynamic ambient glow shifting to match each skill's brand color.
```

### Phase 9: Interactive Three.js Starfield & Magnetic Contact

```markdown
Create `src/components/sections/Contact.tsx` and `Footer.tsx`:

1. 3D Particle Starfield:
   - Set up an interactive Three.js Canvas with floating particle points that gently rotate and react to pointer coordinates.

2. Magnetic Social Buttons (`MagneticButton.tsx`):
   - Wrap GitHub, LinkedIn, Twitter/X, and Stack Overflow links in spring physics components that pull toward the cursor.
   - Dynamic ambient glow: Shift section lighting color based on the hovered channel (GitHub: white, LinkedIn: cyan, Twitter: blue, Stack Overflow: orange).

3. Editorial Footer:
   - Live local time indicator (Nashik, India / IST).
   - Copyright watermark and "Back to Top" smooth scroll button.
```

### Phase 10: Mobile Touch Fallbacks, 60 FPS Polish & SEO

```markdown
Finalize, polish, and optimize the portfolio for production:

1. Mobile Responsiveness:
   - For viewports `< 768px`, disable heavy pointer parallax listeners and hide the custom cursor.
   - Adjust 3D camera FOV and scale down the lanyard badge to fit mobile screens.
   - Ensure touch drag events on the physics lanyard work cleanly without interfering with vertical scroll.

2. Performance Audit:
   - Ensure all Three.js textures and geometries call `.dispose()` on unmount.
   - Verify that all GSAP ScrollTrigger instances include `anticipatePin: 1` and clean up via `st.kill()`.
   - Validate 60 FPS performance on both Chrome and Safari.

3. SEO & Metadata:
   - Add comprehensive Open Graph meta tags, structured title, and descriptions in `src/app/layout.tsx`.
```

---

## 3. Configuration & Personalization Template

When executing the prompts above for a new portfolio, replace these parameters with your personal information:

```json
{
  "developer": {
    "name": "YOUR NAME",
    "monogram": "YN",
    "role": "Creative Developer / Full Stack Engineer",
    "location": "City, Country",
    "bio": "Your 2-sentence elevator pitch highlighting passions and core skills.",
    "experienceYears": "4+",
    "projectsShipped": "25+",
    "technologiesCount": "15+"
  },
  "socials": {
    "github": "https://github.com/your-username",
    "linkedin": "https://linkedin.com/in/your-username",
    "twitter": "https://twitter.com/your-username",
    "email": "your-email@example.com"
  },
  "assets": {
    "portraitImage": "/images/your-profile.png",
    "badge3DModel": "/card.glb",
    "lanyardTexture": "/lanyard.png"
  }
}
```
