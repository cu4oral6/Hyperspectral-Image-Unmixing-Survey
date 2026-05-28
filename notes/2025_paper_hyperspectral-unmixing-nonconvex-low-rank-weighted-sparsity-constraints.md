# Hyperspectral Unmixing via Nonconvex Low-Rank and Weighted Sparsity Constraints

## Metadata

- **Year**: 2025
- **Venue**: TBD
- **Authors**: TBD
- **Paper**: https://doi.org/10.1109/ICVISP68610.2025.11451684
- **Code**: TBD
- **Project**: TBD
- **Local PDF**: ../pdfs/Hyperspectral Unmixing via Nonconvex Low-Rank and Weighted Sparsity Constraints.pdf
- **Datasets**: Jasper Ridge; USGS; synthetic
- **Tags**: linear,blind,sparse,admm
- **Note status**: skimmed from the local PDF metadata and abstract

## One-Sentence Summary

This skim note records a linear blind unmixing, sparse, ADMM, low-rank paper and tracks its reported evaluation on Jasper Ridge; USGS; synthetic.

## Problem

The paper belongs to the linear blind hyperspectral unmixing track, where endmember spectra and abundance maps are estimated without supplied ground-truth endmembers. It is indexed here because it addresses one or more recurring HU issues such as spatial-spectral feature extraction, spectral variability, sparse or low-rank structure, deep autoencoding, Mamba/Transformer sequence modeling, or benchmark-oriented endmember/abundance estimation.

## Method

- Main idea: linear blind unmixing; sparse; ADMM; low-rank.
- Model / optimization: see the local PDF for the full derivation; this skim note records the method family and reproducibility metadata first.
- Priors or assumptions: linear blind unmixing setting, usually with nonnegativity/sum-to-one abundance constraints or neural equivalents when specified by the paper.
- Training or inference details: not exhaustively extracted in this batch pass.

## Experiments

- Datasets: Jasper Ridge; USGS; synthetic
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
@article{hyperspectral_unmixing_nonconvex_low_rank_weighted_sparsity_constraints,
  title={Hyperspectral Unmixing via Nonconvex Low-Rank and Weighted Sparsity Constraints},
  author={TBD},
  year={2025},
  doi={10.1109/ICVISP68610.2025.11451684}
}
```
