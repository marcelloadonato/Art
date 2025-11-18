# Living Theorem

**A single-canvas mathematical art playground fusing 10+ classic concepts into one living, breathing visualization.**

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Three.js](https://img.shields.io/badge/three.js-r169-orange)

## 🎨 Overview

Living Theorem is an interactive WebGL art application that brings together fundamental mathematical concepts into a unified, real-time visualization. Watch as Voronoi diagrams morph, fractals zoom infinitely, particles breathe harmonically, and your drawings decompose into Fourier epicycles—all governed by the golden ratio.

## ✨ Features

### 10 Interconnected Mathematical Concepts

1. **Voronoi Tessellation** - Dynamic Voronoi diagram with drifting seeds arranged using golden angle spirals
2. **Mandelbrot Fractals** - Infinite fractal zoom embedded within each Voronoi cell
3. **Golden Ratio (φ) System** - All colors, layouts, and timing based on φ = 1.618...
4. **Lissajous Curves + Fourier** - Draw freehand → watch it decompose into rotating epicycles
5. **Parametric Roses** - Beautiful polar equation petals: ρ = cos(kθ)
6. **Ulam Prime Spirals** - Prime number detection with visual bursts
7. **Polyhedral Morphing** - Background geometry breathes between platonic solids
8. **Harmonic Symmetry** - Periodic rotational symmetry pulses (90°, 180°)
9. **Particle Systems** - 10,000 particles distributed via Fibonacci sphere
10. **Golden Color Palettes** - All hues derived from φ progressions

## 🎮 Controls

### Mouse/Touch Interactions

| Action | Effect |
|--------|--------|
| **Drag** | Draw Lissajous curves that decompose into Fourier epicycles |
| **Scroll/Pinch** | Adjust parametric rose petals (k value) |
| **Click/Tap** | Add or remove Voronoi seeds (max 32) |
| **Double-tap** | Trigger symmetry pulse |

### Keyboard Shortcuts

| Key | Action |
|-----|--------|
| **Space** | Pause/Resume animation |
| **R** | Reset entire scene |
| **S** | Save screenshot (PNG) |
| **G** | Start/Stop GIF recording |
| **1** | Toggle Voronoi layer |
| **2** | Toggle particle system |
| **3** | Toggle Lissajous curves |
| **4** | Toggle polyhedron |

### GUI Panel

The dat.GUI panel (top-right) provides real-time control over:

- **Voronoi**: Seed count, drift speed
- **Mandelbrot**: Iteration depth, zoom level
- **Parametric Rose**: Petal count (k value)
- **Particles**: Size, flow speed, count
- **Time**: Global time scale, pause state
- **Polyhedron**: Morph factor between shapes
- **Layers**: Individual visibility toggles

## 🔬 Mathematical Explanations

### Voronoi Tessellation

Divides the plane into regions based on proximity to seed points. Seeds are initially placed using the **golden angle** (≈137.5°):

```
θ = n × (2π / φ²)
```

This creates optimal spiral packing with no regular patterns.

### Mandelbrot Set

For each complex number `c`, iterates:

```
z_{n+1} = z_n² + c
z_0 = 0
```

If |z| remains bounded after many iterations, `c` is in the set (colored by escape time).

### Golden Ratio Color System

Colors generated using φ-based hue rotation:

```
hue(t) = (t × φ) mod 1.0
```

This ensures maximum perceptual distinction between adjacent colors.

### Fourier Decomposition

Your drawn curve is decomposed via Discrete Fourier Transform (DFT):

```
X_k = Σ(n=0 to N-1) x_n × e^(-2πikn/N)
```

Each frequency component becomes a rotating circle (epicycle).

### Parametric Rose

Polar equation:

```
ρ(θ) = cos(k × θ)
```

- If k is rational (p/q), rose has finite petals
- If k is irrational, rose never closes
- Scroll to adjust k in real-time

### Ulam Prime Spiral

Numbers arranged in a spiral:

```
1  ← starting at center
↓
2 3 → ...
```

Prime numbers are detected and highlighted, revealing mysterious diagonal patterns.

### Polyhedral Morphing

Vertices breathe using harmonic motion:

```
scale(t) = 1 + 0.1 × sin(t × φ)
```

Rotation speeds also scaled by φ for non-repeating patterns.

### Fibonacci Sphere Distribution

Particles placed using:

```
φ = arccos(1 - 2(i + 0.5)/N)
θ = π(1 + √5) × i
```

This achieves perfectly uniform distribution on a sphere.

## 🚀 Getting Started

### Quick Start

1. Simply open `index.html` in a modern browser
2. No build process, no dependencies to install
3. Works offline after first load

### Requirements

- Modern browser with WebGL 2.0 support
  - Chrome 56+
  - Firefox 51+
  - Safari 15+
  - Edge 79+
- GPU with decent shader support
- 2GB+ RAM recommended

### Performance Tips

- Lower particle count for slower devices
- Reduce Mandelbrot iterations if stuttering
- Close other GPU-intensive applications
- Disable post-processing for max FPS

## 🎨 Creative Exploration

### Recommended Experiments

1. **Slow Morph**: Set time scale to 0.2, watch the slow dance
2. **Prime Focus**: Increase Voronoi seeds to 32, observe prime patterns
3. **Golden Draw**: Draw spirals matching the golden ratio
4. **Fractal Deep Dive**: Max out Mandelbrot depth, scroll into infinity
5. **Harmonic Resonance**: Set rose k to φ (≈1.618)

### Artistic Variations

- **Minimal**: Disable all layers except Voronoi + Mandelbrot
- **Chaos**: Max all values, draw frantically
- **Meditation**: Pause time, single Voronoi seed, slow mouse circles
- **Fibonacci Focus**: Set rose k to 5, 8, 13 (Fibonacci numbers)

## 📐 Technical Architecture

### Stack

- **Three.js r169** - WebGL rendering engine
- **GLSL Shaders** - GPU-accelerated math (Voronoi, Mandelbrot)
- **dat.GUI** - Real-time parameter control
- **Vanilla JavaScript** - No framework overhead

### File Structure

```
Living-Theorem/
├── index.html          # Single self-contained file
└── README.md           # This file
```

### Performance Targets

- **60 FPS** @ 1920×1080 on mid-range laptop (2022)
- **< 800 KB** gzipped total size
- **Mobile-friendly** with touch support
- **10,000+ particles** without frame drops

### Shader Pipeline

1. **Vertex Shader**: Transform geometry, pass varyings
2. **Fragment Shader**:
   - Calculate Voronoi cells
   - Render Mandelbrot per-cell
   - Apply golden ratio colors
   - Detect primes, draw roses
   - Mix all layers
3. **Post-processing** (optional): Bloom, vignette, grain

## 🎓 Educational Value

### Learning Opportunities

This project demonstrates:

- **Complex GLSL Programming** - Multi-layer shader composition
- **Mathematical Visualization** - Abstract → Visual
- **Real-time Graphics** - 60fps constraint optimization
- **Interaction Design** - Multi-modal input (mouse, touch, keyboard)
- **Generative Art** - Algorithmic beauty
- **Number Theory** - Primes, golden ratio, Fibonacci

### Classroom Use

Perfect for:

- **Mathematics**: Visual proof of concepts
- **Computer Graphics**: WebGL/shader programming
- **Computer Science**: Algorithm visualization
- **Art/Design**: Generative/procedural art
- **Physics**: Harmonic motion, wave decomposition

## 🛠️ Customization

### Modifying Parameters

Edit the `params` object in `index.html`:

```javascript
this.params = {
    numVoronoiSeeds: 16,      // Start with more/fewer cells
    mandelbrotDepth: 64,       // Higher = more detail (slower)
    roseK: 5.0,                // Petal count
    particleCount: 10000,      // Increase for denser clouds
    timeScale: 1.0,            // Speed up/slow down
    // ... and more
};
```

### Adding Your Own Layers

1. Create new shader in `<script type="x-shader/...">` tags
2. Add material in `setupMaterials()`
3. Create geometry in `setupGeometry()`
4. Update in `update()` method
5. Add GUI control in `setupGUI()`

### Color Palette Tweaking

Modify `goldenColor()` function:

```javascript
goldenColor(t) {
    const hue = (t * this.PHI) % 1.0;
    // Change HSV→RGB conversion here
    // Or use OKLCH for perceptual uniformity
}
```

## 📸 Export & Sharing

### Screenshot

- Press **S** or click "Screenshot" in GUI
- Saves full-resolution PNG
- Filename: `living-theorem-[timestamp].png`

### GIF Recording

- Press **G** to start/stop
- Currently shows placeholder alert
- **To implement**: Integrate FFmpeg.wasm for actual encoding

### URL State Sharing

Currently not implemented. To add:

```javascript
// Encode state to URL hash
location.hash = btoa(JSON.stringify(this.params));

// Decode on load
const state = JSON.parse(atob(location.hash.slice(1)));
```

## 🐛 Known Issues

- GIF export requires FFmpeg.wasm integration
- Mobile performance varies by device
- Safari may have reduced particle counts
- Some shader features require WebGL 2.0

## 🔮 Future Enhancements

- [ ] Reaction-diffusion texture layer
- [ ] Audio reactivity (Web Audio API)
- [ ] Curl noise flow fields
- [ ] Post-processing effects (bloom, chromatic aberration)
- [ ] Julia set mode toggle
- [ ] Lorenz attractor integration
- [ ] VR/AR mode
- [ ] Multiplayer collaborative canvas

## 🤝 Contributing

This is a solo art project, but suggestions welcome!

1. Fork the repo
2. Create feature branch
3. Test on multiple devices
4. Submit PR with performance metrics

## 📜 License

MIT License - Do whatever you want, attribution appreciated!

## 🙏 Acknowledgments

- **Benoit Mandelbrot** - Fractal geometry
- **Georgy Voronoi** - Tessellation theory
- **Joseph Fourier** - Harmonic analysis
- **Fibonacci** - Sequence of natural growth
- **Euclid** - Golden ratio discovery
- **Three.js Team** - Amazing WebGL library

## 📚 References

- [Three.js Documentation](https://threejs.org/docs/)
- [The Book of Shaders](https://thebookofshaders.com/)
- [Golden Ratio in Art](https://en.wikipedia.org/wiki/Golden_ratio)
- [Mandelbrot Set](https://en.wikipedia.org/wiki/Mandelbrot_set)
- [Fourier Transform](https://en.wikipedia.org/wiki/Fourier_transform)
- [Voronoi Diagram](https://en.wikipedia.org/wiki/Voronoi_diagram)

---

**Made with ♾️ by a lover of mathematical beauty**

*"Mathematics is the art of giving the same name to different things."* — Henri Poincaré
