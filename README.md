# Asteroids (Web)

A self-contained, single-file HTML5 Canvas clone of the classic arcade game **Asteroids**.
No build step, no dependencies — just open [`index.html`](index.html) in any modern browser.

## Play

Double-click `index.html`, or serve the folder and visit it in a browser.

**Controls**

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

## Running a local server (optional)

If you'd rather serve it over HTTP, a tiny dependency-free PowerShell server is included:

```powershell
powershell -ExecutionPolicy Bypass -File serve.ps1 -Port 8080
# then open http://localhost:8080/
```

Opening `index.html` directly from disk works just as well.

## About

Built as a from-scratch browser recreation of a Unity 2D Asteroids project, using
plain Canvas 2D and `requestAnimationFrame`. Everything lives in one file.
