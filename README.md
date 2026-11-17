# ME4233 Lid-Driven Cavity Flow — Interactive Website

A single-page, static GitHub Pages website with an in-browser numerical demonstration of the vorticity–streamfunction cavity flow problem.

## Deploy on GitHub Pages
1. Create a new public GitHub repository.
2. Upload `index.html`, `style.css`, and `script.js` to its root (not inside a nested folder).
3. Open **Settings → Pages → Build and deployment**.
4. Set **Source: Deploy from a branch**, **Branch: main**, **Folder: / (root)**, then Save.
5. Wait for the published URL to appear in the Pages settings.

## Local preview
Open `index.html` in a browser, or run `python -m http.server 8000` from the folder and visit `http://localhost:8000`.

## Numerical notes
- Uses `field[i,j] = field(x_i,y_j)`; visualization maps x horizontally and y vertically.
- Uses second-order central spatial differences, lecture four-stage RK time integration, and GS-SOR for streamfunction.
- Second-order wall-vorticity formulas are applied between time steps. Velocity coefficients and wall values are held fixed during RK stages, so this segregated implementation does not guarantee fourth-order accuracy for the fully coupled nonlinear system.
- Browser grid choices are 21, 31, and 51 nodes per direction, not the full assignment's required 51 and 101 node study.
- No numerical results are fabricated; the browser calculates fields live. For final assignment conclusions, use validated Python outputs with grid/time-step sensitivity checks.
