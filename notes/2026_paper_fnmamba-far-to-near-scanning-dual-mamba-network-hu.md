# FNMamba: A Far-to-Near Scanning Dual Mamba Network for Hyperspectral Image Unmixing

## Metadata

- **Year**: 2026
- **Venue**: TBD
- **Authors**: Lin Qi; Yili Zeng; Ying Sun; Feng Gao; Junyu Dong
- **Paper**: TBD
- **Code**: TBD
- **Project**: TBD
- **Local PDF**: ../pdfs/FNMamba__A_Far_to_Near_Scanning_Dual_Mamba_Network_for_Hyperspectral_Image_Unmixing.pdf
- **Datasets**: Jasper Ridge; Samson
- **Tags**: linear, blind, Mamba, state-space-model, autoencoder, spatial-spectral, Jasper-Ridge, Samson

## Quick Reading

- **What it is about**: FNMamba is a dual-branch Mamba unmixing network that combines far-to-near spatial scanning with grouped spectral sequence modeling for abundance and endmember estimation.
- **Is it linear blind unmixing?** Yes. It estimates endmembers and abundances directly from the HSI and uses an autoencoder-style linear decoder/endmember matrix, so this survey classifies it as linear blind unmixing.
- **Datasets used**: Jasper Ridge and Samson.
- **Experimental effect**: It reports the best mean SAD on Jasper Ridge and the best mean SAD/RMSE on Samson among the compared baselines. On Jasper Ridge, TANet still has the lower mean RMSE in the same comparison table.

## One-Sentence Summary

FNMamba adapts Mamba to blind hyperspectral unmixing by scanning spatial tokens from far to near and modeling grouped spectral dependencies before reconstructing pixels through a learned endmember matrix.

## Problem

Recent deep blind unmixing methods often use convolution, attention, or transformer modules to combine spatial and spectral information. These modules can be expensive or may not match the geometry of hyperspectral patches and spectral sequences. The paper argues that Mamba/state-space modeling is attractive because it can capture long-range dependencies with linear complexity, but the scan order needs to be designed for unmixing rather than copied directly from generic vision tasks.

## Method

- Main architecture: an autoencoder-like network with a spatial Mamba branch, a spectral Mamba branch, an abundance head, and a linear decoder whose weights act as the endmember matrix.
- Far-to-near spatial Mamba (FNSM): arranges spatial patch tokens so that distant contextual information is scanned before nearer tokens around the target pixel, aiming to inject broader spatial context while preserving local abundance structure.
- Grouped spectral Mamba module (GSMM): splits spectral bands into groups and applies sequence modeling to learn both local spectral continuity and broader band dependencies.
- Training strategy: includes reconstruction loss and sparsity-style regularization; the paper also reports that the two-stage training design is important for stable abundance RMSE.

## Experiments

- Datasets: Jasper Ridge and Samson.
- Metrics: SAD for endmember estimation and RMSE for abundance estimation. The paper tables report values in units of x10^-2; the benchmark CSV stores decimal values.
- Baselines: VCA, l1/2-NMF, EndNet, CNN-AEU, TANet, A2SAN, and DPCM-HAEM.
- Jasper Ridge: 100 x 100 pixels, 198 bands after removing water/atmospheric bands, 4 endmembers (tree, water, soil, road). FNMamba reports mean SAD 0.0340 and mean RMSE 0.0807. It is best in mean SAD and best on tree/water RMSE, while TANet has a lower mean RMSE of 0.0754.
- Samson: 95 x 95 pixels, 156 bands from 401-889 nm, 3 endmembers (soil, tree, water). FNMamba reports mean SAD 0.0207 and mean RMSE 0.0502, both best in the extracted comparison table.

## Strengths

- The scan design is task-aware: spatial ordering and spectral grouping are both motivated by the structure of HSI unmixing rather than generic image classification.
- Results on Samson are strong and consistent across both SAD and RMSE.
- The ablation suggests that the two-stage training, sparse regularization, spatial neighborhood size, and spectral grouping all matter to final performance.

## Weaknesses / Questions

- Venue, DOI, official paper URL, and code link are not verified from the local PDF or public search.
- Experiments are limited to two classic small real datasets; there is no Urban, Cuprite, APEX, or large agricultural scene in the current extracted version.
- Jasper Ridge RMSE is not the best overall despite the paper's strong SAD result, so claims should separate endmember and abundance performance.
- The method depends on several architectural and training choices, and reproducibility is hard to judge without code.

## Relevance To My Work

- Useful for comparing recent Mamba-based linear blind HU methods such as UNMamba, SUMamba, FACM, ProMU, and Mamba-enhanced spatial-spectral models.
- The far-to-near spatial scan is a concrete design idea for patch-level abundance estimation and could be tested against center-first spiral, raster, Hilbert, or learned ordering strategies.
- The grouped spectral Mamba module is relevant if the goal is to reduce transformer cost while still modeling long-range spectral dependency.

## BibTeX

```bibtex
@article{qi2026fnmamba,
  title={FNMamba: A Far-to-Near Scanning Dual Mamba Network for Hyperspectral Image Unmixing},
  author={Qi, Lin and Zeng, Yili and Sun, Ying and Gao, Feng and Dong, Junyu},
  year={2026},
  note={Venue and DOI not verified}
}
```
