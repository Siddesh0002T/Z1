# Visual Design System & Aesthetic Specification
## Creative Developer 3D Editorial Portfolio

---

## 1. Aesthetic Philosophy

The visual language blends **High-Fashion Editorial Magazine Design** with **Cyberpunk Terminal Diagnostics** and **Tactile WebGL 3D Realism**.

- **Monumental Editorial Typography**: Dramatic, condensed headline typefaces (`Bebas Neue`) paired with surgical typographic layout.
- **Deep Luxury Monochrome**: A pitch-black obsidian foundation (`#050505`) elevated by razor-sharp white contrast and laser-precise neon accents.
- **Physical Tactility**: 3D physics-based conference badges on fabric lanyards, CSS 3D perspective flythroughs, and responsive magnetic cursors.
- **Atmospheric Multi-Layer Depth**: Fine-grain blueprint grids, rotating radar targeting rings, ambient dust particles, and subtle analog film noise.

---

## 2. Color System & Design Tokens

### 2.1 Core Palette

```
Obsidian Black  [#050505]  Primary background
Surface Black   [#0a0a0a]  Card and panel elevated surface
Pure White      [#ffffff]  Primary text and high-contrast headlines
White Dim       [rgba(255,255,255,0.55)]  Secondary narrative text
White Mute      [rgba(255,255,255,0.25)]  Metadata, dates, and border accents
Glass Border    [rgba(255,255,255,0.06)]  Default hairline dividers
Hover Border    [rgba(255,255,255,0.18)]  Active element border highlights
```

### 2.2 Cyberpunk Accent Palette

| Accent Name | HEX Code | Purpose & Application |
| :--- | :--- | :--- |
| **Electric Cyan** | `#00d4ff` | Interactive links, terminal identity data, 3D badge accents, glow halos. |
| **Matrix Green** | `#00ff41` | System status (`STATUS: Available`), terminal success badges, Node.js highlights. |
| **Ultraviolet / Purple** | `#bf5af2` | Magnetic contact triggers, secondary glow gradients, Twitter/X hover highlights. |
| **React Cyan** | `#61dafb` | React / Next.js skill pills and interactive circular meters. |
| **GSAP Chartreuse** | `#88ce02` | GSAP motion design branding and progress indicators. |

---

## 3. Typography System

### 3.1 Font Families

1. **Display Heading**: `'Bebas Neue', 'Impact', sans-serif`
   - *Characteristics*: Ultra-condensed, architectural uppercase display typeface.
   - *Usage*: Hero developer name (`SIDDHESH`), section title watermarks (`PROJECTS`, `EXPERIENCE`, `SKILLS`).
2. **Body & Interface**: `'Inter', 'Space Grotesk', sans-serif`
   - *Characteristics*: Modern neo-grotesque sans-serif with high legibility and balanced proportions.
   - *Usage*: Bio text, card descriptions, navigation links, button text.
3. **Monospace & Telemetry**: `'JetBrains Mono', 'Courier New', monospace`
   - *Characteristics*: Technical monospaced font with high distinction between characters.
   - *Usage*: Terminal logs, code blocks, project tags, skill levels, timestamps.

### 3.2 Fluid Typographic Scale

| Role | Font Family | Size Specification | Letter Spacing | Line Height |
| :--- | :--- | :--- | :--- | :--- |
| **Monumental Hero Name** | Display | `clamp(14vw, 22vw, 24vw)` | `-0.02em` | `0.82` |
| **Section Big Watermark** | Display | `clamp(4.5rem, 9vw, 8rem)` | `-0.03em` | `0.9` |
| **Card Header / Title** | Display | `clamp(1.4rem, 2.2vw, 2.0rem)` | `0.02em` | `1.1` |
| **Body Narrative** | Body | `clamp(0.8rem, 1.1vw, 0.95rem)` | `normal` | `1.85` |
| **Technical Telemetry** | Monospace | `clamp(0.45rem, 0.7vw, 0.65rem)` | `0.15em` | `1.4` |

