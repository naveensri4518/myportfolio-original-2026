# Dynamic Full Stack Developer Portfolio & GSAP Showcase

This repository contains:
1. **The Exact Same Original Website** (`original.html`) — Pristine, fully self-contained recreation of the *GSAP x Webflow* interactive showcase by Off Brand.
2. **The Converted Full Stack Developer Portfolio** (`index.html`) — The exact same website transformed into a modern, high-performance portfolio for a Full Stack Developer & System Architect (using default name **Jishnu Mondal**).

---

## 🚀 Quick Start / How to Run

You can open either file directly in any modern browser:

- **Portfolio Website (Default Entrypoint)**: Open [`index.html`](file:///Users/jishnu9/Web%20Dev%20Files/Dynamic%20Portfolio%20Website/index.html)
- **Original GSAP x Webflow Showcase**: Open [`original.html`](file:///Users/jishnu9/Web%20Dev%20Files/Dynamic%20Portfolio%20Website/original.html)

Or run a local static server:
```bash
python3 -m http.server 8000
```
Then visit:
- Portfolio: `http://localhost:8000/` or `http://localhost:8000/index.html`
- Original Site: `http://localhost:8000/original.html`

> **Note**: Both pages include a sleek floating switcher badge in the top-right corner allowing 1-click toggling between the **Original GSAP Showcase** and the **Full Stack Developer Portfolio**.

---

## 🛠 What Was Done

### Phase 1: In-Depth Analysis of the Workspace Files
The source files consisted of `Gsap X Webflow.html` and the `Gsap X Webflow_files` asset directory containing:
- **GSAP Animation Suite**: Core GSAP, ScrollTrigger, SplitText, ScrollSmoother, Flip, ScrollToPlugin, InertiaPlugin, ScrambleTextPlugin, Observer, Draggable, MotionPathPlugin, MotionPathHelper.
- **Smooth Scroll**: Lenis smooth scroll engine synced to GSAP ticker.
- **31 Visual Assets**: High-resolution AVIF cutouts, layered shadow passes, sky textures, runner sequences, and typography SVGs.
- **Issue Discovered**: The raw HTML was serialized from a live Chrome browser session, containing:
  - 113 DOM nodes with stale `aria-hidden="true"` generated mid-animation by SplitText.
  - Browser extension debris (`#volume-booster-visusalizer`, hidden textareas, audio outputs).
  - Remotely linked fonts and remote videos that would stall if offline.
  - Dynamic overlay proxies injected by Draggable that caused duplicate items in 3D perspective carousels.

### Phase 2: Pristine Recreation of the Original Website (`original.html`)
- **Offline Self-Containment**: Downloaded `WorkSans` (Regular, Medium, SemiBold) and `Anton-Regular` woff2 fonts locally into `Gsap X Webflow_files/`, with Google Fonts fallback.
- **Local Video Integration**: Downloaded the high-res `running.mp4` video locally into `Gsap X Webflow_files/`.
- **DOM Sanitization**: Reconstructed pure string nodes for all SplitText targets (`hero` title, `par` subtext, buttons, `videogrow` title, and text effects triggers).
- **Inertia & Slider Fixes**: Removed stale draggable overlay proxies and reset slide states so 3D cylinder and loop slider calculations run smoothly on startup.
- **Navigation Bar**: Section selector powered by GSAP `Flip` to glide the highlight indicator between tabs (`Flip`, `Scroll Trigger`, `Slider`, `Inertia`, `Text Effects`, `Marquee`).

### Phase 3: Conversion to a Full Stack Developer Portfolio (`index.html`)
The website was converted section-by-section to represent a top-tier Full Stack Developer and System Architect portfolio (default identity: **Jishnu Mondal**):

| Section | Original Feature | Converted Full Stack Portfolio Feature |
| :--- | :--- | :--- |
| **Top Nav** | Webflow x GSAP Branding | **Jishnu Mondal // Full Stack Dev** badge, live availability indicator & section tabs |
| **Hero (`#hero`)** | "MAKE IT MEAN MORE WITH GSAP" | **"BUILDING FULL STACK DIGITAL EXPERIENCES"** with split-character animation, interactive overview/architecture toggle, and tech stack motion stripes |
| **Stack (`#flip`)** | Grid/List animation toggle (Hover, Resize, Timeline) | **Tech Stack & System Domains** (Frontend, Backend, Databases, Cloud & DevOps, Real-Time Streams, Security & Performance) with GSAP `Flip` transition |
| **Architecture (`#scrolltrigger`)** | Pinned media grow animation | **"SYSTEM ARCHITECTURE"** — High-throughput distributed telemetry showcase scaling from card to full-screen view |
| **Projects (`#slider`)** | Infinite horizontal loop cards | **Production Projects Showcase**: Nexus AI Platform, Pulse Telemetry, DevFlow Cloud IDE, HyperSync DB, Aether Commerce |
| **Experience (`#inertia`)** | 3D draggable inertia cylinder | **8+ Years Career Timeline & Milestones**: Interactive 3D draggable cylinder with realistic inertia deceleration |
| **Principles (`#text`)** | Interactive text effect triggers | **Engineering Principles Playground**: Pixel Precision, Clean Architecture, System Resilience, Developer Ergonomics, Edge Performance, User-Centric Focus |
| **Ecosystem (`#marquee`)** | Dual-direction scroll marquee | **Full Stack Technology Ecosystem Marquee**: Continuous dual-flow banner of modern languages, cloud platforms, and tooling |
| **Footer** | Animated SVG logo & templates copy | **"Let's Build Something Extraordinary"**: Animated signature SVG, interactive contact bar (Email, GitHub, LinkedIn), and smooth Back-to-Top scroll |

---

## 📂 File Architecture
```
Dynamic Portfolio Website/
├── index.html                   # Converted Full Stack Developer Portfolio (Jishnu Mondal)
├── original.html                # Exact identical recreation of the original GSAP showcase
├── Gsap X Webflow.html          # Original unmodified browser-saved HTML
├── Gsap X Webflow_files/        # All local styles, scripts, fonts, images, and video
│   ├── gsap.min.js              # GSAP Core
│   ├── ScrollTrigger.min.js     # ScrollTrigger plugin
│   ├── SplitText.min.js         # SplitText plugin
│   ├── Flip.min.js              # Flip plugin
│   ├── InertiaPlugin.min.js     # InertiaPlugin
│   ├── Draggable.min.js         # Draggable plugin
│   ├── ScrambleTextPlugin.min.js# ScrambleText plugin
│   ├── lenis.min.js             # Lenis smooth scroll
│   ├── Anton-Regular.woff2      # Local Anton heading font
│   ├── WorkSans-*.woff2         # Local Work Sans body fonts
│   ├── running.mp4              # Local video asset
│   └── *.avif                   # Cutouts, textures, and illustration passes
├── build_portfolio.py           # Generator script for portfolio adaptation
├── update_portfolio.py          # Refinement and interactive copy handler script
└── README.md                    # Project documentation
```

