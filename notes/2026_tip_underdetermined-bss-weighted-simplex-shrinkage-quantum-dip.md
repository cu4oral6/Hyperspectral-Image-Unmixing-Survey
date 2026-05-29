# Underdetermined Blind Source Separation via Weighted Simplex Shrinkage Regularization and Quantum Deep Image Prior

## Metadata

- **Year**: 2026
- **Venue**: IEEE Transactions on Image Processing
- **Authors**: Chia-Hsiang Lin; Si-Sheng Young
- **Paper**: https://doi.org/10.1109/TIP.2026.3673957
- **Code**: TBD
- **Project**: TBD
- **Local PDF**: ../pdfs/Underdetermined Blind Source Separation via Weighted Simplex Shrinkage Regularization and Quantum Deep Image Prior.pdf
- **Datasets**: synthetic; real MSI/HSI datasets
- **Tags**: mixed, blind, multispectral unmixing, deep image prior, quantum, simplex
- **Note status**: skimmed from the local PDF

## One-Sentence Summary

GQ-mu tackles underdetermined multispectral unmixing by using a quantum deep image prior to create virtual HSI bands and weighted simplex shrinkage to regularize blind source separation.

## Problem

Multispectral unmixing is underdetermined when the number of sources exceeds the number of observed bands, making blind source separation harder than standard HU.

## Method

- Uses quantum deep image prior for virtual band splitting, turning MSI into a virtual HSI.
- Performs HU on the virtual HSI to recover virtual hyperspectral sources.
- Applies weighted simplex shrinkage regularization based on abundance sparsity to mitigate ill-posedness.

## Experiments

Simulation and real-world experiments evaluate source recovery and abundance maps, reporting practical performance for challenging multispectral unmixing.

## Strengths

- Directly addresses underdetermined MSI/MU rather than standard overdetermined HU.
- Combines geometric simplex regularization with deep image prior.
- Potentially relevant to low-band or sensor-limited unmixing.

## Weaknesses / Questions

- The quantum DIP component may be harder to reproduce and interpret.
- No official code URL was found in the local PDF.
- It spans MSI and HU, so taxonomy is mixed rather than pure HU.

## Relevance To My Work

Useful for thinking about underdetermined or multispectral unmixing when few bands are available.

## BibTeX

```bibtex
@article{lin2026gqmu,
  title={Underdetermined Blind Source Separation via Weighted Simplex Shrinkage Regularization and Quantum Deep Image Prior},
  author={Chia-Hsiang Lin and Si-Sheng Young},
  journal={IEEE Transactions on Image Processing},
  year={2026},
  doi={10.1109/TIP.2026.3673957}
}
```
