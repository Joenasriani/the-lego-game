BrickBuilder 3D - XR Edition

A high-fidelity, mobile-first 3D building sandbox inspired by LEGO. Built with React Three Fiber, this application features physically based rendering (PBR), a fully immersive WebXR (VR/AR) mode for Meta Quest, and a robust save/load system.

🚀 Features

Core Mechanics

Modular Building: Snap-to-grid system with collision detection and "Ghost Brick" previews.

PBR Rendering: Realistic plastic materials with accurate Index of Refraction (IOR), roughness, and clearcoat.

Save & Load: Persist builds via Local Storage or export/import JSON files to share creations.

Undo/Redo System: Full history stack for worry-free experimentation.

Procedural Audio: Satisfying click and pop sound effects generated via Web Audio API (no assets to load).

Screenshot Mode: High-resolution capture of your builds without UI clutter.

XR / VR Support (Meta Quest Optimized)

Immersive Mode: Full WebXR support. Clicking "Enter VR" transports you into the scene.

Floating Dashboard: A 3D holographic menu palette that floats in front of the user in VR.

Ergonomics: The board automatically adjusts height and distance for comfortable standing or seated play.

Controller Support: Full 6DoF controller tracking for precise brick placement.

Mobile & Desktop Responsive

Touch Controls: Optimized OrbitControls for pinch-to-zoom and touch-to-rotate.

Responsive UI: HUD elements adapt to screen size, ensuring thumb-reachability on mobile devices.

🛠️ Tech Stack

Core: React 18

3D Engine: Three.js

Renderer: React Three Fiber (@react-three/fiber)

Helpers: React Three Drei (OrbitControls, RoundedBox, Environment)

XR/VR: React Three XR (@react-three/xr)

Styling: Tailwind CSS (via CDN)

Icons: Lucide React

📦 Quick Start

This project is designed as a Single File Application for maximum portability. You do not need npm install or a build step to run the production version.

Option 1: Direct Play

Download index.html.

Open the file directly in any modern web browser (Chrome, Edge, Safari, Firefox).

To enable VR, open the hosted link in the Meta Quest Browser.

Option 2: Local Development

If you want to modify the code, it is recommended to run it through a local server to avoid CORS issues with textures or WebXR.

Install a simple HTTP server (e.g., via Python or Node):

npx serve .


Open http://localhost:3000 in your browser.

🎮 Controls

Desktop (Mouse)

Left Click: Place Brick / Select UI

Right Click (Drag): Pan Camera

Left Click (Drag): Rotate Camera

Scroll: Zoom In/Out

Mobile (Touch)

Tap: Place Brick

One Finger Drag: Rotate Camera

Two Finger Pinch: Zoom / Pan

VR (Meta Quest)

Point & Trigger: Interact with the floating UI dashboard.

Controller Ray: Point at the grid to see the Ghost Brick.

Trigger: Place brick.

Grip/B Button: Delete mode (configurable via dashboard).

📂 Data Structure

Builds are saved as a JSON array of brick objects:

[
  {
    "id": "uuid-string",
    "position": [0, 1, 0],
    "color": "#ef4444",
    "rotation": 0
  }
]


📄 License

Distributed under the MIT License. See LICENSE for more information.
