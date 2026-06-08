# 🦕 DinoRun

A polished, production-ready Chrome Dino-inspired endless runner built with **pure HTML, CSS, and JavaScript** — no frameworks, no external dependencies.

---

## 🎮 How to Play

| Control         | Action           |
|-----------------|------------------|
| `SPACE` / `↑`   | Jump             |
| `↑` (airborne)  | Double Jump      |
| `↓`             | Duck             |
| `R`             | Restart (after game over) |
| **Tap**         | Jump (mobile)    |
| **Swipe down**  | Duck (mobile)    |

**Objective:** Survive as long as possible, avoiding cacti and flying birds. The game speeds up over time!

---

## ✨ Features

- **Smooth 60 FPS** gameplay via `requestAnimationFrame`
- **Single / Double jump** — tap again mid-air for extra height
- **Duck** to avoid high-flying birds
- **3 cactus variants** — single, double, triple trunk
- **3 bird height levels** — forcing different evasion strategies
- **Day / Night cycle** — transitions every 700 points with sound
- **Procedural sound effects** — Web Audio API, zero audio files
- **Particle effects** — dust on landing, explosion on death
- **Scrolling ground** with surface detail
- **Animated dino** — running legs, blinking eye, tail
- **Animated birds** — flapping wings
- **Score counter** with milestone flash every 100 points
- **High score** persisted via `localStorage`
- **Mute button** to silence all audio
- **Start screen** and **Game Over screen** with score board
- **Day/Night mode** on `<body>` and canvas via CSS variables
- **Responsive design** — scales to any viewport
- **Mobile touch support**

---

## 📁 Folder Structure

```
project/
│
├── index.html   ← HTML shell, overlay screens, HUD
├── style.css    ← All visual styling (day/night, animations, UI)
├── game.js      ← Full game engine (OOP, ~600 lines)
└── README.md    ← This file
```

---

## 🚀 Running Locally

Just open `index.html` in any modern browser:

```bash
# Option 1 — double-click index.html in your file explorer

# Option 2 — serve with Python
python3 -m http.server 8080
# then open http://localhost:8080

# Option 3 — serve with Node.js npx
npx serve .
```

No build step, no npm install, no configuration required.

---

## ☁️ Deploying to GitHub Pages

### Step 1 — Create a GitHub repository

Go to [github.com/new](https://github.com/new) and create a new **public** repository (e.g. `dinorun`).

### Step 2 — Push the code

Run these commands from inside the `project/` folder:

```bash
git init
git add .
git commit -m "Initial commit — DinoRun"
git branch -M main
git remote add origin https://github.com/<YOUR_USERNAME>/dinorun.git
git push -u origin main
```

Replace `<YOUR_USERNAME>` with your GitHub username.

### Step 3 — Enable GitHub Pages

1. Open your repository on GitHub.
2. Go to **Settings → Pages** (left sidebar).
3. Under **Source**, select **Deploy from a branch**.
4. Set the branch to `main` and folder to `/ (root)`.
5. Click **Save**.

GitHub will show you a URL like `https://<YOUR_USERNAME>.github.io/dinorun/` — it will be live within ~60 seconds.

---

## 🏗 Architecture

The entire game is implemented as a set of ES6 classes:

| Class             | Responsibility                                       |
|-------------------|------------------------------------------------------|
| `AudioManager`    | Web Audio API sound synthesis                        |
| `InputManager`    | Keyboard & touch event handling                      |
| `Renderer`        | Canvas 2D context wrapper + theme colours            |
| `Dino`            | Player physics, animation, hitbox                    |
| `Obstacle`        | Abstract base class for obstacles                    |
| `Cactus`          | Ground obstacle (3 variants)                         |
| `Bird`            | Flying obstacle (3 heights, animated wings)          |
| `Ground`          | Scrolling ground strip with parallax surface detail  |
| `ParticleSystem`  | Dust puffs and death explosions                      |
| `Game`            | Main controller — game loop, state machine, scoring  |

### Game Loop

```
requestAnimationFrame → update(dt) → draw()
  update:
    speed += increment * dt         (ramp difficulty)
    score += speed * dt * 0.015     (distance-based scoring)
    ground.update(dt, speed)        (scroll ground)
    dino.update(dt)                 (physics + animation)
    obstacles[].update(dt, speed)   (move + cull)
    checkCollision(dino, obstacles) (AABB)
    particles.update(dt)
  draw:
    clear canvas
    ground.draw()
    particles.draw()
    obstacles[].draw()
    dino.draw()
```

---

## 🛠 Browser Compatibility

| Browser         | Status  |
|-----------------|---------|
| Chrome 80+      | ✅ Full  |
| Firefox 75+     | ✅ Full  |
| Safari 13+      | ✅ Full  |
| Edge 80+        | ✅ Full  |
| iOS Safari 13+  | ✅ Full  |
| Android Chrome  | ✅ Full  |

Requires: `Canvas 2D API`, `Web Audio API`, `requestAnimationFrame`, `localStorage`.

---

## 📄 License

MIT — free to use, modify, and distribute.
