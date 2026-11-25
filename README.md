# Projectile Motion Lab

An interactive projectile motion simulator that runs in the browser. It was built with plain HTML, CSS and JavaScript, with no libraries or build step.

**Live demo:** `https://<your-username>.github.io/projectile-motion-lab/` (see "Publish it" below)

## What it does

- Sliders for launch speed, angle and height
- Choice of gravity: Earth, Moon, Mars or Jupiter
- Optional air resistance (quadratic drag) with adjustable mass and diameter
- Shows time of flight, range, maximum height and impact speed
- Compares the real path with the ideal path when drag is on
- Lets you keep several paths on one graph to compare them
- Works on phones and in light or dark mode

## The physics

Without air resistance:

```
x = v0 cos(θ) t
y = h0 + v0 sin(θ) t − ½ g t²
T = (v0 sin θ + √((v0 sin θ)² + 2 g h0)) / g
H = h0 + (v0 sin θ)² / (2g)
R = v0 cos θ · T
```

With air resistance, the drag force is F = ½ ρ Cd A v², so the acceleration is `a = −k |v| v − g ĵ` with `k = ρ Cd A / (2m)`. This has no simple closed-form solution, so it is solved numerically with the 4th-order Runge–Kutta method (time step 0.01 s). The simulator uses ρ = 1.225 kg/m³ and Cd = 0.47 (smooth sphere).

### Checks

For v0 = 30 m/s, θ = 45°, h0 = 0, g = 9.81 m/s², the formulas give T = 4.325 s, R = 91.74 m and H = 22.94 m. The numerical solver, run with almost zero drag, reproduces the same values.

## Run it

Open `index.html` in any browser. No install is needed.

## Publish it (GitHub Pages)

1. Create a new repository named `projectile-motion-lab` and upload `index.html` and `README.md`.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
4. After a minute, your site is live at `https://<your-username>.github.io/projectile-motion-lab/`.
5. Replace the demo link above with your real link.

## Ideas for extending it

- Add wind (a constant horizontal force)
- Let the user choose the shape (cube, cylinder) with different Cd values
- Export the path data as a CSV file
- Add a target and a "hit the target" game mode

## About

Made by [Your Name] for Engineering Physics / Engineering Mechanics, 1st year B.Tech.
