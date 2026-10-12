# Product Requirements Document (PRD)
## Creative Developer 3D Editorial Portfolio

---

## 1. Executive Summary & Vision

### 1.1 Vision Statement
The **Creative Developer 3D Editorial Portfolio** is an Awwwards / FWA-tier personal website designed to showcase high-level creative engineering, 3D WebGL rendering, physics simulation, and editorial typography. Combining the aesthetics of high-fashion luxury editorial layouts with cyberpunk terminal diagnostics, the site provides an unforgettable, cinematic experience for tech recruiters, design agency directors, and enterprise clients.

### 1.2 Primary Objectives
1. **Differentiate & Mesmerize**: Position the developer (Siddhesh More) at the top 1% of creative front-end and full-stack engineers through bespoke WebGL interactions and buttery GSAP transitions.
2. **Demonstrate Technical Mastery**: Showcase proficiency across modern React 19, Next.js 16, Three.js, React Three Fiber (R3F), Rapier physics simulation, GSAP ScrollTrigger, Lenis smooth scrolling, and Tailwind CSS v4.
3. **Showcase Real Work & Credentials**: Present professional history, education, and development projects through tactile, interactive 3D components (e.g., interactive physics lanyard badge, 3D Z-axis project flythrough).
4. **Seamless Cross-Device Experience**: Deliver high frame rates (60+ FPS) on modern desktop displays while gracefully adapting animations, touch controls, and layouts on tablet and mobile viewports.

---

## 2. Target Audience & Personas

| Persona | Role | Primary Goal | Key Experience Hook |
| :--- | :--- | :--- | :--- |
| **Design Agency Art Director** | Creative Director / Head of Studio | Evaluate visual finesse, motion choreography, and design taste. | Editorial typography, bespoke cursor trails, multi-layer parallax hero. |
| **Tech Recruiter / Talent Lead** | Technical Recruiter | Quickly assess core technologies, experience, and contact options. | Interactive 3D lanyard badges, clear stats panel, direct GitHub/LinkedIn CTA. |
| **Engineering VP / Lead Architect** | Tech Lead / Engineering Manager | Verify clean architecture, code quality, and technical depth. | WebGL physics integration, performant scroll-scrub animations, TypeScript typing. |
| **Freelance Client / Founder** | Startup CEO / Product Owner | Hire for full-stack web/mobile application delivery. | Project showcase, terminal profile diagnostics, contact inquiry trigger. |

---

## 3. Core Functional Requirements & Feature Matrix

### 3.1 Cinematic Preloader (`LoadingScreen`)
- **System Boot Sequence**: Displays an animated initials monogram ("SM") and progress bar.
- **Dynamic Percentage Counter**: Smoothly interpolates from `0%` to `100%` across sequenced milestones.
- **Curtain Reveal**: Upon completion (`100%`), the black preloader screen wipes vertically upward (`yPercent: -100`) with an exponential easing curve, revealing the hero canvas.

### 3.2 Dynamic Editorial Cursor (`CustomCursor`)
- **Dual-Ring Interpolation**: Central luminous dot tracked in real-time (`requestAnimationFrame`) paired with an inertia-damped outer glow ring.
- **Contextual Hover States**:
  - `default`: Electric green/cyan luminescence.
  - `link` / `button`: Enlarges and shifts to violet/purple accent.
  - `image` / `3d`: Expands into a translucent circular lens highlighting draggable elements.
- **Particle Trail**: Spawns ephemeral trailing particles that dissipate with velocity-based opacity decay.
- **Device Detection**: Automatically disables on touch-enabled or mobile devices to prevent interaction conflicts.

### 3.3 Multi-Stage Sticky Hero Experience (`Hero`)
- **Sticky Viewport Scroller**: A pinned `280vh` scroll track with a locked `100vh` sticky canvas viewport.
- **Display Typography Choreography**:
  - Giant background title (`SIDDHESH`) rendered with individual letter spans.
  - Scroll-triggered letter elevation, vertical stretching, and blur dissipation.
