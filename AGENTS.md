# AGENTS.md

Asteroids clone — HTML5 Canvas + vanilla ES6+ JavaScript. No frameworks, no bundler, no dependencies, no `package.json`. There is nothing to install, build, lint, or test; all verification is manual in a browser.

## Run

Open `index.html` directly in a browser, or:

```bash
npx serve .   # → http://localhost:3000
```

## Architecture

- All game logic lives in `game.js` — a single classic `<script>` (no ES modules, no `import`/`export`, no build step). Classes: `Ship`, `Asteroid`, `Bullet`, `Particle`.
- Game state machine: `state` is `'playing' | 'dead' | 'gameover'` (see `update()`).
- Entities follow the `dead` flag + `filter()` removal pattern; asteroid sizes 1–3 are indexed via the parallel `RADII` / `SPEEDS` / `POINTS` arrays.

## Gotchas

- **Canvas size is duplicated**: `index.html` (`canvas width/height` attributes) and `game.js` (`W` / `H` constants, 800×600) must be kept in sync. The toroidal `wrap()` movement depends on `W`/`H`.
- **Input edge detection**: `pressed(code)` consumes `justPressed` — it must be called exactly once per frame per key, or key presses get lost.
- **dt is clamped** to 0.05 s in `loop()`; all physics are dt-based, so don't assume fixed frame steps.
- **README is partly aspirational**: it mentions power-ups and a "estrella fugaz" (shooting star) that do NOT exist in `game.js`. Trust the code over the README.

## Conventions

- UI strings and docs are in Spanish (`es`) — keep new HUD/overlay text in Spanish.
- Style: single quotes, semicolons, section banner comments (`// ── Name ──`) inside `game.js`.
