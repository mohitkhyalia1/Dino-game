# 🦕 DinoRun — Cinematic Edition

A feature-rich, browser-based endless runner game built entirely in a single HTML file — no frameworks, no dependencies, no install required.

![HTML5](https://img.shields.io/badge/HTML5-Canvas-orange?style=flat-square&logo=html5)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-yellow?style=flat-square&logo=javascript)
![No Dependencies](https://img.shields.io/badge/Dependencies-None-brightgreen?style=flat-square)
![Single File](https://img.shields.io/badge/Single-File-blue?style=flat-square)

---

## 🎮 Play It

Just open **`DinoRun_v3.html`** in any modern browser — that's it.

> No server needed. No install. No build step. Double-click and run.

---

## ✨ Features

### 🎬 Cinematic Presentation
- Animated intro screen with procedural starfield, nebula wisps, and firework particles
- Cinematic letterbox bars that retract when the game begins
- Vignette overlay and motion-blur effects at high speed
- Smooth slow-motion death sequence

### 🌅 Dynamic Day/Night Cycle
A full **6-phase sky system** that evolves as your score climbs:

| Phase | Sky |
|-------|-----|
| Dawn | Deep purple → orange horizon |
| Morning | Blue sky with warm light |
| Noon | Bright cyan, high sun |
| Evening | Golden hour tones |
| Sunset | Red/amber sky |
| Night | Dark starfield with moon |

Shadow direction and length update dynamically with the sun's position across the sky.

### 🌦️ Live Weather System
Five weather states cycle randomly during gameplay:
- **Clear** — standard visibility
- **Mist** — ground-level fog wisps
- **Rain** — angled rainfall with streaks
- **Dust** — wind-blown particle clouds
- **Storm** — heavy rain + lightning flash overlays

### 🏔️ Parallax 2.5D World
- Multiple scrolling layers: far mountains, mid ridges, near terrain, trees, clouds
- Fractal-subdivided mountain silhouettes for a natural look
- Volumetric cloud rendering
- Ground-level pebbles and surface detail

### 🎵 Procedural Audio
All sound is synthesized live via the **Web Audio API** — no audio files needed:
- Jump, double-jump, duck, and land sounds
- Ambient wind (scales with game speed)
- Milestone chime on every 100 points
- Game-over fanfare
- Day/night transition tone

### 🦕 Dino Mechanics
- **Jump** — launch off the ground
- **Double Jump** — second jump mid-air
- **Duck / Fast-fall** — crouch under birds or slam back down
- Smooth squash-and-stretch animation on land
- Idle breathing animation on the start screen

### 🌵 Obstacles
- Procedurally generated cacti (single, double, triple clusters)
- Flying pterodactyls at varying heights (unlocked after score 500)
- Spacing and speed both scale with your score

### ⚡ Escalating Difficulty
Speed ramps from **340 px/s** at start up to **1150 px/s** at the cap, with a visible speed-up flash and score pulse every milestone.

### 📊 Score & Persistence
- Live score and personal best displayed in the HUD
- High score saved to **localStorage** — survives page reloads
- New best highlighted in gold on the game-over card

### 📱 Mobile & Fullscreen Support
- Fully touch-controlled (tap to jump, swipe down to duck)
- Fullscreen button + keyboard shortcut (`F`)
- Portrait-mode warning with animated rotate prompt on mobile
- Orientation lock to landscape when entering fullscreen

---

## 🕹️ Controls

| Action | Keyboard | Mouse | Touch |
|--------|----------|-------|-------|
| Jump | `Space` / `↑` | Left Click | Tap |
| Double Jump | `↑` (mid-air) | Left Click (mid-air) | Tap (mid-air) |
| Duck / Fast-fall | `↓` | Right Click | Swipe Down |
| Restart | `R` | — | — |
| Fullscreen | `F` | Fullscreen button | Fullscreen button |

---

## 📁 Repository Structure

```
dinorun/
├── DinoRun_v3.html   # The entire game — HTML, CSS, and JS in one file
└── README.md
```

---

## 🏗️ Technical Overview

The game is built with vanilla JavaScript and the HTML5 Canvas API, structured around these core classes:

| Class | Responsibility |
|-------|---------------|
| `Game` | Main loop, state machine (idle → running → dead) |
| `Dino` | Player physics, animation, collision |
| `Ground` | Scrolling terrain and surface detail |
| `Background` | Parallax layers, sky, stars, mountains, clouds |
| `DayNight` | 6-phase sky color blending |
| `Weather` | Rain, mist, dust, storm simulation |
| `ObstacleManager` | Cactus and bird spawning/pooling |
| `Audio2` | Web Audio API sound synthesis |
| `Input` | Unified keyboard, mouse, and touch handler |
| `IntroEngine` | Animated title screen (separate canvas) |

No external libraries or frameworks. The Google Fonts CDN is the only network request (`Cinzel Decorative` + `Rajdhani`).

---

## 🌐 Browser Compatibility

Works in all modern browsers that support the Canvas API and Web Audio API:

| Browser | Support |
|---------|---------|
| Chrome / Edge | ✅ Full |
| Firefox | ✅ Full |
| Safari (macOS) | ✅ Full |
| Safari (iOS 15+) | ✅ Full |
| Samsung Internet | ✅ Full |

---

## 🚀 Getting Started

```bash
# Clone the repo
git clone https://github.com/your-username/dinorun.git

# Open the game
open DinoRun_v3.html   # macOS
start DinoRun_v3.html  # Windows
xdg-open DinoRun_v3.html  # Linux
```

Or just drag the file into your browser.

---

## 📜 License

This project is released under the [MIT License](https://opensource.org/licenses/MIT). Feel free to fork, modify, and share.

---

<p align="center">Made with ❤️ and a single HTML file</p>
