# Mouse Lung Explorer

Public, static 3D mouse-lung anatomical viewer. [Open version 3.0](viewer/mouse_lung_v3.0.html) or start from [the project landing page](index.html). The viewer includes a **Save PNG** action for the whole-lung scene and the active 2D section, plus **Save ROI PNG** for the independent alveolar-region panel. Screenshots are saved by the browser, not sent to a server. A modern browser with network access is currently needed for Three.js and the optional body OBJ.

The gross lung shape and airways are a published M07 anatomical reference. The E02 alveolar ROI is a separate public measured dataset and is not registered to M07. The whole-lung airspace overlay is schematic; its enlarged shapes, spacing and count are illustrative. [Detailed sources and methods](viewer/README.md).

## Versions

| Display version | Historical build filename | Interpretation |
|---|---|---|
| 2.5–2.7 | `viewer/archive/*v25*` through `*v27*` | Reference viewer lineage |
| 2.8 | `viewer/archive/mouse_lung_v28.html` | Independent ROI and readable plane IDs |
| 2.9 | `viewer/archive/mouse_lung_v29.html` | Schematic whole-lung toggle |
| 3.0 | `viewer/mouse_lung_v3.0.html` | Schematic 2D cuts, provenance labels and PNG export |

The version numbers in historical filenames were `v25`–`v30`; the public display numbering is 2.5–3.0. `viewer/archive/mouse_lung_v30.html` preserves the exact pre-release HTML for provenance.

## Reproducibility

- `notebooks/16_lung_anatomical_frame_audit.ipynb`: M07 coordinate audit, section geometry and exploratory Xenium plane hypotheses. Xenium day 14/day 30 images are **optional external inputs**, not distributed here.
- `notebooks/17_alveolar_roi_and_viewer.ipynb`: independent E02 ROI reconstruction, viewer progression and 3.0 packaging. Earlier notebook cell outputs record executed local steps. The 3.0 packaging cell is executed after migration.
- `data/`: local raw and derived inputs, ignored by Git. See [SOURCES.md](SOURCES.md) for source IDs, attribution and download instructions; the local `data/README.md` is available only in the data-bearing checkout. Public HTML embeds the display geometry it needs; the raw data are for reproducing the build.
- `qa/`: small versioned checks and provenance.

The source notebooks assume their named Python packages and Node.js. They use paths relative to this repository. The source-to-geometry correspondence does **not** establish M07-specific alveoli, or registration of the Xenium day sections to the reference lung.

## GitHub Pages

The repository root has `index.html` and `.nojekyll`, so it is ready to serve as a static Pages site from the repository root when Pages is enabled. To link it from `arashabadi.github.io` later, point a project card to the published `mouse-lung-explorer` Pages URL. No automatic deployment or site change is made here.