- **Centerpiece Developer Portrait**:
  - High-resolution alpha-masked portrait centered at bottom.
  - As scroll progresses, glides smoothly to the left half (`-25vw`), creating space for editorial panels on the right.
- **Sequenced Three-Panel Narrative**:
  - **Panel 1 (Intro)**: Creative developer intro, headline, and primary tech chips.
  - **Panel 2 (Terminal Profile & Stats)**: Retro cyberpunk terminal block (`developer_profile.sh`), identity telemetry, and stat counters (`4+ Years`, `30+ Projects`, `15+ Tech`).
  - **Panel 3 (Capabilities)**: Icon-accented breakdowns for Web Development, Mobile Development, and Backend/Database Engineering.
- **Multi-Layer Background Stack**:
  1. CSS Blueprint Grid (`80px` cadence)
  2. Rotating SVG Radar Rings
  3. Canvas particle dust field with continuous drift
  4. Radial gradient halo & ground glow beneath portrait
  5. SVG fractal turbulence noise overlay

### 3.4 Infinite Marquee Dividers (`MarqueeDivider`)
- **Dual Stream Infinite Ribbon**: Horizontally looping skill ribbons with opposite directional vectors.
- **Branded Vector Badges**: SVG icons for React, Next.js, TypeScript, Three.js, GSAP, Node.js, Python, Kotlin, and Tailwind CSS.
- **Hover Speed Damping**: Seamless CSS/GSAP keyframe transitions without jumping or layout shifts.

### 3.5 3D Physics-Simulated Interactive Credentials (`Experience` & `Education`)
- **Rapier Physics Rope & Badge Simulation**:
  - Utilizes `@react-three/rapier` to simulate a physical conference badge hanging on a fabric lanyard.
  - Multi-segment rope joint chain (`useRopeJoint`, `useSphericalJoint`) connected to an anchor point.
  - RigidBody card responds to mouse drags, gravity, centrifugal forces, and collisions.
- **Dynamic In-Memory Canvas Texture**:
  - Dynamic generation of HTML5 `<canvas>` elements mapping candidate details (Role, Company, Dates, Skills, Degree, College) directly into the GLTF model's front UV atlas (`/card.glb`).
- **Interactive Tugging & Card Swapping**:
  - ScrollTrigger updates the active credential card in real-time.
  - Physics trigger drops or resets cards with tactile physics elasticity.

### 3.6 3D Perspective Z-Axis Projects Showcase (`Projects`)
- **CSS 3D Camera Flythrough**:
  - Pinned viewport with CSS `perspective: 1200px` container.
  - Project cards positioned sequentially along the Z-axis (`-i * 1600 - 800px`).
  - As the user scrolls, cards translate forward through space toward the camera, smoothly fading and blurring as they pass the camera plane (`Z > 200px`).
- **Card Interactive Tilt & Expander**:
  - Framer Motion 3D tilt tracking mouse pointer on hover.
  - Expandable modal/drawer for in-depth tech stack breakdowns and direct external repository links.

### 3.7 Interactive Matrix Skills Section (`Skills`)
- **Categorized Proficiency Metrics**:
  - Interactive radar-style skill selector (Frontend, Fullstack, WebGL, Motion, Backend).
  - Animated SVG circular progress meters and detailed skill narratives.
  - Water-drop accent motion and dynamic color shifts synchronized to each skill's primary brand color.

### 3.8 Starfield Particle Contact Portal (`Contact` & `Footer`)
- **Interactive Three.js Particle Cloud**:
  - Canvas rendering floating particle field that responds to mouse coordinates.
- **Magnetic Link Buttons**:
  - Magnetic physics buttons for GitHub, LinkedIn, Twitter/X, Stack Overflow, and Email.
  - Dynamic ambient color shifting based on hovered social channel.
- **Editorial Footer**:
  - Local Nashik, India live time indicator, copyright watermark, and back-to-top smooth scroller.

---

