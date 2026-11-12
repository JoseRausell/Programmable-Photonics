# Programmable Photonics · Interactive Lab

Interactive, purely theoretical simulations of the devices and circuits used in programmable photonics.
Everything is computed in the browser from analytical / transfer-matrix models, for teaching purposes.
Open `index.html` in any modern browser (double-click). No internet connection or server is needed.

## Structure

```
index.html          Landing page: introduction, key concepts and component catalogue
components/
  mzi.html          MZI / tunable basic unit (TBU) and thermo-optic phase shifter
  ring.html         Single-bus ring / racetrack: coupling regimes, Q, backscattering splitting, thermal tuning
  adddrop.html      Add-drop ring / racetrack: through & drop, critical coupling, backscattering (reflection + add port), thermal tuning
  ps.html           Thermo-optic phase shifter: 2D heat conduction (method of images), Pπ, trenches, thermal crosstalk, time response
  dc.html           Directional coupler: coupled-mode theory vs gap, length, wavelength, asymmetry, tolerance
  mmi.html          MMI 1×2 / 2×2: self-imaging by modal propagation analysis, imbalance, phase, equivalent MZI error
  ff.html           Feed-forward meshes: theory view + Reck / Clements simulators (decomposition, programming, hand editing, fidelity, Monte Carlo)
```

Each simulation is a single self-contained HTML file (3D view, plots and model, no external libraries).
Every page has a "← Component catalog" link back to `index.html`.

## Adding a new component

1. Create `components/<name>.html` (copy an existing one as a template). Add the back link inside `<header>`:
   `<a class="back" href="../index.html">← Component catalog</a>`
2. In `index.html`, find the `COMPONENTS` list and add or edit an entry:
   ```js
   { id: 'adddrop', name: 'Add-drop ring', category: 'Resonators', status: 'available',
     href: 'components/adddrop.html', icon: 'adddrop', tags: ['drop port', 'filter'],
     summary: 'Short description shown on the card.' }
   ```
   - `status`: `'available'` (the card becomes a link to `href`) or `'soon'` (greyed out).
   - `category`: any text; filter chips are generated automatically from the categories.
   - `icon`: key of an illustration in the `ICONS` object (inline SVG). Add a new one there if needed.

## Planned components

Hexagonal recirculating mesh.
