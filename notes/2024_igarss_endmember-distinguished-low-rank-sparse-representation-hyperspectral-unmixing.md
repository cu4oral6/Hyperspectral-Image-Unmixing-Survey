# Endmember Distinguished Low-Rank and Sparse Representation for Hyperspectral Unmixing

## Metadata

- **Year**: 2024
- **Venue**: IEEE IGARSS
- **Authors**: TBD
- **Paper**: https://doi.org/10.1109/IGARSS53475.2024.10641266
- **Code**: TBD
- **Project**: TBD
- **Local PDF**: ../pdfs/Endmember Distinguished Low-Rank and Sparse Representation for Hyperspectral Unmixing.pdf
- **Datasets**: USGS synthetic
- **Tags**: linear,blind,sparse,admm
- **Note status**: skimmed from the local PDF metadata and abstract

## Quick Reading

- **What it is about**: This paper studies sparse, ADMM, low-rank for hyperspectral unmixing, centered on "Endmember Distinguished Low-Rank and Sparse Representation for Hyperspectral Unmixing".
- **Is it linear blind unmixing?** Yes. In this survey taxonomy it is treated as linear blind unmixing because it estimates endmembers and abundances from the HSI without supplied endmember spectra under a linear/reconstruction-based unmixing setup.
- **Datasets used**: USGS synthetic.
- **Experimental effect**: On USGS synthetic, reports competitive or second-best performance against recent baselines (SAD/RMSE).

## One-Sentence Summary

This skim note records a linear blind unmixing, sparse, ADMM, low-rank paper and tracks its reported evaluation on USGS.

## Problem

The paper belongs to the linear blind hyperspectral unmixing track, where endmember spectra and abundance maps are estimated without supplied ground-truth endmembers. It is indexed here because it addresses one or more recurring HU issues such as spatial-spectral feature extraction, spectral variability, sparse or low-rank structure, deep autoencoding, Mamba/Transformer sequence modeling, or benchmark-oriented endmember/abundance estimation.

## Method

- Main idea: linear blind unmixing; sparse; ADMM; low-rank.
- Model / optimization: see the local PDF for the full derivation; this skim note records the method family and reproducibility metadata first.
- Priors or assumptions: linear blind unmixing setting, usually with nonnegativity/sum-to-one abundance constraints or neural equivalents when specified by the paper.
- Training or inference details: not exhaustively extracted in this batch pass.

## Experiments

- Datasets: USGS synthetic
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
@article{endmember_distinguished_low_rank_sparse_representation_hyperspectral_unmixing,
  title={Endmember Distinguished Low-Rank and Sparse Representation for Hyperspectral Unmixing},
  author={TBD},
  year={2024},
  doi={10.1109/IGARSS53475.2024.10641266}
}
```
