# Mouse Lung Explorer

Public, static 3D mouse-lung anatomical viewer. The [project URL](index.html) opens the interactive Lite viewer directly; download [version 3.2](viewer/mlung3d_v3.2_full.html), about 43 MiB. Open that downloaded HTML in a current browser; no installation or local server is needed. Three.js and the optional body OBJ still require internet access. The top-right camera icon offers a dark 3200 × 1800 figure PNG by default or a transparent 2200-pixel PNG. Both carry the version and a small source credit. The GIF icon defaults to Slide (1280 × 720, 20 fps) with a dark background; a video icon records a 16:9 supplementary movie as browser-native H.264 MP4 when available, otherwise WebM. Recording ends when the same icon is clicked again. With Clip active, exports show the 3D model beside its 2D mesh section, the larger anatomical orientation compass, and the M07-local plane equation. Encoding occurs in the visitor's browser. The separate E02 panel retains **Save ROI PNG**.

The gross lung shape and airways are a published M07 anatomical reference. The E02 alveolar ROI is a separate public measured dataset and is not registered to M07. The whole-lung airspace overlay is schematic; its enlarged shapes, spacing and count are illustrative. [Detailed sources and methods](viewer/README.md).

## Versions

| Display version | Historical build filename | Interpretation |
|---|---|---|
| 2.5–2.7 | `viewer/archive/*v25*` through `*v27*` | Reference viewer lineage |
| 2.8 | `viewer/archive/mouse_lung_v28.html` | Independent ROI and readable plane IDs |
| 2.9 | `viewer/archive/mouse_lung_v29.html` | Schematic whole-lung toggle |
| 3.0 | `viewer/archive/mouse_lung_v3.0.html` | Schematic 2D cuts, provenance labels and PNG export |
| 3.1 | Git history | Presentation exports and compact plane controls |
| 3.2 | `viewer/mlung3d_v3.2_full.html` | Direct Lite entry, full-resolution download and publication exports |

The version numbers in historical filenames were `v25`–`v30`; the public display numbering is 2.5–3.2. `viewer/archive/mouse_lung_v30.html` preserves the exact pre-release HTML for provenance.

## Reproducibility

- `notebooks/16_lung_anatomical_frame_audit.ipynb`: M07 coordinate audit, section geometry and exploratory Xenium plane hypotheses. Xenium day 14/day 30 images are **optional external inputs**, not distributed here.
- `notebooks/17_alveolar_roi_and_viewer.ipynb`: independent E02 ROI reconstruction, viewer progression and 3.0 packaging. Earlier notebook cell outputs record executed local steps. The 3.0 packaging cell is executed after migration.
- `notebooks/18_viewer_presentation_exports.ipynb`: executed 3.0 → 3.1 UI and export derivation. The geometry is unchanged.
- `data/`: local raw and derived inputs, ignored by Git. See [SOURCES.md](SOURCES.md) for source IDs, attribution and download instructions; the local `data/README.md` is available only in the data-bearing checkout. Public HTML embeds the display geometry it needs; the raw data are for reproducing the build.
- `qa/`: small versioned checks and provenance.

The source notebooks assume their named Python packages and Node.js. They use paths relative to this repository. The source-to-geometry correspondence does **not** establish M07-specific alveoli, or registration of the Xenium day sections to the reference lung.

## GitHub Pages

The repository root redirects immediately to the interactive Lite viewer. Full HTML is downloadable from within Lite. GitHub Pages serves the static HTML bytes, but does not render 3D or encode GIFs. The full viewer is about 43 MiB per uncached download; GitHub currently documents a [100 GB/month soft bandwidth limit](https://docs.github.com/en/pages/getting-started-with-github-pages/github-pages-limits) and a 1 GB published-site size limit. The repository's tracked files are currently about 316 MiB. The Lite-first path reduces the initial transfer, but Full downloads still use bandwidth. The personal site links to this public viewer.

M07 plane addresses use its own millimeter coordinate frame. Right/ventral/cranial terminology follows the quadruped NAV framework advocated by [Ruberte et al. (2025)](https://doi.org/10.1007/s00335-025-10156-6); that paper does not measure M07 dimensions or register Xenium sections.

## Lightweight public preview

The [interactive Lite preview](viewer/mlung3d_v3.2_lite.html) is derived by [notebook 19](notebooks/19_public_light_viewer.ipynb) from the full M07 viewer. It clusters surface vertices on a 0.08 mm grid, reducing the page from 42.8 MiB to about 18.1 MiB and gross mesh triangles from 3.94 million to 0.74 million. Rotation, plane positioning, and the independent E02 ROI remain interactive. Lite retains interactive 3D clipping, but its 2D section panel is hidden because vertex clustering does not preserve reliable closed contours. Download and open the Full HTML locally for 2D sections, detailed anatomical interpretation, and every PNG/GIF/video export. Lite replaces capture controls with a full-viewer download prompt. Both builds render in the visitor’s browser; only the locally opened Full HTML enables PNG/GIF/video encoding. Static hosting only serves files.
