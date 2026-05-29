# Conic Hull Fitting-Based Dictionary Matrix Learning for Nonnegative Matrix Factorization

## Metadata

- **Year**: 2026
- **Venue**: IEEE Transactions on Systems, Man, and Cybernetics: Systems
- **Authors**: Zhijie Lin; Zhaoshui He; Hao Liang; Wenqing Su; Beihai Tan; Ji Tan
- **Paper**: https://doi.org/10.1109/TSMC.2026.3655184
- **Code**: TBD
- **Project**: TBD
- **Local PDF**: ../pdfs/Conic Hull Fitting-Based Dictionary Matrix Learning for Nonnegative Matrix Factorization.pdf
- **Datasets**: synthetic; hyperspectral unmixing; facial parts learning
- **Tags**: linear, blind, NMF, conic hull, dictionary learning, separability
- **Note status**: skimmed from the local PDF

## One-Sentence Summary

This paper proposes conic-hull fitting NMF algorithms that relax strict separability and are tested on hyperspectral unmixing as a real-world NMF application.

## Problem

Many extreme-ray NMF methods rely on 1-sparse or separability assumptions that are often violated in realistic data, including mixed hyperspectral pixels.

## Method

- Recasts NMF geometrically as conic hull fitting in the positive orthant.
- Uses half-hyperplane identification rather than only extreme rays.
- Derives HICHF, EnhancedHICHF, and ExtendedHICHF algorithms with efficient EVD-based implementation.

## Experiments

Experiments cover synthetic nonseparable NMF and real parts-based learning tasks, including hyperspectral unmixing, with comparisons against state-of-the-art NMF methods.

## Strengths

- Useful bridge between convex geometry/NMF theory and HU.
- Explicitly targets nonseparable cases.
- Algorithmic design is relatively simple and interpretable.

## Weaknesses / Questions

- HU is one application rather than the only focus.
- No official code URL was found in the local PDF.
- Dataset and metric details should be checked before using it as a benchmark row.

## Relevance To My Work

Good theoretical background for NMF-based blind HU when pure-pixel assumptions are weak.

## BibTeX

```bibtex
@article{lin2026conic,
  title={Conic Hull Fitting-Based Dictionary Matrix Learning for Nonnegative Matrix Factorization},
  author={Zhijie Lin and Zhaoshui He and Hao Liang and Wenqing Su and Beihai Tan and Ji Tan},
  journal={IEEE Transactions on Systems, Man, and Cybernetics: Systems},
  year={2026},
  doi={10.1109/TSMC.2026.3655184}
}
```
