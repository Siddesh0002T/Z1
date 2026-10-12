# Development Roadmap, Tasks & AI Generation Prompts
## Creative Developer 3D Editorial Portfolio

---

## 1. Feature Status Matrix

| Module | Status | Verification Check |
| :--- | :--- | :--- |
| **Cinematic Preloader** | ✅ Completed | Tested 0% to 100% counter, logo scale-in, curtain reveal to page. |
| **Custom Glow Cursor** | ✅ Completed | Dual-ring lerp interpolation, particle trail, hover expansion states. |
| **Sticky Hero 280vh Scrub** | ✅ Completed | Split-letter elevation, portrait glide to left, 3-panel narrative scrub. |
| **Multi-Layer Background** | ✅ Completed | CSS grid, SVG rotating radar, canvas floating dust, SVG fractal noise. |
| **Dual Infinite Marquee** | ✅ Completed | Opposing ticker streams with branded SVG skill badges. |
| **3D Rapier Physics Credentials**| ✅ Completed | Lanyard card simulation, dynamic CanvasTexture UV rendering, drag physics. |
| **Interactive Skills Matrix** | ✅ Completed | Radar categories, animated SVG circular progress gauges, brand glowing drops. |
| **3D Perspective Z-Axis Projects**| ✅ Completed | CSS 3D perspective flythrough with interactive project card tilt & links. |
| **Starfield Particle Contact** | ✅ Completed | Three.js particle cloud, magnetic social links, dynamic color shifting. |
| **Smooth Scrolling Engine** | ✅ Completed | Lenis smooth scroll ticker locked with GSAP ScrollTrigger. |
| **SEO & OpenGraph Tags** | ✅ Completed | Full metadata, responsive viewport, social sharing preview tags. |

---

## 2. Backlog & Advanced Future Enhancements

### 2.1 Interactive Audio / Sound Effects (SFX) Engine
- Integrate Web Audio API or Howler.js for subtle haptic auditory feedback:
  - Soft mechanical click on magnetic button hover.
  - Subtle synthesizer whoosh during section transitions.
  - Cyberpunk terminal beep sound on text decryption scramble.
  - Audio mute/unmute toggle in the navigation bar.

### 2.2 Custom GLSL Post-Processing Shaders
- Add fullscreen WebGL post-processing passes:
  - Dynamic chromatic aberration that scales with Lenis scroll velocity.
  - Lens distortion on hover over 3D project cards.
  - Interactive ripple shader when clicking on the background canvas.

### 2.3 Mobile Device Gyroscope Tilt
- Access `DeviceOrientationEvent` on iOS / Android devices:
  - Tilt the 3D physics lanyard badge according to the physical orientation of the mobile phone.
  - Dynamic parallax shifting of the hero portrait based on device tilt.

### 2.4 Deep Case Study Pages
- Create dynamic `/projects/[slug]` routes for in-depth engineering breakdowns:
  - Architecture diagrams, performance benchmarks, and interactive live demo embeds.

---

## 3. Modular Step-by-Step Generation Prompts

Use these prompts sequentially to reproduce this portfolio or create an advanced creative developer showcase:

### Prompt 1: Project Setup, Dependencies & Theme Tokens
```markdown
Create a new Next.js 16 project using React 19, TypeScript, and Tailwind CSS v4.
Install dependencies:
- gsap, @gsap/react
- three, @types/three, @react-three/fiber, @react-three/drei, @react-three/rapier, meshline
- framer-motion, lenis, lucide-react

Configure `globals.css` with an Editorial Cyberpunk theme:
- Deep obsidian background (#050505), surface dark (#0a0a0a), white text (#ffffff).
- Neon accents: electric cyan (#00d4ff), matrix green (#00ff41), ultraviolet (#bf5af2).
- Font variables: Bebas Neue for display headings, Inter for body, JetBrains Mono for telemetry.
- Multi-layer background classes: 80px CSS blueprint grid and SVG fractal noise overlay.
```

### Prompt 2: Lenis Smooth Scrolling & Custom Glow Cursor
```markdown
Implement smooth scrolling and custom mouse interactions:
1. Create `src/hooks/useLenis.ts`: Initialize Lenis smooth scroll and bind its requestAnimationFrame loop directly into `gsap.ticker` to ensure perfect synchronization with GSAP ScrollTrigger.
2. Create `src/components/ui/CustomCursor.tsx`: Build a custom cursor with a central luminous point and a lerped outer aura ring. Add a particle trail system that emits soft glowing dots on mouse movement. Include hover state detection for links, buttons, and 3D canvases. Disable automatically on touch devices.
```

