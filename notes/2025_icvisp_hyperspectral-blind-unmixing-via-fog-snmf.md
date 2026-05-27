# Hyperspectral Blind Unmixing via First-Order Graph-Guided Sparse Nonnegative Matrix Factorization

## Metadata

- **Year**: 2025
- **Venue**: 9th International Conference on Vision, Image and Signal Processing (ICVISP)
- **Authors**: Xinyi Zhou; Shaoquan Zhang; Mengxiong Tang; Jiaqiang Zhou; Ye Wu; Fan Li; Chengzhi Deng
- **Paper**: https://doi.org/10.1109/ICVISP68610.2025.11451711
- **Code**: TBD
- **Local PDF**: ../pdfs/Hyperspectral_Blind_Unmixing_via_First-Order_Graph-Guided_Sparse_Nonnegative_Matrix_Factorization.pdf
- **Datasets**: USGS synthetic data; Samson
- **Tags**: nmf, sparse, graph, spatial-spectral, blind, Samson

## One-Sentence Summary

Proposes FoG-SNMF, a sparse NMF blind unmixing model that adds first-order graph-difference spatial regularization and dual weighting to improve abundance and endmember estimation.

## Problem

Standard NMF-based blind unmixing uses nonnegativity and sparsity but can underuse spatial topology in hyperspectral images. The paper targets better spatial-context modeling while preserving sparsity and smoothness.

## Method

- Starts from linear mixing model and sparse NMF.
- Constructs first-order graph difference operators to capture spatial topological relationships.
- Adds a spatial-structure regularization term and dual weighted sparse regularization.
- Optimizes endmember matrix and abundance matrix under nonnegativity and sum-to-one constraints.

## Experiments

- Synthetic experiment uses the USGS spectral library with 224 bands, 75 x 75 pixels, 5 endmembers, and additive white noise at 10, 20, and 30 dB.
- Real experiment uses Samson with 95 x 95 pixels, 156 bands, and 3 endmembers: rock, tree, water.
- Metrics: SAD for endmembers and RMSE for abundances.
- Reported Samson result for FoG-SNMF: mean SAD 0.0506 and RMSE 0.2270.
- Baselines include GLNMF, l1/2-NMF, TV-RSNMF, SSWNMF, and SLRTF.

## Strengths

- Clear classical optimization baseline for spatially constrained blind unmixing.
- Includes both synthetic and real-data experiments.
- Gives concrete SAD/RMSE tables that are useful for benchmark tracking.

## Weaknesses / Questions

- Need to verify whether code is available.
- Conference paper is short; implementation and convergence details may be limited.
- The method is designed around linear mixing and may not address nonlinear mixtures or spectral variability.

## Relevance To My Work

- Useful as a spatial-graph sparse NMF baseline.
- Good benchmark entry for Samson and synthetic USGS experiments.

## BibTeX

```bibtex
@inproceedings{zhou2025hyperspectral,
  title={Hyperspectral Blind Unmixing via First-Order Graph-Guided Sparse Nonnegative Matrix Factorization},
  author={Zhou, Xinyi and Zhang, Shaoquan and Tang, Mengxiong and Zhou, Jiaqiang and Wu, Ye and Li, Fan and Deng, Chengzhi},
  booktitle={9th International Conference on Vision, Image and Signal Processing (ICVISP)},
  year={2025},
  doi={10.1109/ICVISP68610.2025.11451711}
}
```

