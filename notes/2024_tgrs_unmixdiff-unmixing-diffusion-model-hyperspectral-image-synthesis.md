# UnmixDiff: Unmixing-Based Diffusion Model for Hyperspectral Image Synthesis

## Metadata

- **Year**: 2024
- **Venue**: IEEE Transactions on Geoscience and Remote Sensing, vol. 62
- **Authors**: Yang Yu; Erting Pan; Yong Ma; Xiaoguang Mei; Qihai Chen; Jiayi Ma
- **Paper**: https://doi.org/10.1109/TGRS.2024.3425517
- **Code**: https://github.com/yuyang95/UnmixingDM
- **Project**: TBD
- **Local PDF**: ../pdfs/UnmixDiff_Unmixing-Based_Diffusion_Model_for_Hyperspectral_Image_Synthesis.pdf
- **Datasets**: synthetic; real datasets
- **Tags**: linear,blind,diffusion,image-synthesis,abundance
- **Note status**: skimmed from the local PDF metadata and abstract

## One-Sentence Summary

This skim note records a linear blind unmixing, unmixing-based diffusion, image synthesis paper and tracks its reported evaluation on synthetic; real datasets.

## Problem

The paper belongs to the linear blind hyperspectral unmixing track, where endmember spectra and abundance maps are estimated without supplied ground-truth endmembers. It is indexed here because it addresses one or more recurring HU issues such as spatial-spectral feature extraction, spectral variability, sparse or low-rank structure, deep autoencoding, Mamba/Transformer sequence modeling, or benchmark-oriented endmember/abundance estimation.

## Method

- Main idea: linear blind unmixing; unmixing-based diffusion; image synthesis.
- Model / optimization: see the local PDF for the full derivation; this skim note records the method family and reproducibility metadata first.
- Priors or assumptions: linear blind unmixing setting, usually with nonnegativity/sum-to-one abundance constraints or neural equivalents when specified by the paper.
- Training or inference details: not exhaustively extracted in this batch pass.

## Experiments

- Datasets: synthetic; real datasets
- Metrics: visual quality; spectral consistency
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
@article{unmixdiff_unmixing_diffusion_model_hyperspectral_image_synthesis,
  title={UnmixDiff: Unmixing-Based Diffusion Model for Hyperspectral Image Synthesis},
  author={Yang Yu; Erting Pan; Yong Ma; Xiaoguang Mei; Qihai Chen; Jiayi Ma},
  year={2024},
  doi={10.1109/TGRS.2024.3425517}
}
```
