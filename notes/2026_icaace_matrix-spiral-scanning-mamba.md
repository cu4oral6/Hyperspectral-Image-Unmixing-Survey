# A Hyperspectral Unmixing Method Based on Matrix Spiral Scanning Mamba

## Metadata

- **Year**: 2026
- **Venue**: 2026 9th International Conference on Advanced Algorithms and Control Engineering (ICAACE)
- **Authors**: Haoyan Deng
- **Paper**: https://doi.org/10.1109/ICAACE69793.2026.11508730
- **Code**: TBD
- **Project**: TBD
- **Local PDF**: ../pdfs/A Hyperspectral Unmixing Method Based on Matrix Spiral Scanning Mamba.pdf
- **Datasets**: Jasper Ridge
- **Tags**: linear, blind, Mamba, state-space-model, spiral-scanning, spectral-spatial, Jasper-Ridge

## Quick Reading

- **What it is about**: SUMamba adapts Mamba to hyperspectral unmixing by scanning local spatial patches in a center-focused spiral order and pairing this with bidirectional spectral SSM modeling.
- **Is it linear blind unmixing?** Yes. In this survey taxonomy it is treated as linear blind unmixing because it estimates endmembers and abundances from the HSI without supplied endmember spectra under a linear/reconstruction-based unmixing setup.
- **Datasets used**: Jasper Ridge.
- **Experimental effect**: Jasper Ridge: Mean SAD 0.046 +/- 0.0018; RMSE 0.061 +/- 0.0032; best in the extracted table.

## One-Sentence Summary

SUMamba adapts Mamba to hyperspectral unmixing by scanning local spatial patches in a center-focused spiral order and pairing this with bidirectional spectral SSM modeling.

## Problem

Mamba is attractive for hyperspectral unmixing because state space models can capture long-range dependencies with linear computational complexity. However, standard unidirectional, bidirectional, cross-scan, or multi-directional scanning strategies are not designed around the central pixel in a hyperspectral patch. This can weaken the modeled relationship between a target mixed pixel and its neighbors, which matters directly for abundance-map continuity and endmember consistency.

## Method

- Main idea: construct a matrix spiral scanning sequence centered on the target pixel, so the spatial SSM emphasizes the target pixel and its surrounding pixels before fusing opposite scan directions.
- Spatial branch: reduces feature dimensionality, applies linear projection, depthwise separable convolution, SiLU activation, and a Spatial SSM (Spa-SSM) using bidirectional matrix spiral scanning, followed by feature fusion and layer normalization.
- Spectral branch: proposes a spectral abundance extraction module (SpeAEM) with a skip path and a main spectral SSM path. Spectral bands are grouped, then bidirectional scanning models continuous-band correlations and more separated discriminative spectral cues.
- Losses: combines reconstruction MSE and spectral angular distance (SAD), plus an endmember-mean MSE constraint that pulls the learned endmember matrix toward the global mean spectral distribution.

## Experiments

- Datasets: Jasper Ridge
- Baselines: uDAS, DAEU, SIDAEU, CyCU-Net, MTAEU, UST-Net, A2SAN, and UNMamba.
- Metrics: endmember SAD and abundance RMSE.
- Key results: SUMamba reports the best overall values in the extracted table, with Mean SAD 0.046 +/- 0.0018 and RMSE 0.061 +/- 0.0032 on Jasper Ridge. Per-endmember SAD values are 0.056 for soil, 0.050 for tree, 0.031 for water, and 0.046 for road.

## Strengths

- The spiral scan is well aligned with the unmixing setting because the central pixel is the prediction target and its local neighborhood supports spatial abundance consistency.
- Mamba/SSM gives a plausible route to long-range spectral-spatial modeling without the quadratic cost of transformer attention.
- Directly compares with a recent Mamba baseline, UNMamba, and reports lower Mean SAD and RMSE on Jasper Ridge.

## Weaknesses / Questions

- The abstract claims experiments on four benchmark datasets, but the extracted body text and tables show only Jasper Ridge.
- The paper is short and does not provide detailed ablation results for the spiral scan, spectral scan, and endmember-mean loss separately.
- No official code link is reported in the paper.
- The method is categorized here as linear blind unmixing because the loss and comparisons follow the common reconstruction-based unmixing setup, but the paper does not spell out all physical constraints in detail.

## Relevance To My Work

- Useful as a compact example of adapting Mamba scanning order to the geometry of hyperspectral unmixing rather than reusing generic vision scans.
- Good comparison point for other 2025-2026 Mamba-based HU methods such as UNMamba, Efficient Progressive Mamba, and frequency-adaptive convolutional Mamba.
- The center-pixel spiral idea is relevant for designing spatial modules that preserve abundance-map locality.

## BibTeX

```bibtex
@inproceedings{deng2026hyperspectral,
  title={A Hyperspectral Unmixing Method Based on Matrix Spiral Scanning Mamba},
  author={Deng, Haoyan},
  booktitle={2026 9th International Conference on Advanced Algorithms and Control Engineering (ICAACE)},
  year={2026},
  doi={10.1109/ICAACE69793.2026.11508730}
}
```
