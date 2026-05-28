# Robust Multiscale Spectral-Spatial Regularized Sparse Unmixing for Hyperspectral Imagery

## Metadata

- **Year**: 2024
- **Venue**: IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing
- **Authors**: TBD
- **Paper**: https://doi.org/10.1109/JSTARS.2023.3337130
- **Code**: TBD
- **Project**: TBD
- **Local PDF**: ../pdfs/Robust Multiscale Spectral-Spatial Regularized Sparse Unmixing for Hyperspectral Imagery.pdf
- **Datasets**: Urban
- **Tags**: linear,blind,sparse,multiscale
- **Note status**: skimmed from the local PDF metadata and abstract

## Quick Reading

- **What it is about**: This paper studies sparse, multiscale for hyperspectral unmixing, centered on "Robust Multiscale Spectral-Spatial Regularized Sparse Unmixing for Hyperspectral Imagery".
- **Is it linear blind unmixing?** Yes. In this survey taxonomy it is treated as linear blind unmixing because it estimates endmembers and abundances from the HSI without supplied endmember spectra under a linear/reconstruction-based unmixing setup.
- **Datasets used**: Urban.
- **Experimental effect**: Evaluated on Urban with SAD/RMSE; exact result values are not yet extracted in this survey note.

## One-Sentence Summary

This skim note records a linear blind unmixing, sparse, multiscale paper and tracks its reported evaluation on Urban.

## Problem

The paper belongs to the linear blind hyperspectral unmixing track, where endmember spectra and abundance maps are estimated without supplied ground-truth endmembers. It is indexed here because it addresses one or more recurring HU issues such as spatial-spectral feature extraction, spectral variability, sparse or low-rank structure, deep autoencoding, Mamba/Transformer sequence modeling, or benchmark-oriented endmember/abundance estimation.

## Method

- Main idea: linear blind unmixing; sparse; multiscale.
- Model / optimization: see the local PDF for the full derivation; this skim note records the method family and reproducibility metadata first.
- Priors or assumptions: linear blind unmixing setting, usually with nonnegativity/sum-to-one abundance constraints or neural equivalents when specified by the paper.
- Training or inference details: not exhaustively extracted in this batch pass.

## Experiments

- Datasets: Urban
- Metrics: SAD; RMSE
- Code status: TBD; no official code URL was found in the local PDF or quick verification pass.
- Extraction note: The local PDF abstract and metadata were used for this skim note; no verbatim abstract is reproduced here.

## Strengths

- Adds a relevant linear blind HU method to the survey taxonomy.
- Useful for comparing method families within the same linear blind unmixing bucket.
- Keeps DOI, local PDF, note path, and code status in one place for later deep reading.

## Weaknesses / Questions

- This is a skim note; detailed equations, hyperparameters, and ablations still need manual reading.
- Code remains `TBD` unless an official URL was explicitly found and verified.
- Dataset/protocol fields may need refinement if the paper reports multiple synthetic and real settings.

## Relevance To My Work

- Use this entry when surveying linear blind HU baselines and recent neural/optimization variants.
- Prioritize for deeper reading if its method family matches the current project direction or if code is available.

## BibTeX

```bibtex
@article{robust_multiscale_spectral_spatial_regularized_sparse_unmixing_hyperspectral,
  title={Robust Multiscale Spectral-Spatial Regularized Sparse Unmixing for Hyperspectral Imagery},
  author={TBD},
  year={2024},
  doi={10.1109/JSTARS.2023.3337130}
}
```
