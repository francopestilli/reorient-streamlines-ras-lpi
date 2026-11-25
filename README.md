# fix RAS/LPI labeling

<!-- brainlife-app:begin (generated from the App manifest; edit the manifest, not this block) -->

> **Fixes inconsistent RAS/LPI endpoint labels of left and right MDLFang, MDLFspl, Uncinate and Aslant ROIs by comparing ROI centroids along each tract's main axis and swapping file names when needed.**

For each listed tract, loads the left/right RAS and LPI endpoint ROIs, checks that left and right are in consistent coordinates, and swaps the RAS and LPI file names whenever the RAS ROI is not on the expected side along the tract's main orientation (z for MDLF and Aslant, y for Uncinate). Use it to make endpoint labels consistent across subjects before tract profile or endpoint analyses. It needs an ROIs dataset containing left/right RAS and LPI ROIs for all four tracts.

| | |
|---|---|
| 📥 **Inputs** | `neuro/rois` |
| 📤 **Outputs** | `neuro/rois` |
| 🐳 **Container** | `brainlife/pyafq:dev` |
| ⚙️ **Resources** | 4 CPUs · 28 GB memory · 10 h walltime |
| 🔗 **Run it** | [doi.org/10.25663/brainlife.app.795](https://doi.org/10.25663/brainlife.app.795) |

#### 📥 Inputs

| Input | Datatype | Required | Description |
|---|---|---|---|
| `rois` | `neuro/rois` | yes | ROIs directory with left and right RAS and LPI endpoint ROIs per tract. Must contain left/right *RAS* and *LPI* NIfTI ROIs for MDLFang, MDLFspl, Uncinate and Aslant. |

#### 📤 Outputs

| Output | Datatype | Description |
|---|---|---|
| `rois_relabeled` | `neuro/rois` | Same ROIs with the RAS/LPI labels corrected where they were swapped. |

<!-- brainlife-app:end -->

