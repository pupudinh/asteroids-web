# Asteroids (Web)

**▶ [Play it live](https://pupudinh.github.io/asteroids-web/)** — a self-contained, single-file HTML5 Canvas clone of the classic arcade game. No build step, no dependencies.

![Asteroids gameplay](demo.gif)

## Controls

| Key | Action |
|-----|--------|
| `W` / `↑` | Thrust |
| `A` `D` / `←` `→` | Turn |
| `Space` / click | Fire |
| `Enter` / click | Restart (on Game Over) |

## Gameplay

- Momentum-based ship — you thrust and drift with inertia.
- Asteroids split when shot: large → two medium → two small → gone.
- Scoring rewards precision: small = 60, medium = 40, large = 20.
- 3 lives; respawn with brief invulnerability (the ship blinks green).
- Everything wraps around the screen edges.

## Run it locally

Just open [`index.html`](index.html) in any modern browser — it runs straight from `file://`.

Or serve it over HTTP with the included dependency-free PowerShell server (no Python/Node needed):

```powershell
powershell -ExecutionPolicy Bypass -File serve.ps1 -Port 8080
# then open http://localhost:8080/
```

## How it works

Everything lives in one file: Canvas 2D rendering driven by `requestAnimationFrame`,
a fixed-step game loop, circle-based collision detection, and screen-wrapping physics.
Built as a from-scratch browser recreation of a Unity 2D Asteroids project.
