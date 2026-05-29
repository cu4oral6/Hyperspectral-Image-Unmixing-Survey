# Hyperspectral Sparse Unmixing via Joint Robust Spatial Priors and Weighted Total Variation Regularization

## Metadata

- **Year**: 2026
- **Venue**: IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing
- **Authors**: Fan Li; Xiyu Chen; Shaoquan Zhang; Jiaqiang Zhou; Huasheng Zhu; Yuyang Liu; Hongyu Zhang; Chengzhi Deng; Shengqian Wang
- **Paper**: https://doi.org/10.1109/JSTARS.2026.3668120
- **Code**: TBD
- **Project**: TBD
- **Local PDF**: ../pdfs/Hyperspectral Sparse Unmixing via Joint Robust Spatial Priors and Weighted Total Variation Regularization.pdf
- **Datasets**: synthetic; real HSI datasets
- **Tags**: linear, semi-supervised, sparse, total variation, spatial priors, robust
- **Note status**: skimmed from the local PDF

## One-Sentence Summary

RSPWTV improves sparse HU by combining robust spatial priors with adaptive weighted total variation to preserve edges while suppressing noise and outliers.

## Problem

Sparse unmixing benefits from spectral libraries, but abundance maps can lose detail under outliers and complex noise when spatial regularization is too weak or too uniform.

## Method

- Starts from a robust sparse unmixing framework.
- Builds adaptive weighted TV using spectral angular similarity and spatial proximity.
- Combines weighted TV with additional robust spatial priors to smooth homogeneous areas while protecting edges.

## Experiments

The paper reports synthetic and real HSI evaluations with standard sparse HU metrics such as SAD, RMSE, and SRE against sparse unmixing baselines.

## Strengths

- Good fit for spectral-library sparse HU.
- Weighted TV is designed to be edge-aware rather than globally uniform.
- Targets robustness to mixed noise and outliers.

## Weaknesses / Questions

- Depends on the quality and relevance of the spectral library.
- No official code URL was found in the local PDF.
- Exact benchmark values should be checked visually before citation.

## Relevance To My Work

Useful when comparing spatially regularized sparse unmixing methods under noise.

## BibTeX

```bibtex
@article{li2026rspwtv,
  title={Hyperspectral Sparse Unmixing via Joint Robust Spatial Priors and Weighted Total Variation Regularization},
  author={Fan Li and Xiyu Chen and Shaoquan Zhang and Jiaqiang Zhou and Huasheng Zhu and Yuyang Liu and Hongyu Zhang and Chengzhi Deng and Shengqian Wang},
  journal={IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing},
  year={2026},
  doi={10.1109/JSTARS.2026.3668120}
}
```
