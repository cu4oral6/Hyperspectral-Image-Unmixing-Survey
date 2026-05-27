<div align="center">

# Hyperspectral Image Unmixing Survey

An organized paper list for hyperspectral image unmixing, inspired by awesome-style survey repositories.

[中文版](README.zh-CN.md)

</div>

<p align="center">
  <a href="#-news">News</a> |
  <a href="#-contents">Contents</a> |
  <a href="#-papers">Papers</a> |
  <a href="#-datasets">Datasets</a> |
  <a href="#-benchmarks">Benchmarks</a> |
  <a href="#-reading-notes">Reading Notes</a> |
  <a href="#-contributing">Contributing</a>
</p>

## News

- **2026-05-28**: Added 3 local PDFs, paper metadata, DOI links, and reading notes.
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

where `Y` is the observed hyperspectral data, `A` contains endmember signatures, `S` contains abundance coefficients, and `N` denotes noise or modeling error. Practical unmixing methods often need to handle nonlinearity, spectral variability, spatial structure, sparse priors, and limited ground truth.

## Taxonomy

- **Classical optimization**: NMF, sparse regression, simplex/geometric methods, Bayesian models.
- **Spatial-spectral priors**: total variation, graph regularization, low-rank modeling, superpixel priors.
- **Nonlinear unmixing**: kernel methods, bilinear/multilinear models, physics-inspired nonlinear models.
- **Deep unmixing**: autoencoders, CNNs, transformers, unfolded networks, self-supervised methods.
- **Blind / unsupervised unmixing**: no labeled abundance maps or known endmembers.
- **Spectral variability**: endmember bundles, variability-aware dictionaries, domain adaptation.
- **Robust unmixing**: noisy, corrupted, low-SNR, or mixed-degradation scenes.
- **Evaluation and benchmarks**: synthetic mixtures, real datasets, reproducible protocols.

## Papers

The main editable table is in [data/papers.csv](data/papers.csv). Keep this README as a curated shortlist, and keep the CSV as the full database.

### 2026

| Title | Venue | Task | Code | Notes |
|---|---|---|---|---|
| [Hyperspectral Image Synthesis Through Blind Unmixing Dictionary and Deep Diffusion Models](https://doi.org/10.1109/LGRS.2025.3646054) | IEEE GRSL | HS image synthesis via blind unmixing dictionary + diffusion | [GitHub](https://github.com/martinapastorino/HSI_DDPM) | [note](notes/2026_grsl_hyperspectral-image-synthesis-through-blind-unmixing-dictionary-and-deep-diffusion-models.md) |

### 2025

| Title | Venue | Task | Code | Notes |
|---|---|---|---|---|
| [Deep Diffusion Models and Unsupervised Hyperspectral Unmixing for Realistic Abundance Map Synthesis](https://doi.org/10.1109/CVPRW67362.2025.00286) | CVPRW | Abundance-map synthesis via blind unmixing + diffusion | TBD | [note](notes/2025_cvprw_deep-diffusion-models-and-unsupervised-hyperspectral-unmixing.md) |
| [Hyperspectral Blind Unmixing via First-Order Graph-Guided Sparse Nonnegative Matrix Factorization](https://doi.org/10.1109/ICVISP68610.2025.11451711) | ICVISP | Graph-guided sparse NMF blind unmixing | TBD | [note](notes/2025_icvisp_hyperspectral-blind-unmixing-via-fog-snmf.md) |

### 2024

| Title | Venue | Task | Code | Notes |
|---|---|---|---|---|
| TBD | TBD | TBD | TBD | TBD |

### Before 2024

| Title | Venue | Task | Code | Notes |
|---|---|---|---|---|
| TBD | TBD | TBD | TBD | TBD |

## Datasets

| Dataset | Scene Type | Ground Truth | Common Use | Link |
|---|---|---|---|---|
| Samson | Remote sensing | Endmembers / abundances | Linear unmixing benchmark | TBD |
| Jasper Ridge | Remote sensing | Endmembers / abundances | Linear unmixing benchmark | TBD |
| Urban | Remote sensing | Endmembers / abundances | Linear unmixing benchmark | TBD |
| Cuprite | Remote sensing | Reference minerals | Endmember extraction / mineral mapping | TBD |

## Benchmarks

Recommended columns for benchmark tracking:

| Paper | Dataset | Endmembers | Metric | Result | Protocol Notes |
|---|---|---:|---|---:|---|
| TBD | TBD | TBD | SAD / RMSE / SRE | TBD | TBD |

Common metrics:

- `SAD`: spectral angle distance for endmember estimation.
- `RMSE`: abundance reconstruction error.
- `SRE`: signal-to-reconstruction error.
- `RE`: reconstruction error.

## Reading Notes

Use [notes/template.md](notes/template.md) for each paper. Suggested filename:

```text
notes/YYYY_venue_short-title.md
```

Example:

```text
notes/2025_tgrs_example-unmixing-method.md
```

## Useful Links

- [All-in-One-Image-Restoration-Survey](https://github.com/Harbinzzy/All-in-One-Image-Restoration-Survey): structure reference for this repository.
- Add domain-specific survey papers, benchmark repositories, and dataset pages here.

## Contributing

When adding a paper:

1. Add one row to [data/papers.csv](data/papers.csv).
2. Add a short note under [notes](notes/) if the paper is important or already read.
3. Add code, project page, dataset, and benchmark links whenever available.
4. Prefer official links first, then arXiv/OpenReview, then third-party mirrors.

Suggested tags:

```text
classical, sparse, nmf, bayesian, spatial-spectral, nonlinear, deep, autoencoder,
transformer, unfolding, self-supervised, blind, spectral-variability, robust,
benchmark, survey
```
