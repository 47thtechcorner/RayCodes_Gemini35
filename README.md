Codes for my Youtube Video [I Tested Gemini 3.5 Flash in Antigravity 2.0 and Couldn't Believe the Results](https://youtu.be/yoa4opGsvP4)

# Neon Pong - Player vs AI Web Game

A high-fidelity, single-player, dark-mode "Neon Pong" game built in a single HTML5 file. It features customizable AI tiers, retro synthesized sound effects, fluid ball trails, and particle hit sparkles. 

The game runs entirely on the client-side with zero external assets, databases, or runtime server dependencies. It can be run offline directly from the file system or via a simple local HTTP server.

---

## Tech Stack
- **Orchestration**: Antigravity (Advanced Agentic Coding Environment)
- **Model**: Gemini 3.5 Flash
- **Graphics**: HTML5 Canvas API (Dynamic rendering, particles, and glows)
- **Sound**: Web Audio API (Synthesized oscillators for retro-arcade sound events)
- **Styling**: CSS3 (Glassmorphism layout, scanlines, floating blur background blobs)
- **Programming Language**: Vanilla JavaScript (ES6+)

---

## Setup & Run Steps

Since this project has no backend network dependencies, you have two simple ways to run it on Windows:

### Method A: Single-Click Offline Run (Easiest)
1. Navigate to the folder containing `index.html`.
2. Double-click `index.html`.
3. It will open instantly in your default web browser (Chrome, Edge, Firefox, etc.).

### Method B: Local HTTP Server (PowerShell)
To serve it over a local network port:
1. Open **Windows PowerShell** and navigate to your workspace directory:
   ```powershell
   cd "d:\Ray Codes\AG Projects\Gemini 3.5"
   ```
2. Start the HTTP server:
   - **If you have Python installed**:
     ```powershell
     python -m http.server 8000
     ```
   - **If you have Node.js installed**:
     ```powershell
     npx http-server -p 8000
     ```
3. Open your browser and navigate to: `http://localhost:8000`

---

## Test & Play Guide

1. **Launch Menu**: On load, choose an AI Difficulty Level:
   - **EASY (Tier 1)**: Relaxed tracking speed, high error rate, and reaction delays.
   - **MEDIUM (Tier 2)**: Balanced tracking speed and moderate tracking precision.
   - **HARD (Tier 3)**: Fast tracking speed and minimal tracking offsets.
   - **INSANE (Tier Max)**: Hyper-fast tracking speed, real-time recalculations, and perfect tracking.
2. **Start the Game**: Click the glowing **"LAUNCH GAME"** button.
3. **Controls**:
   - Move the Left Paddle (Cyan) using **W** and **S** keys, or the **Arrow Up** and **Arrow Down** keys.
   - Alternatively, on mobile devices or touch screens, drag your finger vertically on the left half of the screen.
4. **Gameplay Flow**:
   - Paddle hits trigger high-frequency synth hit tones and Cyan/Magenta particle explosions.
   - Scoring points triggers screen-border flashes, scoring sweeps, and celebration particle fountains.
   - First to **7 points** wins the match and unlocks the custom victory/defeat sweep.

---

## Code Architecture Explanation

- **UI Layout & Glassmorphism CSS**: Sets up custom neon variables, animated background blur blobs, and scanline shaders. Leverages backdrop filters to create a glossy retro container.
- **Audio Synthesizer (`AudioEngine`)**: Uses the browser's native `AudioContext` and oscillator nodes to programmatically synthesize sound effects (hit tone ramps, low bounce vibrations, score chirps, and game over arpeggios).
- **AI Engine (`updateAI`)**: Regulates the right paddle. Uses difficulty multipliers to constraint maximum speed, reaction ticks (how often it updates target vectors), and randomized tracking offsets.
- **Physics Engine (`updatePhysics`)**: Resolves ball movement vectors, boundaries, paddle bounding-box overlap collision, spin math (modifying vertical velocity depending on where the ball strikes the paddle), and score bounds.

---

## Copy-Pasteable Generation Prompt

To recreate this game from scratch in any agentic coding assistant, copy and paste the following prompt:

```text
Act as the Antigravity Agent Manager. I need you to build a dark-mode "Neon Pong" game in a single self-contained HTML file. 

Specifically, design:
1. UI/UX: HTML layout and Vanilla CSS styling for a futuristic, cyber-themed glassmorphism panel. Background must feature deep purple gradients, floating animated glow blobs, and scanline overlays. 
2. Start Menu: Add a title "NEON PONG" with a glowing text animation, a difficulty selector (EASY, MEDIUM, HARD, INSANE), and a "LAUNCH GAME" button.
3. Game Screen: Include a score counter (PLAYER vs COMPUTER), a responsive HTML5 Canvas container, and a return/quit controls button.
4. Game Logic & Physics: Implement the Canvas rendering loop. Create paddle boundary-clamping, ball physics, speed increments on hit, and spin mechanics (adjusting ball exit angle depending on where it strikes the paddle).
5. AI Controller: Implement the right paddle to track the ball's Y-coordinate. Limit the AI's speed, tracking accuracy, and update frequency based on the selected difficulty.
6. Visual Effects: Add a glowing tail trailing the ball, color-coded particle explosions on paddle bounces, and screen-border flashes when a point is scored.
7. Sound Effects: Programmatically synthesize retro sound effects (no external audio assets!) using the Web Audio API (oscillators for hits, bounces, scoring, victory, and defeat).

Combine everything into exactly ONE file: index.html. Keep code clean, avoid bloated architecture, and ensure the game is immediately runnable directly from the file system.
```

---

## Future Feature Ideas
- **Power-Up Orbs**: Floating icons that temporarily shrink the AI paddle or trigger double-size balls.
- **Dynamic Arena Modifiers**: Obstacles spawning in the middle of the field causing unpredictable bounces.
- **Local Co-op Mode**: A 2-player keyboard mode where Player 1 uses W/S and Player 2 uses Arrow Up/Down.
- **Custom Visual Themes**: Theme selector options to change colors to Green, Orange, or Red.
- **Visual Statistics**: Post-match summary showing maximum volley length, average ball velocity, and paddle contact points.