## 4. Non-Functional Requirements

### 4.1 Performance & Frame Rate
- **Target FPS**: Minimum 60 FPS on desktop (Chrome, Safari, Firefox, Edge).
- **Asset Optimization**: 3D models (`card.glb`) compressed to under 700 KB; textures optimized with WebP/PNG compression.
- **WebGL Lifecycle**: Dynamic importing (`next/dynamic` with `ssr: false`) for all Canvas and WebGL components to prevent hydration mismatch and server memory leaks.
- **Throttled Computation**: Parallax listeners and mouse tracking executed strictly via `requestAnimationFrame` or GSAP internal ticker.

### 4.2 Smooth Scrolling Architecture
- **Inertia Physics**: Integrated **Lenis 1.3** smooth scroller synchronized with **GSAP ScrollTrigger**.
- **Scroll Syncing**: `lenis.on('scroll', ScrollTrigger.update)` and `gsap.ticker.add((time) => lenis.raf(time * 1000))` ensuring buttery scrub fidelity without frame drops.

### 4.3 Accessibility (a11y) & SEO
- **Semantic HTML5**: Native `<main>`, `<section>`, `<nav>`, `<h1>`-`<h3>`, `<button>`, and `<a>` landmarks.
- **Screen Reader Support**: Hidden decorative elements flagged with `aria-hidden="true"`; interactive controls equipped with descriptive `aria-label` tags.
- **Meta & Open Graph**: Descriptive Open Graph meta tags, responsive viewport settings, and crisp favicon iconography.

---

## 5. Master Prompt for AI Re-creation & Evolution

To recreate or build an even more advanced iteration of this portfolio using an LLM or autonomous agent, use the following master prompt:

```markdown
Build a world-class, Awwwards-tier 3D Creative Developer Portfolio using Next.js 16 (App Router), React 19, TypeScript, Three.js, @react-three/fiber, @react-three/rapier, GSAP (ScrollTrigger), Framer Motion, Lenis smooth scroll, and Tailwind CSS v4.

Visual Style:
- Aesthetic: Editorial Dark Luxury Magazine meets Cyberpunk Terminal.
- Color Palette: #050505 background, #ffffff high-contrast typography, accents of neon electric blue (#00d4ff), matrix green (#00ff41), and ultraviolet (#bf5af2).
- Fonts: Bebas Neue (giant display titles), Inter (clean body text), JetBrains Mono (terminal code & telemetry).
- Multi-layer background: Blueprint grid (80px), rotating SVG radar rings, canvas floating dust particles, and subtle SVG fractal noise overlay.

Key Sections & Mechanics:
1. Cinematic Preloader: Monogram logo fade, progress counter 0->100%, vertical curtain reveal.
2. Custom Glow Cursor: Dual-ring mouse follower with particle trail, expanding on links and 3D canvases.
3. Editorial Navigation: Minimalist frosted glass navbar with logo, section jump links, social icons, and theme pill.
4. Sticky Pinned Hero (280vh): Split-letter giant typography ('SIDDHESH') flying up on scroll; full-length cutout portrait gliding from center to left; sequenced 3-stage narrative panels fading in on the right (Intro -> Cyberpunk Terminal Specs -> Technical Disciplines).
5. Infinite Dual Marquee: Dual opposing ticker streams with tech SVG icons and subtle borders.
6. 3D Rapier Physics Credentials: Real-time 3D lanyard ID badge using @react-three/rapier (rope & spherical joints), meshline strap, and dynamic HTML5 canvas textures drawing role/company details onto the GLTF card UV map.
7. 3D Perspective Z-Axis Projects: Pinned CSS 3D perspective viewport where project cards travel forward along the Z-axis toward the camera on scroll scrub.
8. Matrix Skills Radar: Interactive skill category breakdown with animated SVG circular telemetry and custom brand color glow.
9. Interactive Starfield Contact: Three.js ambient particle sphere, magnetic social buttons with reactive hover colors, and local time ticker.
```
