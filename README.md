# Box Shadow Invader

A single-div pixel art graphic that renders an animated space invader without images, extra markup, or script assets.

---

## Overview

Most web graphics rely on external PNGs, SVGs, or heavy HTML canvas setups to display retro sprites. This repository demonstrates how to draw and animate a complex 8-bit character using a single HTML element and CSS box-shadow coordinate mapping.

By chaining `steps()` animation timing functions with `currentColor` inheritance, the sprite toggles between active frames and shifts color palettes entirely within the render engine.

---

## How It Works

The entire sprite architecture rests on three core principles:

1. **Pixel Coordinate Mapping:** A single `10px x 10px` root element acts as the origin point. Every pixel in the 8-bit invader is drawn as an offset shadow relative to that origin.
2. **Keyframe Frame Swapping:** Instead of loading sprite sheets, two distinct `box-shadow` offset declarations swap instantly inside `@keyframes` using `steps(2)` to create rigid 8-bit motion.
3. **Palette Inheritance:** The box-shadows use `currentColor` as their fill value. Cycling the base element's CSS `color` property automatically updates every rendered shadow pixel across the board.

---

## Key Features

* Single-element DOM layout using `.invader`.
* Zero external asset dependencies or render-blocking scripts.
* Multi-layered keyframe animations combining frame swapping, floating translation, and dynamic color cycling.
* Built-in `.damaged` modifier class to demonstrate high-frequency flicker states.

---

## Tech Stack Breakdown

* **HTML5:** Semantic structure providing the base canvas wrapper.
* **CSS3:** Advanced `box-shadow` coordinate lists, custom keyframes, step-based timing functions, and CSS color variables.

---

## Web-Based Quick Start

You don't need to clone this locally or run a local dev server to inspect or modify the code.

### Option 1: GitHub Codespaces
1. Click the green **Code** button at the top right of this repository.
2. Select the **Codespaces** tab and click **Create codespace on main**.
3. Once the environment loads, install the "Live Preview" extension in VS Code web to view `index.html` live inside your browser.

### Option 2: GitHub Pages Deployment
1. Go to **Settings** > **Pages** in this repository.
2. Under **Build and deployment**, set the source to **Deploy from a branch**.
3. Select `main` branch and `/ (root)`, then click **Save**.
4. Access the live URL provided by GitHub in your browser.

---

## Repository Structure

```text
box-shadow-invader/
├── .github/
│   └── workflows/
│       └── static-lint.yml   # Lints markup and styling integrity on push
├── .gitignore                # OS and editor file exclusions
├── LICENSE                   # MIT License
├── README.md                 # Project documentation
├── index.html                # Canvas element and sprite mount point
└── style.css                 # Coordinate maps, animations, and color cycles
```

## Roadmap

[] Add optional UI controls to toggle the .damaged class state dynamically.

[] Expand coordinate mappings to include additional classic retro arcade sprites.

[] Expose coordinate offset arrays as native CSS custom properties for easier custom sprite creation.
