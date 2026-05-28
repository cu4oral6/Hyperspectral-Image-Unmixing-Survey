<div align="center">

# Hyperspectral Image Unmixing Survey

An organized paper list for hyperspectral image unmixing, inspired by awesome-style survey repositories.

[中文版](README.zh-CN.md)

</div>

<p align="center">
  <a href="#news">News</a> |
  <a href="#contents">Contents</a> |
  <a href="#papers">Papers</a> |
  <a href="#datasets">Datasets</a> |
  <a href="#benchmarks">Benchmarks</a> |
  <a href="#reading-notes">Reading Notes</a>
</p>

## News

- **2026-05-28**: Deduplicated paper list and reorganized entries by linear/nonlinear and blind/non-blind unmixing.
- **2026-05-28**: Added local paper metadata, DOI links, bilingual notes, and benchmark records.
- **2026-05-27**: Repository scaffold created for collecting hyperspectral image unmixing papers.

## Contents

- [Problem Setup](#problem-setup)
- [Taxonomy](#taxonomy)
- [Papers](#papers)
- [Datasets](#datasets)
- [Benchmarks](#benchmarks)
- [Reading Notes](#reading-notes)
- [Useful Links](#useful-links)
- [Contributing](#contributing)

## Problem Setup

Hyperspectral image unmixing estimates a set of endmembers and their abundance maps from mixed spectral pixels. A typical linear mixing model is:

```text
Y = AS + N
```

where `Y` is the observed hyperspectral data, `A` contains endmember signatures, `S` contains abundance coefficients, and `N` denotes noise or modeling error.

## Taxonomy

This repository uses a primary four-way classification:

- **Linear blind unmixing**: linear mixing model; endmembers and abundances are estimated from the image without known endmember spectra.
- **Linear non-blind unmixing**: linear mixing model; endmembers or a spectral library are given or externally supplied.
- **Nonlinear blind unmixing**: nonlinear mixing model; endmembers and abundances are estimated without known endmember spectra.
- **Nonlinear non-blind unmixing**: nonlinear mixing model; endmembers, libraries, or other external material priors are supplied.

Secondary tags track method families such as NMF, sparse regression, Bayesian inference, graph regularization, autoencoders, diffusion models, transformers, spectral variability, and benchmarks.

## Papers

The main editable table is in [data/papers.csv](data/papers.csv). Duplicate files and versioned papers are collapsed by DOI/title; earlier versions are noted inside the most complete paper note.

### Linear Blind Unmixing

| Year | Title | Venue | Method | Code | Notes |
|---:|---|---|---|---|---|
| 2026 | [Hyperspectral Image Synthesis Through Blind Unmixing Dictionary and Deep Diffusion Models](https://doi.org/10.1109/LGRS.2025.3646054) | IEEE Geoscience and Remote Sensing Letters, vol. 23 | linear blind unmixing; deep generative unmixing; image synthesis | [GitHub](https://github.com/martinapastorino/HSI_DDPM) | [note](notes/2026_grsl_hyperspectral-image-synthesis-through-blind-unmixing-dictionary-and-deep-diffusion-models.md) |
| 2025 | [A Spectral-Spatial Attention Network for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3576479) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | linear blind unmixing; spectral-spatial attention; denoising | TBD | TBD |
| 2025 | [Hyperspectral Blind Unmixing via First-Order Graph-Guided Sparse Nonnegative Matrix Factorization](https://doi.org/10.1109/ICVISP68610.2025.11451711) | 9th International Conference on Vision, Image and Signal Processing (ICVISP) | linear blind unmixing; graph-guided sparse NMF | TBD | [note](notes/2025_icvisp_hyperspectral-blind-unmixing-via-fog-snmf.md) |
| 2025 | [Integrating Recurrent-KAN With SAM Adapter for Blind Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3635216) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | linear blind unmixing; Recurrent-KAN; SAM adapter | TBD | TBD |
| 2025 | [Noise-to-Abundance Translation: Unsupervised Hyperspectral Unmixing Based on Diffusion Models](https://doi.org/10.1109/TGRS.2025.3582029) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | linear blind unmixing; diffusion model; autoencoder | TBD | TBD |
| 2025 | [Unrolling Plug-and-Play Network for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3540992) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | linear blind unmixing; unrolled plug-and-play network | TBD | TBD |
| 2024 | [Blind Unmixing Using Dispersion Model-Based Autoencoder to Address Spectral Variability](https://doi.org/10.1109/TGRS.2024.3399003) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | linear blind unmixing; dispersion model; spectral variability; two-stream autoencoder | TBD | TBD |
| 2024 | [MAT-Net: Multiscale Aggregation Transformer Network for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2024.3494795) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | linear blind unmixing; multiscale aggregation transformer | TBD | TBD |
| 2024 | [Unidirectional Local-Attention Autoencoder Network for Spectral Variability Unmixing](https://doi.org/10.1109/TGRS.2024.3375598) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | linear blind unmixing; spectral variability; local-attention autoencoder | TBD | TBD |
| 2024 | [UnmixDiff: Unmixing-Based Diffusion Model for Hyperspectral Image Synthesis](https://doi.org/10.1109/TGRS.2024.3425517) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | linear blind unmixing; unmixing-based diffusion; image synthesis | TBD | TBD |
| 2023 | [Multiview Spatial-Spectral Two-Stream Network for Hyperspectral Image Unmixing](https://doi.org/10.1109/TGRS.2023.3237556) | IEEE Transactions on Geoscience and Remote Sensing, vol. 61 | linear blind unmixing; unsupervised autoencoder; spatial-spectral network | TBD | [note](notes/2023_tgrs_multiview-spatial-spectral-two-stream-network.md) |

### Linear Non-Blind / Semi-Supervised Unmixing

| Year | Title | Venue | Method | Code | Notes |
|---:|---|---|---|---|---|
| 2025 | [Adaptive Multitask Autoencoder-Based Hyperspectral Unmixing Exploiting Auxiliary Data via Graph Associations](https://doi.org/10.1109/TGRS.2025.3551119) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | linear unmixing with auxiliary data; adaptive multitask autoencoder; graph associations | TBD | TBD |
| 2025 | [MSSF-Net: A Multimodal Spectral-Spatial Feature Fusion Network for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3563647) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | linear unmixing with auxiliary modality; multimodal spectral-spatial fusion | TBD | TBD |
| 2024 | [Diffusion-Model-Based Hyperspectral Unmixing Using Spectral Prior Distribution](https://doi.org/10.1109/TGRS.2024.3408475) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | linear non-blind unmixing; spectral-library prior; diffusion model | TBD | TBD |

### Nonlinear Blind Unmixing

| Year | Title | Venue | Method | Code | Notes |
|---:|---|---|---|---|---|
| 2025 | [A Biobjective Model-Driven Autocoder for Blind Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3577325) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | nonlinear blind unmixing; biobjective model-driven autoencoder; kernel model | TBD | TBD |
| 2025 | [DEAE: Diffusion-Enhanced Autoencoder Network for Unsupervised Nonlinear Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3608084) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | nonlinear blind unmixing; diffusion-enhanced autoencoder; EMLM | TBD | TBD |
| 2024 | [DAAN: A Deep Autoencoder-Based Augmented Network for Blind Multilinear Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2024.3381632) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | nonlinear blind unmixing; multilinear mixing model; augmented autoencoder | TBD | TBD |
| 2024 | [EMLM-Net: An Extended Multilinear Mixing Model-Inspired Dual-Stream Network for Unsupervised Nonlinear Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2024.3363427) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | nonlinear blind unmixing; EMLM-inspired dual-stream network; unfolded ADMM | TBD | TBD |
| 2024 | [Hyperspectral Unmixing Based on Multilinear Mixing Model Using Convolutional Autoencoders](https://doi.org/10.1109/TGRS.2024.3360714) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | nonlinear blind unmixing; multilinear mixing model; convolutional autoencoder | TBD | TBD |
| 2024 | [Two-Stream Autoencoder-Based Hyperspectral Unmixing Using Hapke Model](https://doi.org/10.1109/IGARSS53475.2024.10640399) | IEEE International Geoscience and Remote Sensing Symposium (IGARSS) | nonlinear blind unmixing; Hapke model; two-stream autoencoder | TBD | TBD |

### Nonlinear Non-Blind Unmixing

| Year | Title | Venue | Method | Code | Notes |
|---:|---|---|---|---|---|
| TBD | TBD | TBD | TBD | TBD | TBD |

### Surveys and Tools

| Year | Title | Venue | Method | Code | Notes |
|---:|---|---|---|---|---|
| 2024 | [AE-RED: A Hyperspectral Unmixing Framework Powered by Deep Autoencoder and Regularization by Denoising](https://doi.org/10.1109/TGRS.2024.3377472) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | blind unmixing; autoencoder; regularization by denoising; nonlinear-capable | TBD | TBD |
| 2024 | [Hyperspectral Blind Unmixing Using a Double Deep Image Prior](https://doi.org/10.1109/TNNLS.2023.3294714) | IEEE Transactions on Neural Networks and Learning Systems, vol. 35, no. 11 | blind unmixing; double deep image prior; linear and nonlinear models | TBD | TBD |
| 2024 | [Image Processing and Machine Learning for Hyperspectral Unmixing: An Overview and the HySUPP Python Package](https://doi.org/10.1109/TGRS.2024.3393570) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | survey and software; supervised semi-supervised and blind linear unmixing | [GitHub](https://github.com/BehnoodRasti/HySUPP) | TBD |

## Datasets

| Dataset | Scene Type | Ground Truth | Common Use | Link |
|---|---|---|---|---|
| Samson | Remote sensing | Endmembers / abundances | Linear unmixing benchmark | TBD |
| Jasper Ridge | Remote sensing | Endmembers / abundances | Linear unmixing benchmark | TBD |
| Urban | Remote sensing | Endmembers / abundances | Linear unmixing benchmark | TBD |
| Cuprite | Remote sensing | Reference minerals | Endmember extraction / mineral mapping | TBD |
| PRISMA | Remote sensing | No public abundance ground truth in listed papers | HS image synthesis / abundance generation | TBD |
| USGS synthetic | Synthetic | Endmembers / abundances | Controlled linear unmixing benchmark | TBD |

## Benchmarks

Benchmark records are maintained in [data/benchmarks.csv](data/benchmarks.csv).

| Paper | Dataset | Endmembers | Metric | Result | Protocol Notes |
|---|---|---:|---|---:|---|
| FoG-SNMF | USGS synthetic | 5 | SAD | 0.1105 / 0.0297 / 0.0065 | SNR 10 / 20 / 30 dB |
| FoG-SNMF | USGS synthetic | 5 | RMSE | 0.0791 / 0.0612 / 0.0224 | SNR 10 / 20 / 30 dB |
| FoG-SNMF | Samson | 3 | Mean SAD | 0.0506 | rock / tree / water |
| FoG-SNMF | Samson | 3 | RMSE | 0.2270 | rock / tree / water |

Common metrics:

- `SAD`: spectral angle distance for endmember estimation.
- `RMSE`: abundance reconstruction error.
- `SRE`: signal-to-reconstruction error.
- `RE`: reconstruction error.

## Reading Notes

Use [notes/template.md](notes/template.md) for English notes and [notes/zh-CN/template.md](notes/zh-CN/template.md) for Chinese notes.

## Useful Links

- [All-in-One-Image-Restoration-Survey](https://github.com/Harbinzzy/All-in-One-Image-Restoration-Survey): structure reference for this repository.
- Add domain-specific survey papers, benchmark repositories, and dataset pages here.

## Contributing

When adding a paper:

1. Add one row to [data/papers.csv](data/papers.csv).
2. Classify it by `mixing_model` and `supervision`.
3. Add a short note under [notes](notes/) and, when useful, [notes/zh-CN](notes/zh-CN/).
4. Do not upload publisher PDFs to the public repository; use DOI, arXiv, OpenReview, or project links.

