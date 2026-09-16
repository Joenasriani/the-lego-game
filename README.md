BrickBuilder 3D


## 🚀 Features

### Core Mechanics

- Modular Building: Snap-to-grid placement with collision checks and a ghost brick preview.
- Build / Move / Delete modes with rotation support.
- Undo / Redo history stack for editing safely.
- Save / Reload scene state with localStorage JSON persistence.
- Punch All physics interaction with progressive damage effects.
- Realistic low-volume procedural impact sounds (plastic / wood / metal).

### Export & Output

- 3D Export: STL (primary) and OBJ (secondary).
- High-resolution screenshot export (canvas only, no UI overlays).

### Responsive UI

- Mobile (≤768px), tablet (768–1024px), and desktop (≥1024px) friendly controls.
- Touch-friendly controls with ~44px minimum tap targets.
- Scroll-safe toolbars and no forced horizontal page scrolling.

### Onboarding

- First-load overlay explains the core interactions within seconds.
- Primary “Start Building” action is highlighted.

## 🛠️ Tech Stack

Core: React 18

3D Engine: Three.js

Renderer: React Three Fiber (@react-three/fiber)

Helpers: React Three Drei (OrbitControls, RoundedBox, Environment)

Styling: Tailwind CSS (via CDN)

## 📦 Quick Start

This project is designed as a Single File Application for maximum portability. You do not need npm install or a build step to run the production version.

### Option 1: Direct Play

Download index.html.

Open the file directly in any modern web browser (Chrome, Edge, Safari, Firefox).

### Option 2: Local Development

If you want to modify the code, run it through a local server.

Install a simple HTTP server (e.g., via Python or Node):

npx serve .


Open http://localhost:3000 in your browser.


### Browser Compatibility Note

The app now uses direct ESM CDN imports (instead of an import map) to improve GitHub Pages compatibility across browsers and stricter browser settings.

If the hosted page ever appears blank, do a hard refresh and check that your browser/network allows these CDNs:

- `esm.sh`
- `cdn.tailwindcss.com`
- `unpkg.com`

## 🎮 Controls

### Desktop (Mouse)

Left Click: Place Brick / Select UI

Right Click (Drag): Pan Camera

Left Click (Drag): Rotate Camera

Scroll: Zoom In/Out

### Mobile (Touch)

Tap: Place Brick

One Finger Drag: Rotate Camera

Two Finger Pinch: Zoom / Pan

## 📂 Data Structure

Builds are saved as a JSON array of brick objects:

[
  {
    "id": "uuid-string",
    "position": [0, 1, 0],
    "color": "#ef4444",
    "rotation": 0
  }
]


## 📄 License

Distributed under the MIT License. See LICENSE for more information.
