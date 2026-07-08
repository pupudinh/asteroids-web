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
a game loop, circle-based collision detection (squared-distance, no `sqrt`), and
screen-wrapping physics. The canvas backing store is scaled by `devicePixelRatio`
for crisp rendering on HiDPI displays, and all tunables live in one `CONFIG` object.
Built as a from-scratch browser recreation of a Unity 2D Asteroids project.

## Known limitations / future work

Deliberately out of scope for this single-file build — each is a clean next step:

- **Desktop keyboard only.** No touch controls, so mobile is view-only for now.
- **Fixed 900×640 playfield.** Scales down to fit small screens but isn't fully responsive.
- **Brute-force collision.** `O(bullets × asteroids)` per frame with no spatial partitioning —
  fine at the current object counts, but a spatial grid would be the fix at scale.
- **No object pooling.** Bullets and particles are allocated per use; pooling would cut
  garbage-collection churn if object counts grew large.
