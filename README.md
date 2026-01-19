# ⚡ Multiverse Breach: Dimension Runner

![Version](https://img.shields.io/badge/version-1.0.0-blue) ![License](https://img.shields.io/badge/license-MIT-green) ![Status](https://img.shields.io/badge/status-prototype-orange)
![Tech Stack](https://img.shields.io/badge/Three.js-WebGL-black) ![Platform](https://img.shields.io/badge/platform-Mobile%20%7C%20Web-lightgrey)

> **"When two universes collide, the only way out is forward."**

**Multiverse Breach** is a high-performance, browser-based 3D infinite runner built with **Three.js** and **WebGL**. Designed for mobile-first interactivity, it features a custom physics engine, dynamic environmental theming, and optimized touch-gesture controls.

---

## 📖 Table of Contents

- [About the Project](#-about-the-project)
- [Key Features](#-key-features)
- [Technical Architecture](#-technical-architecture)
- [Installation & Usage](#-installation--usage)
- [Controls](#-controls)
- [Future Roadmap (AI Integration)](#-future-roadmap)
- [License & Disclaimer](#-license--disclaimer)

---

## 🪐 About the Project

This project explores the intersection of **Web Graphics Library (WebGL)** and **Game Theory**. The goal was to create a seamless 3D experience that runs at 60 FPS on mobile devices without external app installation.

The game simulates a "Universe Merge" event where the player must navigate a quantum tunnel. The environment dynamically shifts between two distinct visual styles:
* **The Gotham Protocol:** Dark, brooding atmospherics with high contrast (DC Style).
* **The Stark Initiative:** High-tech, saturated visuals with neon accents (Marvel Style).

---

## 🌟 Key Features

### 1. Zero-Dependency Rendering
* Built using a single HTML5 structure injecting **Three.js** via CDN.
* No heavy game engines (Unity/Unreal) required—pure JavaScript logic.

### 2. Mobile-Optimized Physics
* **Touch Input System:** Custom event listeners (`touchstart`, `touchmove`, `touchend`) calculate swipe vectors to determine intent (Jump vs. Dodge).
* **Smooth Interpolation:** Utilizes Linear Interpolation (**Lerp**) for lane switching, preventing "jittery" movement and ensuring fluid visual transitions.

### 3. Progressive Difficulty Algorithm
* The game does not use hard-coded levels. Instead, it utilizes a mathematical function to increase the `gameSpeed` variable relative to the `score` and `deltaTime`, ensuring an infinite scaling difficulty curve.

---

## ⚙️ Technical Architecture

### The Core Loop
The game operates on a `requestAnimationFrame` loop to maintain sync with the device's refresh rate.

function animate() {
    // 1. Calculate Delta Time
    // 2. Update Physics (Gravity & Velocity)
    // 3. Render Scene
    requestAnimationFrame(animate);
}

Collision Detection (AABB)
Instead of expensive mesh-based colliders, I implemented a lightweight Axis-Aligned Bounding Box (AABB) logic for performance efficiency:
Dynamic Memory Management
To prevent memory leaks in the browser:
 * Obstacles are instantiated and pushed to an array.
 * Once an obstacle passes the camera frustum (z > 5), it is removed from the scene and spliced from the array, keeping the DOM footprint minimal.
   
💻 Installation & Usage

Since this is a client-side web application, no build tools (Webpack/Vite) are strictly necessary for the prototype.
Option 1: Direct Play
 * Download index.html.
 * Open it in any modern browser (Chrome/Safari/Edge).
Option 2: Local Server (Recommended for Assets)
If you expand the game to use texture images, you will need a local server to avoid CORS errors.
# Clone the repo
git clone [https://github.com/yourusername/multiverse-breach.git](https://github.com/yourusername/multiverse-breach.git)

# Enter directory
cd multiverse-breach

# Run Python simple server
python -m http.server 8000

Then navigate to localhost:8000 in your browser.

🎮 Controls

The input system detects the device type and adjusts accordingly.

🔮 Future Roadmap

This project is a foundation for my research into Generative AI in Gaming.
 * [ ] GenAI Textures: Integration of Stable Diffusion API to generate unique obstacle textures in real-time based on the "Universe" selected.
 * [ ] Reinforcement Learning Agent: Training a PPO (Proximal Policy Optimization) agent to play the game and identify "impossible" obstacle patterns.
 * [ ] Backend Integration: Connecting to a Flask/Django backend to store high scores and user metrics.

Disclaimer: This project is a fan creation for educational purposes. "Iron Man", "Batman", and related characters are trademarks of Marvel Characters, Inc. and DC Comics respectively. No copyright infringement is intended.


Developed by Syed Ismail Nasser
Student @ IIIT Bangalore