### Prompt 3: Cinematic Preloader Curtain Reveal
```markdown
Create `src/components/sections/LoadingScreen.tsx`:
- Build a full-screen luxury editorial preloader overlay.
- Animate an initials monogram ("SM") scaling and fading in.
- Animate a numeric percentage counter smoothly counting from 0 to 100 with a thin progress line.
- Upon reaching 100%, animate the entire black overlay sliding upward (`yPercent: -100`) with `power3.inOut` easing, invoking an `onComplete` callback that reveals the main page content.
```

### Prompt 4: Sticky Pinned Hero with Gliding Portrait & 3-Panel Narrative
```markdown
Build `src/components/sections/Hero.tsx` and `HeroBackground.tsx`:
- Container: Outer wrapper with `height: 280vh` containing a sticky `100vh` frame.
- Background: Rotating SVG concentric radar rings, 80px blueprint grid, and an animated HTML5 canvas particle dust field.
- Split-Letter Title: Giant display title ('SIDDHESH') spanning 22vw. On scroll scrub (0.0 to 0.3), letters fly upward with stagger and blur dissipation.
- Portrait Glide: Center bottom cutout image of the developer. As the user scrolls, the portrait glides smoothly to the left half (`-25vw`).
- 3 Sequenced Narrative Panels: Right half reveals 3 distinct panels across scroll progress:
  - Panel 1: Creative developer introduction with skill badges.
  - Panel 2: Cyberpunk terminal block (`developer_profile.sh`) with location, role, and stat counters (4+ Years, 30+ Projects).
  - Panel 3: Technical disciplines with custom geometric icons.
```

### Prompt 5: 3D Rapier Physics Interactive Credentials (Lanyard Badges)
```markdown
Create `src/components/3d/ExperienceCard.tsx` and `src/components/sections/Experience.tsx`:
- Set up an interactive 3D WebGL scene using `@react-three/fiber` and `@react-three/rapier`.
- Load a 3D badge model (`card.glb`) and simulate a hanging lanyard badge using Rapier physics:
  - Create a 4-node chain with dynamic spherical colliders and a fixed anchor.
  - Connect links using `useSphericalJoint` and `useRopeJoint`.
  - Render the strap using `meshline` and a fabric texture.
- Dynamic Canvas Texture: Generate an HTML5 canvas at runtime that draws company name, role, date, and description onto the GLTF material's front UV atlas.
- Interaction: Allow users to click and drag the card with real-time physics elasticity, momentum, and return-to-rest behavior.
```

### Prompt 6: 3D Perspective Z-Axis Projects Flythrough
```markdown
Build `src/components/sections/Projects.tsx`:
- Pinned viewport with CSS `perspective: 1200px`.
- Project cards positioned sequentially along the Z-axis (`initialZ = -i * 1600 - 800px`).
- Connect to GSAP ScrollTrigger: As the user scrolls, project cards translate forward along the Z-axis toward the camera.
- Fade out and blur cards as they pass behind the camera plane (`Z > 200px`).
- Add 3D mouse tilt on hover using Framer Motion springs, showing project details, live preview links, and GitHub source links.
```

### Prompt 7: Interactive Matrix Skills Radar & Telemetry
```markdown
Create `src/components/sections/Skills.tsx`:
- Build an interactive skills dashboard divided into Frontend, Fullstack, WebGL, Motion, and Backend.
- Display animated circular SVG telemetry meters indicating percentage proficiencies (React 95%, Three.js 85%, GSAP 92%, etc.).
- On selecting a skill, animate a glowing water-drop accent and shift the section's ambient illumination to match the skill's brand color.
```

### Prompt 8: Starfield Particle Cloud & Magnetic Contact Portal
```markdown
Create `src/components/sections/Contact.tsx` and `Footer.tsx`:
- Render an ambient 3D rotating starfield particle cloud using Three.js points and buffer geometries.
- Build magnetic social link buttons (GitHub, LinkedIn, Twitter/X, Stack Overflow) that attract toward the cursor using spring physics.
- Add dynamic ambient glow that shifts color depending on which social link is hovered.
- Add an editorial footer with local time display, copyright info, and a back-to-top smooth scroller.
```
