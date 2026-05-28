# Stationary Wavelet Convolutional Network With Generative Feature Learning for Hyperspectral Unmixing

## Metadata

- **Year**: 2025
- **Venue**: IEEE Transactions on Geoscience and Remote Sensing
- **Authors**: TBD
- **Paper**: https://doi.org/10.1109/TGRS.2024.3516114
- **Code**: https://github.com/UPCGIT/SWC-Net
- **Project**: TBD
- **Local PDF**: ../pdfs/Stationary Wavelet Convolutional Network With Generative Feature Learning for Hyperspectral Unmixing.pdf
- **Datasets**: synthetic
- **Tags**: linear,blind,graph
- **Note status**: skimmed from the local PDF metadata and abstract

## Quick Reading

- **What it is about**: This paper studies graph for hyperspectral unmixing, centered on "Stationary Wavelet Convolutional Network With Generative Feature Learning for Hyperspectral Unmixing".
- **Is it linear blind unmixing?** Yes. In this survey taxonomy it is treated as linear blind unmixing because it estimates endmembers and abundances from the HSI without supplied endmember spectra under a linear/reconstruction-based unmixing setup.
- **Datasets used**: synthetic.
- **Experimental effect**: On synthetic, the paper reports RMSE 35.3 and compares against recent HU baselines.

## One-Sentence Summary

This skim note records a linear blind unmixing, graph paper and tracks its reported evaluation on synthetic.

## Problem

The paper belongs to the linear blind hyperspectral unmixing track, where endmember spectra and abundance maps are estimated without supplied ground-truth endmembers. It is indexed here because it addresses one or more recurring HU issues such as spatial-spectral feature extraction, spectral variability, sparse or low-rank structure, deep autoencoding, Mamba/Transformer sequence modeling, or benchmark-oriented endmember/abundance estimation.

## Method

- Main idea: linear blind unmixing; graph.
- Model / optimization: see the local PDF for the full derivation; this skim note records the method family and reproducibility metadata first.
- Priors or assumptions: linear blind unmixing setting, usually with nonnegativity/sum-to-one abundance constraints or neural equivalents when specified by the paper.
- Training or inference details: not exhaustively extracted in this batch pass.

## Experiments

- Datasets: synthetic
- Metrics: SAD; RMSE
- Code status: Verified official code/project URL from the local PDF or official page.
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
@article{stationary_wavelet_convolutional_network_generative_feature_learning_hyperspectral,
  title={Stationary Wavelet Convolutional Network With Generative Feature Learning for Hyperspectral Unmixing},
  author={TBD},
  year={2025},
  doi={10.1109/TGRS.2024.3516114}
}
```
