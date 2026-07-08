# Universe

A GPU-accelerated procedural starfield simulation rendered in WebGL2. Fly through an infinite, deterministic star field with gravitational lensing black holes, volumetric nebulae, and a procedural skybox.

## Features

- **Infinite starfield** — spatial hash generates deterministic star positions on the fly as you move through space. No geometry is stored; everything is computed per-frame.
- **Variable star brightness** — stars follow a realistic magnitude distribution with procedural spectral colors.
- **Black holes** — gravitational lensing distorts the star field around procedurally placed black holes.
- **Volumetric nebulae** — 3D Perlin noise clouds with dust absorption, distance fading, and per-nebula color palettes.
- **Procedural skybox** — faint galaxies, nebulae, and a milky way band rendered as a background layer.
- **Autopilot flight** — procedural joystick input via multi-octave noise with spring-damper trajectory tracking and coordinated roll banking.
- **Adjustable controls** — sliders for velocity, star count, brightness, fog, attitude, lag, black hole rate/size, plus toggle buttons for black holes and nebulae.
- **Persistent settings** — slider and button states are saved to localStorage and restored on reload.

## Running locally

This is a single-page static site. Serve it with any HTTP server:

```bash
# Python
python3 -m http.server 8000

# Node.js (npx, no install)
npx serve .

# PHP
php -S localhost:8000
```

Then open `http://localhost:8000` in a browser that supports WebGL2.

`index.html` redirects to `starfield.html`, which contains the entire application.

## Deployment

The project is deployed via AWS Amplify. `customHttp.yml` configures cache-busting headers so changes are reflected immediately.

## Controls

| Slider | Description |
|--------|-------------|
| Velocity | Flight speed through the starfield |
| Stars | Total number of stars rendered |
| Brightness | Overall star brightness and point size |
| Fog | Distance fog that fades stars at range |
| Attitude | Camera pitch/yaw/roll intensity during flight |
| Lag | How loosely the trajectory follows the camera heading |
| BH Rate | Black hole spawn frequency |
| BH Size | Einstein radius of black holes |

Toggle buttons enable/disable black holes and nebulae independently. A **Defaults** button resets all controls to their default values.

Click the (i) button next to any slider for a description.