---

## 4. Multi-Layer Visual Atmosphere

Every section is underpinned by 5 distinct visual layers that create depth and visual richness:

```
┌────────────────────────────────────────────────────────┐
│ Layer 5: Film Noise Overlay (SVG fractalNoise 0.032)   │
├────────────────────────────────────────────────────────┤
│ Layer 4: Ambient Floating Dust Particles (HTML5 Canvas)│
├────────────────────────────────────────────────────────┤
│ Layer 3: Rotating Radar Targeting Rings (Concentric SVG)│
├────────────────────────────────────────────────────────┤
│ Layer 2: Radial Glow Halo Spotlights & Ground Glows    │
├────────────────────────────────────────────────────────┤
│ Layer 1: Blueprint Precision Grid (80px x 80px CSS)    │
├────────────────────────────────────────────────────────┤
│ Base Background: #050505 (Obsidian Black)              │
└────────────────────────────────────────────────────────┘
```

### 4.1 Blueprint Precision Grid
Rendered via CSS linear gradients:
```css
background-image:
  linear-gradient(rgba(255, 255, 255, 0.035) 1px, transparent 1px),
  linear-gradient(90deg, rgba(255, 255, 255, 0.035) 1px, transparent 1px);
background-size: 80px 80px;
```

### 4.2 Analog Noise Overlay
Continuous noise jitter created via an inlined SVG fractal noise filter:
```css
.hero-noise {
  position: fixed;
  inset: 0;
  pointer-events: none;
  opacity: 0.032;
  background-image: url("data:image/svg+xml,...");
  animation: noise-shift 0.1s steps(1) infinite;
}
```

---

## 5. 3D WebGL Materials & Shading System

### 5.1 ID Card Model (`/card.glb`)
- **Base Material**: `MeshPhysicalMaterial` with subtle plastic glossiness (`roughness: 0.2`, `metalness: 0.1`).
- **Dynamic Front Face**: UV coordinates `[0, 0, 0.5, 0.755]` mapped to an in-memory high-res `THREE.CanvasTexture` rendering developer identity, QR codes, and company logos.
- **Back Face**: Solid matte black (`#080808`) with subtle debossed cybernetic line work.

### 5.2 Fabric Lanyard Strap
- **Geometry**: `MeshLineGeometry` generated dynamically along Catmull-Rom spline curves calculated from the 4 Rapier physics nodes.
- **Material**: `MeshLineMaterial` using texture `/lanyard.png` with repeating typographic branding (`CREATIVE DEV // 2026`).

### 5.3 Studio Lighting Pipeline
- **Environment**: Studio HDR environment (`city` preset) blurred to `0.8` for soft ambient reflections.
- **Lightformers**:
  - Top directional lightformer: Intensity `2.0`, white rim accent.
  - Side fill lightformer: Soft cyan tint (`#00d4ff`) to highlight card bevels.

---

## 6. Micro-Interactions & Motion Design

### 6.1 Custom Cursor Physics
- Central pinpoint tracked to exact mouse coordinates.
- Outer aura ring lerped with exponential dampening (`0.15` factor).
- Particle emitter creates faint fading trail dots when cursor moves faster than threshold velocity.

### 6.2 Cyberpunk Text Scramble Decryption
- Hovering over buttons or revealing terminal lines triggers `useScramble`.
- Characters cycle through random cybernetic runes (`@#$%^&*!?><|~+-=01`) before resolving from left to right.

### 6.3 Magnetic Physics Buttons
- Elements wrapped with `<MagneticButton>` compute relative mouse offset:
  ```typescript
  const x = (clientX - (left + width / 2)) * 0.35;
  const y = (clientY - (top + height / 2)) * 0.35;
  ```
- Position springs back to `(0, 0)` smoothly via Framer Motion spring physics (`stiffness: 150, damping: 15`).
