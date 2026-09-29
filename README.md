# Mouse Lung Explorer

Public, static 3D mouse-lung anatomical viewer. [Open version 3.1](viewer/mouse_lung_v3.1.html) or start from [the project landing page](index.html). The top-right camera icon downloads a transparent PNG; the record icon captures up to six seconds of user-controlled rotation as a compact GIF (640 px, approximately 12 frames/s). Click record again to stop early. Resume/pause rotation and cycle 1×, 1.5×, 2× speed with the adjacent icons. Exports contain the model, a small live orientation compass and concise plane parameters when a plane is visible; interface panels are omitted. PNG has full alpha; GIF permits only one-bit transparency. Browser-side encoding requires no server work on GitHub Pages; it does consume local CPU and memory. The separate E02 panel retains **Save ROI PNG**. The GIF encoder is vendored locally, while Three.js and the optional body OBJ still require network access.

The gross lung shape and airways are a published M07 anatomical reference. The E02 alveolar ROI is a separate public measured dataset and is not registered to M07. The whole-lung airspace overlay is schematic; its enlarged shapes, spacing and count are illustrative. [Detailed sources and methods](viewer/README.md).

## Versions

| Display version | Historical build filename | Interpretation |
|---|---|---|
| 2.5–2.7 | `viewer/archive/*v25*` through `*v27*` | Reference viewer lineage |
| 2.8 | `viewer/archive/mouse_lung_v28.html` | Independent ROI and readable plane IDs |
| 2.9 | `viewer/archive/mouse_lung_v29.html` | Schematic whole-lung toggle |
| 3.0 | `viewer/mouse_lung_v3.0.html` | Schematic 2D cuts, provenance labels and PNG export |
| 3.1 | `viewer/mouse_lung_v3.1.html` | Transparent PNG/GIF presentation exports, compact NAV-oriented plane controls |

The version numbers in historical filenames were `v25`–`v30`; the public display numbering is 2.5–3.1. `viewer/archive/mouse_lung_v30.html` preserves the exact pre-release HTML for provenance.

## Reproducibility

- `notebooks/16_lung_anatomical_frame_audit.ipynb`: M07 coordinate audit, section geometry and exploratory Xenium plane hypotheses. Xenium day 14/day 30 images are **optional external inputs**, not distributed here.
- `notebooks/17_alveolar_roi_and_viewer.ipynb`: independent E02 ROI reconstruction, viewer progression and 3.0 packaging. Earlier notebook cell outputs record executed local steps. The 3.0 packaging cell is executed after migration.
- `notebooks/18_viewer_presentation_exports.ipynb`: executed 3.0 → 3.1 UI and export derivation. The geometry is unchanged.
- `data/`: local raw and derived inputs, ignored by Git. See [SOURCES.md](SOURCES.md) for source IDs, attribution and download instructions; the local `data/README.md` is available only in the data-bearing checkout. Public HTML embeds the display geometry it needs; the raw data are for reproducing the build.
- `qa/`: small versioned checks and provenance.

The source notebooks assume their named Python packages and Node.js. They use paths relative to this repository. The source-to-geometry correspondence does **not** establish M07-specific alveoli, or registration of the Xenium day sections to the reference lung.

## GitHub Pages

The repository root has `index.html` and `.nojekyll`, so it is ready to serve as a static Pages site from the repository root when Pages is enabled. To link it from `arashabadi.github.io` later, point a project card to the published `mouse-lung-explorer` Pages URL. No automatic deployment or site change is made here.

M07 plane addresses use its own millimeter coordinate frame. Right/ventral/cranial terminology follows the quadruped NAV framework advocated by [Ruberte et al. (2025)](https://doi.org/10.1007/s00335-025-10156-6); that paper does not measure M07 dimensions or register Xenium sections.
