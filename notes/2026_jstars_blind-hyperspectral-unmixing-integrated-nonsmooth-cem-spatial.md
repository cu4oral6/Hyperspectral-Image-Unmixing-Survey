# Blind Hyperspectral Unmixing With Integrated Nonsmooth and CEM Spatial Constraints

## Metadata

- **Year**: 2026
- **Venue**: IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing
- **Authors**: Shaoquan Zhang; Kexing Li; Xinyi Zhou; Fan Li; Pengfei Lai; Lianhui Liang; Chengzhi Deng; Shengqian Wang
- **Paper**: https://doi.org/10.1109/JSTARS.2026.3678308
- **Code**: TBD
- **Project**: TBD
- **Local PDF**: ../pdfs/Blind Hyperspectral Unmixing With Integrated Nonsmooth and CEM Spatial Constraints.pdf
- **Datasets**: synthetic; real HSI datasets
- **Tags**: linear, blind, NMF, CEM, spatial regularization, sparse, noise robust
- **Note status**: skimmed from the local PDF

## One-Sentence Summary

EISNMF improves blind linear HU by adding endmember nonsmoothness and CEM-guided spatial sparse abundance regularization to an l1-NMF framework.

## Problem

Noise and outliers can distort both endmember spectra and abundance maps in blind HU, especially when standard NMF models lack spatial continuity or target-aware sparse constraints.

## Method

- Adds a nonsmooth matrix in the l1-NMF formulation to encourage sparse and smooth endmember estimates under noise.
- Builds a dual-weight sparse abundance regularizer from a CEM detector and spatial weights.
- Uses the combined model to strengthen abundance sparsity while preserving local spatial continuity.

## Experiments

The paper evaluates synthetic and real hyperspectral scenes with SAD/RMSE-style HU metrics and reports better robustness under noise than compared blind unmixing methods.

## Strengths

- Clear model-based extension of NMF rather than another black-box AE.
- CEM weighting gives the spatial regularizer a target-aware interpretation.
- Useful for noisy blind HU comparisons.

## Weaknesses / Questions

- No official code URL was found in the local PDF.
- Exact table values still need visual checking if used as benchmark numbers.
- The method remains tied to linear blind HU assumptions.

## Relevance To My Work

Use it as a recent model-based NMF baseline for robust blind unmixing under noise.

## BibTeX

```bibtex
@article{zhang2026eisnmf,
  title={Blind Hyperspectral Unmixing With Integrated Nonsmooth and CEM Spatial Constraints},
  author={Shaoquan Zhang and Kexing Li and Xinyi Zhou and Fan Li and Pengfei Lai and Lianhui Liang and Chengzhi Deng and Shengqian Wang},
  journal={IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing},
  year={2026},
  doi={10.1109/JSTARS.2026.3678308}
}
```
