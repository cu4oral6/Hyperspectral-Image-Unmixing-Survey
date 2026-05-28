# Unmixing Before Fusion: A Generalized Paradigm for Multi-Source-Based Hyperspectral Image Synthesis

## Metadata

- **Year**: 2024
- **Venue**: IEEE/CVF Conference on Computer Vision and Pattern Recognition
- **Authors**: TBD
- **Paper**: https://doi.org/10.1109/CVPR52733.2024.00888
- **Code**: https://hsi-synthesis.github.io/
- **Project**: https://hsi-synthesis.github.io/
- **Local PDF**: ../pdfs/Unmixing Before Fusion A Generalized Paradigm for Multi-Source-Based Hyperspectral Image Synthesis.pdf
- **Datasets**: synthetic
- **Tags**: linear,blind
- **Note status**: skimmed from the local PDF metadata and abstract

## One-Sentence Summary

This skim note records a linear blind unmixing paper and tracks its reported evaluation on synthetic.

## Problem

The paper belongs to the linear blind hyperspectral unmixing track, where endmember spectra and abundance maps are estimated without supplied ground-truth endmembers. It is indexed here because it addresses one or more recurring HU issues such as spatial-spectral feature extraction, spectral variability, sparse or low-rank structure, deep autoencoding, Mamba/Transformer sequence modeling, or benchmark-oriented endmember/abundance estimation.

## Method

- Main idea: linear blind unmixing.
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
@article{unmixing_before_fusion_generalized_paradigm_multi_source_hyperspectral,
  title={Unmixing Before Fusion: A Generalized Paradigm for Multi-Source-Based Hyperspectral Image Synthesis},
  author={TBD},
  year={2024},
  doi={10.1109/CVPR52733.2024.00888}
}
```
