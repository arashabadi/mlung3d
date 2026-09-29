# Mouse Lung Explorer

Public, static 3D mouse-lung anatomical viewer. The [landing page](index.html) provides a direct download of [version 3.1](viewer/mouse_lung_v3.1.html), about 43 MiB. Open that downloaded HTML in a current browser; no installation or local server is needed. Three.js and the optional body OBJ still require internet access. The top-right camera icon downloads a transparent PNG. The record icon first opens a quality chooser: **Compact** (640 px, 12 fps, 6 s), **Clear** (960 px, 15 fps, 5 s), or **Slide** (1280 px, 20 fps, 4 s). The browser shows estimated temporary RAM before recording. Record and stop with the on-screen controls; GIF encoding runs on the visitor's CPU/GPU and is downloaded locally. Exports omit interface panels and retain a small live orientation compass and concise plane parameters when a plane is visible. PNG has full alpha; GIF permits only one-bit transparency. The separate E02 panel retains **Save ROI PNG**.

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

The repository root has a lightweight `index.html` and `.nojekyll`; the landing page sends visitors to download the full viewer once. GitHub Pages serves the static HTML bytes, but does not render 3D or encode GIFs. The full viewer is about 43 MiB per uncached download; GitHub currently documents a [100 GB/month soft bandwidth limit](https://docs.github.com/en/pages/getting-started-with-github-pages/github-pages-limits) and a 1 GB published-site size limit. The repository's tracked files are currently about 316 MiB. The download-first path limits repeat transfers but does not make bandwidth cost zero. To link it from `arashabadi.github.io` later, point a project card to the published `mouse-lung-explorer` Pages URL. No automatic deployment or site change is made here.

M07 plane addresses use its own millimeter coordinate frame. Right/ventral/cranial terminology follows the quadruped NAV framework advocated by [Ruberte et al. (2025)](https://doi.org/10.1007/s00335-025-10156-6); that paper does not measure M07 dimensions or register Xenium sections.
