# Viewer and source categories

Open `mouse_lung_v3.1.html` directly or through the repository landing page. The camera icon exports a transparent 3D PNG; the record icon exports a six-second, 640 px, approximately 12 fps GIF. Stop recording early with a second click. Both exclude the control panels and retain the live compass plus a short plane readout when relevant. GIF transparency is one bit per pixel; PNG supports full alpha. **Save ROI PNG** remains available in the independent ROI dialog. All capture and GIF encoding run in the browser and do not use a server-side API.

1. **M07 reference:** published lapdMouse M07 gross lung/airway geometry ([source](https://cebs-ext.niehs.nih.gov/cahs/report/lapd/m07); Bauer et al. 2020, DOI 10.1152/japplphysiol.00615.2019). The original m07 labelmap is kept locally in ignored `data/m07/`. Its five-lobe geometry is not an alveolar atlas.
2. **E02 measured-data ROI:** an independently reconstructed 160×160×96 ROI sampled at 2.2 µm after detector binning, from [Lovric et al.](https://doi.org/10.7910/DVN/XO8FQY) projection data. The thresholded bright-tissue interface is exploratory. It is **not** individually segmented alveoli and is not registered to M07. The paper DOI is 10.1371/journal.pone.0183979.
3. **Schematic whole-lung airspaces:** enlarged 0.40 mm polyhedra with 0.65 mm display spacing generated inside all five lobe meshes. Their size, placement and number are arbitrary design parameters, **not measured anatomy**. When enabled, the 2D panel intersects these identical geometric shapes. Do not use them for morphometry.
4. **Xenium day 14/day 30 planes:** exploratory shape candidates in notebook 16, without specimen-specific 3D registration. No candidate is an established anatomical plane.

The viewer uses Three.js 0.180 from a CDN. The optional CT-style body model is loaded at runtime from [MAMMAL_mouse](https://github.com/anl13/MAMMAL_mouse). This component’s separate upstream terms should be checked before redistributing its OBJ. All displayed source and method categories remain visible inside the app.

The current HTML is self-contained for the gross lung and E02 display geometry. Some network access remains necessary for its JavaScript modules and optional body model. `archive/` contains the original historical HTML snapshots.

5. **Anatomical terminology:** [Ruberte et al. (2025)](https://doi.org/10.1007/s00335-025-10156-6) supports the quadruped NAV directional language shown on the compass and plane controls. It supplies neither M07-specific lengths nor a Xenium registration. The M07 plane address remains local to the archived M07 geometry.

The browser-side GIF encoder is [gifenc 1.0.3](https://github.com/mattdesl/gifenc), © 2017 Matt DesLauriers, MIT license in `assets/LICENSE.gifenc.md`. Its vendored build source is `assets/gifenc.esm.js`; notebook 18 embeds the encoder into the distributable HTML so GIF recording does not fetch a sibling module from `file://`.
