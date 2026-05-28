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

- **2026-05-28**: Indexed 229 local PDFs into 161 unique included papers, with inventory and skipped-paper audit tables.
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

The main editable table is in [data/papers.csv](data/papers.csv). This update indexes **161 unique included papers** from the local `pdfs/` folder. Duplicate files are collapsed by DOI/title; skipped application-adjacent files are tracked in [data/skipped.csv](data/skipped.csv), and the full PDF inventory is in [data/pdf_inventory.csv](data/pdf_inventory.csv).

### Linear Blind Unmixing

| Year | Title | Venue | Method | Code | Notes |
|---:|---|---|---|---|---|
| 2026 | [A Hyperspectral Unmixing Method Based on Matrix Spiral Scanning Mamba](https://doi.org/10.1109/ICAACE69793.2026.11508730) | 2026 9th International Conference on Advanced Algorithms and Control Engineering (ICAACE) | linear blind unmixing; Mamba; spiral scanning | TBD | [note](notes/2026_icaace_matrix-spiral-scanning-mamba.md) |
| 2026 | [GGCT-Net: A Dual-Branch Gated Graph Convolution and Grouped Cross-Attention Transformer Network for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2026.3668181) | IEEE Transactions on Geoscience and Remote Sensing | linear blind unmixing; transformer; graph; attention | TBD | TBD |
| 2026 | [Hyperspectral Image Synthesis Through Blind Unmixing Dictionary and Deep Diffusion Models](https://doi.org/10.1109/LGRS.2025.3646054) | IEEE Geoscience and Remote Sensing Letters, vol. 23 | linear blind unmixing; deep generative unmixing; image synthesis | [GitHub](https://github.com/martinapastorino/HSI_DDPM) | [note](notes/2026_grsl_hyperspectral-image-synthesis-through-blind-unmixing-dictionary-and-deep-diffusion-models.md) |
| 2026 | [Hyperspectral Unmixing Using Frequency-Adaptive Convolutional-Mamba Network](https://doi.org/10.1109/JSTARS.2026.3677880) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | linear blind unmixing; Mamba; spectral variability | TBD | TBD |
| 2026 | [MS^2AE-Net: A Multiscale Spectral-Spatial Autoencoder Network for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2026.3662051) | IEEE Transactions on Geoscience and Remote Sensing | linear blind unmixing; autoencoder; multiscale | TBD | TBD |
| 2026 | [Physics-Guided Vision Transformer Network With Tokens Complementarity for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2026.3676520) | IEEE Transactions on Geoscience and Remote Sensing | linear blind unmixing; transformer; tensor; unfolding | TBD | TBD |
| 2026 | [Preprocessing Algorithm Leveraging Geometric Modeling for Scale Correction in Hyperspectral Images for Improved Unmixing Performance](https://doi.org/10.1109/JSTARS.2026.3687834) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | linear blind unmixing; KAN; graph; spectral variability | TBD | TBD |
| 2025 | [A hyperspectral unmixing model for local distance-weighted variation](https://doi.org/10.1109/IGARSS55030.2025.11242428) | IEEE IGARSS | linear blind unmixing; spectral variability | TBD | TBD |
| 2025 | [A Spectral-Spatial Attention Network for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3576479) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | linear blind unmixing; spectral-spatial attention; denoising | TBD | TBD |
| 2025 | [A Two-Step Linear Mixing Model for Unmixing Under Hyperspectral Variability](https://doi.org/10.1109/IGARSS55030.2025.11243310) | IEEE IGARSS | linear blind unmixing; autoencoder; spectral variability; attention | TBD | TBD |
| 2025 | [ACR-Net: Adaptive Correlation Refined Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3581078) | IEEE Transactions on Geoscience and Remote Sensing | linear blind unmixing; graph; attention | TBD | TBD |
| 2025 | [Adaptive Multiorder Graph Regularized NMF With Dual Sparsity for Hyperspectral Unmixing](https://doi.org/10.1109/JSTARS.2025.3602505) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | linear blind unmixing; NMF; graph; attention | TBD | TBD |
| 2025 | [An Endmember-Oriented Transformer Network for Bundle-Based Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3530642) | IEEE Transactions on Geoscience and Remote Sensing | linear blind unmixing; autoencoder; transformer; bundle; spectral variability | TBD | TBD |
| 2025 | [Band Mask Network with Spatial-Spectral Fusion for Hyperspectral Unmixing](https://doi.org/10.1109/ICAISISAS64483.2025.11051638) | TBD | linear blind unmixing; graph | TBD | TBD |
| 2025 | [Bundle-Based Adaptive Dynamic PSO for Spectral Variability-Aware Endmember Extraction in Hyperspectral Imagery](https://doi.org/10.1109/WHISPERS69515.2025.11501580) | WHISPERS | linear blind unmixing; graph; bundle; spectral variability | TBD | TBD |
| 2025 | [Deep Diffusion Models and Unsupervised Hyperspectral Unmixing for Realistic Abundance Map Synthesis](https://doi.org/10.1109/CVPRW67362.2025.00286) | IEEE/CVF Conference on Computer Vision and Pattern Recognition | linear blind unmixing; diffusion | TBD | TBD |
| 2025 | [Digital Surface Model-Embedded Intrinsic Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3553823) | IEEE Transactions on Geoscience and Remote Sensing | linear blind unmixing; spectral variability | TBD | TBD |
| 2025 | [Dual Embedding Transformer Network for Hyperspectral Unmixing](https://doi.org/10.1109/JSTARS.2024.3523747) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | linear blind unmixing; autoencoder; transformer; attention; multiscale | TBD | TBD |
| 2025 | [Efficient Progressive Mamba Model for Hyperspectral Sequence Unmixing](https://doi.org/10.1109/JSTARS.2025.3593442) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | linear blind unmixing; transformer; Mamba | TBD | TBD |
| 2025 | [Endmember Independence and Bilateral Filtering Regularizations for Blind Hyperspectral Unmixing](https://doi.org/10.1109/JSTARS.2025.3605626) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | linear blind unmixing; tensor | TBD | TBD |
| 2025 | [Endmember Variation via Swarm Intelligence Optimization for Spatially Weighted Sparse Hyperspectral Unmixing](https://doi.org/10.1109/ICVISP68610.2025.11451704) | TBD | linear blind unmixing; sparse; ADMM; spectral variability | TBD | TBD |
| 2025 | [Endmember-Free Hyperspectral Unmixing](https://doi.org/10.1109/JSTARS.2025.3605889) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | linear blind unmixing | TBD | TBD |
| 2025 | [Hyperspectral Blind Unmixing via First-Order Graph-Guided Sparse Nonnegative Matrix Factorization](https://doi.org/10.1109/ICVISP68610.2025.11451711) | 9th International Conference on Vision, Image and Signal Processing (ICVISP) | linear blind unmixing; graph-guided sparse NMF | TBD | [note](notes/2025_icvisp_hyperspectral-blind-unmixing-via-fog-snmf.md) |
| 2025 | [Hyperspectral Unmixing Based on Dual-Graph Manifold Regularization: Joint Preservation of Spatial-Spectral Geometric Structure](https://doi.org/10.1109/ICGMRS66001.2025.11065202) | TBD | linear blind unmixing; NMF; graph | TBD | TBD |
| 2025 | [Hyperspectral Unmixing Using l2,1 Norm-Based Robust Deep Nonnegative Matrix Factorization](https://doi.org/10.1109/IGARSS55030.2025.11242377) | IEEE IGARSS | linear blind unmixing; NMF | TBD | TBD |
| 2025 | [Hyperspectral Unmixing via Nonconvex Low-Rank and Weighted Sparsity Constraints](https://doi.org/10.1109/ICVISP68610.2025.11451684) | TBD | linear blind unmixing; sparse; ADMM; low-rank | TBD | TBD |
| 2025 | [Improved Hyperspectral Unmixing Algorithm Involving the Multiplicative NMF Concept for Additive Mixing Model Dealing with Spectral Variability](https://doi.org/10.1109/IGARSS55030.2025.11243233) | IEEE IGARSS | linear blind unmixing; NMF; spectral variability | TBD | TBD |
| 2025 | [Integrating Recurrent-KAN With SAM Adapter for Blind Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3635216) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | linear blind unmixing; Recurrent-KAN; SAM adapter | TBD | TBD |
| 2025 | [Linearized ADMM for Simplicial and Nonnegative Component Analyses](https://doi.org/10.1109/IEEECONF67917.2025.11443634) | TBD | linear blind unmixing; NMF; ADMM | TBD | TBD |
| 2025 | [Mamba-Enhanced Spatial-Spectral Feature Learning for Hyperspectral Unmixing](https://doi.org/10.1109/JSTARS.2025.3598873) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | linear blind unmixing; Mamba | TBD | TBD |
| 2025 | [Multiscale Spatial Graph-Regularized Hierarchical Sparse Unmixing Based on the Framelet Transform](https://doi.org/10.1109/TGRS.2025.3609968) | IEEE Transactions on Geoscience and Remote Sensing | linear blind unmixing; sparse; graph; ADMM; multiscale | TBD | TBD |
| 2025 | [Noise-to-Abundance Translation: Unsupervised Hyperspectral Unmixing Based on Diffusion Models](https://doi.org/10.1109/TGRS.2025.3582029) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | linear blind unmixing; diffusion model; autoencoder | TBD | TBD |
| 2025 | [On the Exclusion of Hyperspectral Sources](https://doi.org/10.1109/ICASSP43922.2022.9747709) | IEEE ICASSP | linear blind unmixing; graph | TBD | TBD |
| 2025 | [REDU-Net: Robust and Efficient Dynamic Unfolding Network for Abundance Estimation](https://doi.org/10.1109/TGRS.2025.3540378) | IEEE Transactions on Geoscience and Remote Sensing | linear blind unmixing; GAN; attention; unfolding | TBD | TBD |
| 2025 | [Spectral Variability-Aware Cascaded Autoencoder for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3543566) | IEEE Transactions on Geoscience and Remote Sensing | linear blind unmixing; autoencoder; spectral variability | TBD | TBD |
| 2025 | [SSLT-Net: A Spatial-Spectral Linear Transformer Unmixing Network for Hyperspectral Image](https://doi.org/10.1109/LGRS.2024.3514888) | IEEE Geoscience and Remote Sensing Letters | linear blind unmixing; transformer; attention; multiscale | TBD | TBD |
| 2025 | [Stationary Wavelet Convolutional Network With Generative Feature Learning for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2024.3516114) | IEEE Transactions on Geoscience and Remote Sensing | linear blind unmixing; graph | TBD | TBD |
| 2025 | Superpixel-Based Autoencoder-Like Nonnegative Tensor Factorization for Hyperspectral Unmixing | IEEE Transactions on Geoscience and Remote Sensing | linear blind unmixing; autoencoder; NMF; spectral variability; low-rank | TBD | TBD |
| 2025 | [Synthesis of Abundance Maps Through Blind Hyperspectral Unmixing and Deep Diffusion Models](https://doi.org/10.1109/IGARSS55030.2025.11243836) | IEEE IGARSS | linear blind unmixing; diffusion | TBD | TBD |
| 2025 | Transformer for Multitemporal Hyperspectral Image Unmixing | TBD | linear blind unmixing; transformer; attention | TBD | TBD |
| 2025 | [UNMamba: Cascaded Spatial-Spectral Mamba for Blind Hyperspectral Unmixing](https://doi.org/10.1109/LGRS.2025.3545505) | IEEE Geoscience and Remote Sensing Letters | linear blind unmixing; Mamba | TBD | TBD |
| 2025 | [Unrolling Plug-and-Play Network for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3540992) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | linear blind unmixing; unrolled plug-and-play network | TBD | TBD |
| 2025 | Updated Homogeneity Criteria Based Low-Dimensional Representation for Hyperspectral Unmixing | TBD | linear blind unmixing; NMF | TBD | TBD |
| 2025 | [URDM: Hyperspectral Unmixing Regularized by Diffusion Models](https://doi.org/10.1109/TIP.2025.3638151) | IEEE Transactions on Image Processing | linear blind unmixing; diffusion; graph; ADMM | TBD | TBD |
| 2024 | [A Fast Sparse NMF Optimization Algorithm for Hyperspectral Unmixing](https://doi.org/10.1109/JSTARS.2023.3341583) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | linear blind unmixing; NMF; sparse; attention | TBD | TBD |
| 2024 | [A Generalized Multiscale Bundle-Based Hyperspectral Sparse Unmixing Algorithm](https://doi.org/10.1109/LGRS.2024.3358694) | IEEE Geoscience and Remote Sensing Letters | linear blind unmixing; sparse; bundle; spectral variability; multiscale | TBD | TBD |
| 2024 | [A New ADMM-Based Hyperspectral Unmixing Algorithm Associated with a Linear Mixing Model Addressing Spectral Variability with a Multiplicative Structure](https://doi.org/10.1109/IGARSS53475.2024.10640925) | IEEE IGARSS | linear blind unmixing; ADMM; spectral variability | TBD | TBD |
| 2024 | [A New Dual-Feature Fusion Network for Enhanced Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2024.3505292) | IEEE Transactions on Geoscience and Remote Sensing | linear blind unmixing; autoencoder | TBD | TBD |
| 2024 | [A Novel Endmember Bundle Extraction Framework for Capturing Endmember Variability by Dynamic Optimization](https://doi.org/10.1109/TGRS.2024.3354046) | IEEE Transactions on Geoscience and Remote Sensing | linear blind unmixing; graph; bundle; spectral variability | TBD | TBD |
| 2024 | [A Reversible Generative Network for Hyperspectral Unmixing With Spectral Variability](https://doi.org/10.1109/TGRS.2024.3403926) | IEEE Transactions on Geoscience and Remote Sensing | linear blind unmixing; spectral variability; attention | TBD | TBD |
| 2024 | [A Spectral Variability Attention Autoencoder Network for Hyperspectral Unmixing](https://doi.org/10.1109/IGARSS53475.2024.10641672) | IEEE IGARSS | linear blind unmixing; autoencoder; spectral variability; attention | TBD | TBD |
| 2024 | [Addressing Spectral Variability in Hyperspectral Unmixing with a Novel Linear Adaptive Additive Mixing Model and an Associated ADMM-Based Approach](https://doi.org/10.1109/M2GARSS57310.2024.10537424) | IEEE Mediterranean and Middle-East Geoscience and Remote Sensing Symposium | linear blind unmixing; NMF; graph; ADMM; spectral variability | TBD | TBD |
| 2024 | [An ADMM-Based Approach Associated with a Linear Mixing Model Multiplicatively Tuned to Deal with Spectral Variability in Hyperspectral Unmixing](https://doi.org/10.1109/M2GARSS57310.2024.10537495) | IEEE Mediterranean and Middle-East Geoscience and Remote Sensing Symposium | linear blind unmixing; ADMM; spectral variability | TBD | TBD |
| 2024 | [An Admm-Based Hyperspectral Unmixing Algorithm For A Modified Almm Addressing Spectral Variability](https://doi.org/10.1109/M2GARSS57310.2024.10537333) | IEEE Mediterranean and Middle-East Geoscience and Remote Sensing Symposium | linear blind unmixing; NMF; ADMM; spectral variability | TBD | TBD |
| 2024 | [Blind Unmixing Using Dispersion Model-Based Autoencoder to Address Spectral Variability](https://doi.org/10.1109/TGRS.2024.3399003) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | linear blind unmixing; dispersion model; spectral variability; two-stream autoencoder | TBD | TBD |
| 2024 | [Combinatorial Nonnegative Matrix-Tensor Factorization for Hyperspectral Unmixing Using a General lq Norm Regularization](https://doi.org/10.1109/JSTARS.2024.3392497) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | linear blind unmixing; NMF; sparse; tensor; attention | TBD | TBD |
| 2024 | [Comparative Analysis of Endmember Extraction Methods for Lithological Mapping Using Hyperspectral Imaging](https://doi.org/10.1109/MERCon63886.2024.10688782) | TBD | linear blind unmixing; KAN | TBD | TBD |
| 2024 | [Deep Attention-Guided Spatial-Spectral Network for Hyperspectral Image Unmixing](https://doi.org/10.1109/LGRS.2023.3345959) | IEEE Geoscience and Remote Sensing Letters | linear blind unmixing; autoencoder; attention | TBD | TBD |
| 2024 | [DSFC-AE: A New Hyperspectral Unmixing Method Based on Deep Shared Fully Connected Autoencoder](https://doi.org/10.1109/JSTARS.2024.3450856) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | linear blind unmixing; autoencoder; graph; spectral variability | TBD | TBD |
| 2024 | [DSSU: Dual-Stage Sparse Unmixing for Asynchronous Mixed Signal of Infrared Targets](https://doi.org/10.1109/TGRS.2024.3490539) | IEEE Transactions on Geoscience and Remote Sensing | linear blind unmixing; sparse | TBD | TBD |
| 2024 | [Endmember Distinguished Low-Rank and Sparse Representation for Hyperspectral Unmixing](https://doi.org/10.1109/IGARSS53475.2024.10641266) | IEEE IGARSS | linear blind unmixing; sparse; ADMM; low-rank | TBD | TBD |
| 2024 | [Feedback Information-Guided Spectral Variability Attention Network for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2024.3452323) | IEEE Transactions on Geoscience and Remote Sensing | linear blind unmixing; autoencoder; spectral variability; attention | TBD | TBD |
| 2024 | [Frank-Wolfe Algorithm for Simplicial and Nonnegative Component Analysis](https://doi.org/10.1109/SAM60225.2024.10636440) | TBD | linear blind unmixing; NMF | TBD | TBD |
| 2024 | [Graph Laplacian Regularization and Local Collaborative Sparse Regression Based on Superpixel Segmentation for Hyperspectral Imagery](https://doi.org/10.1109/IGARSS53475.2024.10640874) | IEEE IGARSS | linear blind unmixing; sparse; graph; ADMM; attention | TBD | TBD |
| 2024 | [Hyperspectral Unmixing Based on Chaotic Sequence Optimization of Lp Norm](https://doi.org/10.1109/LGRS.2024.3425839) | IEEE Geoscience and Remote Sensing Letters | linear blind unmixing; NMF; sparse | TBD | TBD |
| 2024 | [Hyperspectral Unmixing Using Reweighted Unidirectional TV Low-Rank NTF With Multiple-Factor Collaboration Regularization](https://doi.org/10.1109/JSTARS.2024.3392833) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | linear blind unmixing; sparse; low-rank; tensor | TBD | TBD |
| 2024 | [Hyperspectral Unmixing With Row-Sparsity Enhancement: A Difference-of-Convex Approach](https://doi.org/10.1109/APSIPAASC63619.2025.10849210) | TBD | linear blind unmixing; KAN; sparse; GAN | TBD | TBD |
| 2024 | [Locally-Rank-One-Based Joint Unmixing and Demosaicing Methods for Snapshot Spectral Images. Part II: A Filtering-Based Framework](https://doi.org/10.1109/TCI.2024.3402441) | IEEE Transactions on Computational Imaging | linear blind unmixing; low-rank | TBD | TBD |
| 2024 | [MAT-Net: Multiscale Aggregation Transformer Network for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2024.3494795) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | linear blind unmixing; multiscale aggregation transformer | TBD | TBD |
| 2024 | [MSCC-ViT:A Multiscale Visual-Transformer Network Using Convolution Crossing Attention for Hyperspectral Unmixing](https://doi.org/10.1109/JSTARS.2024.3465227) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | linear blind unmixing; transformer; attention; multiscale | TBD | TBD |
| 2024 | [Multiple Endmember Extraction Using Spatial-Spectral Information](https://doi.org/10.1109/SPIC62469.2024.10691535) | TBD | linear blind unmixing; spectral variability | TBD | TBD |
| 2024 | [On-the-Fly Spectral Unmixing for Real-Time Hyperspectral Data Analysis](https://doi.org/10.1109/WHISPERS65427.2024.10876536) | WHISPERS | linear blind unmixing | TBD | TBD |
| 2024 | [Optimal Transport Based Hyperspectral Unmixing for Highly Mixed Observations](https://doi.org/10.1109/WHISPERS65427.2024.10876524) | WHISPERS | linear blind unmixing; autoencoder; NMF | TBD | TBD |
| 2024 | [Pixel-to-Abundance Translation: Conditional Generative Adversarial Networks Based on Patch Transformer for Hyperspectral Unmixing](https://doi.org/10.1109/JSTARS.2024.3368286) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | linear blind unmixing; transformer; GAN; attention | TBD | TBD |
| 2024 | [Plug-and-Play Prior for Sparse Hyperspectral Image Unmixing](https://doi.org/10.1109/ICCWAMTIP64812.2024.10873727) | IEEE Transactions on Image Processing | linear blind unmixing; sparse; ADMM; plug-and-play | TBD | TBD |
| 2024 | [Probabilistic Simplex Component Analysis via Variational Auto-Encoding](https://doi.org/10.1109/ICASSP48485.2024.10448368) | IEEE ICASSP | linear blind unmixing; GAN | TBD | TBD |
| 2024 | [Robust Multiscale Spectral-Spatial Regularized Sparse Unmixing for Hyperspectral Imagery](https://doi.org/10.1109/JSTARS.2023.3337130) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | linear blind unmixing; sparse; multiscale | TBD | TBD |
| 2024 | [SpACNN-LDVAE: Spatial Attention Convolutional Latent Dirichlet Variational Autoencoder for Hyperspectral Pixel Unmixing](https://doi.org/10.1109/IGARSS53475.2024.10640940) | IEEE IGARSS | linear blind unmixing; autoencoder; NMF; attention | TBD | TBD |
| 2024 | [Toward Robust Hyperspectral Unmixing: Mixed Noise Modeling and Image-Domain Regularization](https://doi.org/10.1109/JSTARS.2024.3379558) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | linear blind unmixing; sparse; GAN | TBD | TBD |
| 2024 | [Transformer-Enhanced CNN Based on Intensive Feature for Hyperspectral Unmixing](https://doi.org/10.1109/LGRS.2024.3485899) | IEEE Geoscience and Remote Sensing Letters | linear blind unmixing; autoencoder; transformer; sparse; GAN | TBD | TBD |
| 2024 | [Two-Stage Evolutionary Algorithm Based on Subspace Specified Searching for Hyperspectral Endmember Extraction](https://doi.org/10.1109/JSTARS.2023.3333955) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | linear blind unmixing; graph | TBD | TBD |
| 2024 | [Unidirectional Local-Attention Autoencoder Network for Spectral Variability Unmixing](https://doi.org/10.1109/TGRS.2024.3375598) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | linear blind unmixing; spectral variability; local-attention autoencoder | TBD | TBD |
| 2024 | [UnmixDiff: Unmixing-Based Diffusion Model for Hyperspectral Image Synthesis](https://doi.org/10.1109/TGRS.2024.3425517) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | linear blind unmixing; unmixing-based diffusion; image synthesis | TBD | TBD |
| 2024 | [Unmixing Before Fusion: A Generalized Paradigm for Multi-Source-Based Hyperspectral Image Synthesis](https://doi.org/10.1109/CVPR52733.2024.00888) | IEEE/CVF Conference on Computer Vision and Pattern Recognition | linear blind unmixing | TBD | TBD |
| 2023 | [Multiview Spatial-Spectral Two-Stream Network for Hyperspectral Image Unmixing](https://doi.org/10.1109/TGRS.2023.3237556) | IEEE Transactions on Geoscience and Remote Sensing, vol. 61 | linear blind unmixing; unsupervised autoencoder; spatial-spectral network | TBD | [note](notes/2023_tgrs_multiview-spatial-spectral-two-stream-network.md) |
| TBD | Generating Synthetic Data to Train a Deep Unrolled Network for Hyperspectral Unmixing | TBD | linear blind unmixing; autoencoder; sparse | TBD | TBD |

### Linear Non-Blind / Semi-Supervised Unmixing

| Year | Title | Venue | Method | Code | Notes |
|---:|---|---|---|---|---|
| 2026 | [A Multiscale Synergistic Attention Network With Initialized Endmembers for Hyperspectral Unmixing](https://doi.org/10.1109/LGRS.2026.3672340) | IEEE Geoscience and Remote Sensing Letters | linear semi-supervised unmixing; autoencoder; attention; multiscale | TBD | TBD |
| 2025 | [A New Fast Sparse Unmixing Algorithm Based on Adaptive Spectral Library Pruning and Nesterov Optimization](https://doi.org/10.1109/JSTARS.2025.3541257) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | linear semi-supervised unmixing; sparse; graph; attention | TBD | TBD |
| 2025 | [Adaptive Multitask Autoencoder-Based Hyperspectral Unmixing Exploiting Auxiliary Data via Graph Associations](https://doi.org/10.1109/TGRS.2025.3551119) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | linear unmixing with auxiliary data; adaptive multitask autoencoder; graph associations | TBD | TBD |
| 2025 | [Double-Weighted Spatial Low-Rank and Superpixel-Guided Adaptive Graph Laplacian Regularization for Sparse Hyperspectral Unmixing](https://doi.org/10.1109/TIM.2025.3548194) | IEEE Transactions on Instrumentation and Measurement | linear semi-supervised unmixing; sparse; graph; low-rank | TBD | TBD |
| 2025 | [Dual-Branch Cross Weighting Network for Multimodal Hyperspectral Unmixing](https://doi.org/10.1109/LGRS.2025.3549218) | IEEE Geoscience and Remote Sensing Letters | linear semi-supervised unmixing; autoencoder; attention; multimodal | TBD | TBD |
| 2025 | [Hyperspectral Sparse Unmixing Based on Dual-Population Cooperative Optimization](https://doi.org/10.1109/LGRS.2025.3545776) | IEEE Geoscience and Remote Sensing Letters | linear semi-supervised unmixing; NMF; sparse | TBD | TBD |
| 2025 | [MSSF-Net: A Multimodal Spectral-Spatial Feature Fusion Network for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3563647) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | linear unmixing with auxiliary modality; multimodal spectral-spatial fusion | TBD | TBD |
| 2025 | [Sparsity and Total Variation Constrained Multilayer Linear Unmixing for Hyperspectral Imagery](https://doi.org/10.1109/ICET64964.2025.11103336) | TBD | linear semi-supervised unmixing; NMF; sparse; graph; ADMM | TBD | TBD |
| 2024 | [An Informed ADMM-Based Approach for Hyperspectral Unmixing Addressing Additively-Adapted Spectral Variability](https://doi.org/10.1109/M2GARSS57310.2024.10537402) | IEEE Mediterranean and Middle-East Geoscience and Remote Sensing Symposium | linear semi-supervised unmixing; NMF; ADMM; spectral variability | TBD | TBD |
| 2024 | [Diffusion-Model-Based Hyperspectral Unmixing Using Spectral Prior Distribution](https://doi.org/10.1109/TGRS.2024.3408475) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | linear non-blind unmixing; spectral-library prior; diffusion model | TBD | TBD |
| 2024 | [Fast Semisupervised Unmixing Using Nonconvex Optimization](https://doi.org/10.1109/TGRS.2024.3440663) | IEEE Transactions on Geoscience and Remote Sensing | linear semi-supervised unmixing; nonconvex optimization | TBD | TBD |
| 2024 | [Hyperspectral Pixel Unmixing With Latent Dirichlet Variational Autoencoder](https://doi.org/10.1109/TGRS.2024.3357589) | IEEE Transactions on Geoscience and Remote Sensing | linear semi-supervised unmixing; autoencoder | TBD | TBD |
| 2024 | [Hyperspectral Unmixing Using Nonconvex Shrinkage and Total Variation](https://doi.org/10.1109/ICEEE62185.2024.10779271) | TBD | linear semi-supervised unmixing; sparse; ADMM; GAN | TBD | TBD |
| 2024 | [Mutual Incoherence and Relative Total Variation Regularizations for Blind Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2024.3388991) | IEEE Transactions on Geoscience and Remote Sensing | linear semi-supervised unmixing; KAN; NMF; sparse | TBD | TBD |

### Nonlinear Blind Unmixing

| Year | Title | Venue | Method | Code | Notes |
|---:|---|---|---|---|---|
| 2026 | [A Swin Transformer-Based Hybrid U-Shape Network for Nonlinear Hyperspectral Unmixing](https://doi.org/10.1109/LGRS.2026.3681172) | IEEE Geoscience and Remote Sensing Letters | nonlinear blind unmixing; transformer; attention; multiscale | TBD | TBD |
| 2026 | [Fully Blind Hyperspectral Unmixing Without Explicit Mixing Models or Endmember Initialization](https://doi.org/10.1109/TGRS.2026.3671829) | IEEE Transactions on Geoscience and Remote Sensing | nonlinear blind unmixing; autoencoder; transformer | TBD | TBD |
| 2026 | [Neural Architecture Search With Spatial-Spectral Attention for Higher-Order Nonlinear Hyperspectral Unmixing](https://doi.org/10.1109/TNNLS.2026.3678170) | IEEE Transactions on Neural Networks and Learning Systems | nonlinear blind unmixing; autoencoder; sparse; attention; multiscale | TBD | TBD |
| 2026 | [Overparameterized Nonnegative Tensor Factorization for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2026.3676754) | IEEE Transactions on Geoscience and Remote Sensing | nonlinear blind unmixing; low-rank; tensor | TBD | TBD |
| 2026 | [SSST-GAN: A Sampling-Based Spatial-Spectral Transformer and Generative Adversarial Network for Hyperspectral Unmixing](https://doi.org/10.1109/JSTARS.2026.3655512) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | nonlinear blind unmixing; transformer; sparse; GAN; attention | TBD | TBD |
| 2026 | [Superpixel-Guided Matrix-Valued Kernel Functions for Multiscale Nonlinear Hyperspectral Unmixing](https://doi.org/10.1109/JSTARS.2025.3630142) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | nonlinear blind unmixing; sparse; multiscale; kernel | TBD | TBD |
| 2025 | [A Biobjective Model-Driven Autocoder for Blind Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3577325) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | nonlinear blind unmixing; biobjective model-driven autoencoder; kernel model | TBD | TBD |
| 2025 | [A Multiscale Autoencoder Framework for Hyperspectral Unmixing](https://doi.org/10.1109/ICICSP66564.2025.11338376) | TBD | nonlinear blind unmixing; autoencoder; GAN; attention; multiscale | TBD | TBD |
| 2025 | [A Novel Bundle-Based Autoencoder for Hyperspectral Unmixing with Spectral Variability](https://doi.org/10.1109/IGARSS55030.2025.11242593) | IEEE IGARSS | nonlinear blind unmixing; autoencoder; transformer; bundle; spectral variability | TBD | TBD |
| 2025 | [A Novel Hyperspectral Unmixing Approach Jointly Addressing Nonlinearity and Spectral Variability in Urban Environments](https://doi.org/10.1109/IGARSS55030.2025.11243933) | IEEE IGARSS | nonlinear blind unmixing; NMF; spectral variability | TBD | TBD |
| 2025 | [DEAE: Diffusion-Enhanced Autoencoder Network for Unsupervised Nonlinear Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3608084) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | nonlinear blind unmixing; diffusion-enhanced autoencoder; EMLM | TBD | TBD |
| 2025 | [Enhanced Spatial-Spectral Attention Network for Hyperspectral Image Unmixing](https://doi.org/10.1109/LGRS.2025.3551729) | IEEE Geoscience and Remote Sensing Letters | nonlinear blind unmixing; autoencoder; GAN; attention; multiscale | TBD | TBD |
| 2025 | [Explainable dynamic spectral unmixing](https://doi.org/10.1109/IGARSS55030.2025.11243542) | IEEE IGARSS | nonlinear blind unmixing; attention | TBD | TBD |
| 2025 | [GAN Based Non-Linear Hyperspectral Unmixing Using Patch Transformer on Chandrayaan-2 IIRS Data](https://doi.org/10.1109/IGARSS55030.2025.11242941) | IEEE IGARSS | nonlinear blind unmixing; autoencoder; transformer; GAN | TBD | TBD |
| 2025 | [Nonlinear Blind Hyperspectral Unmixing Via Generalized Mixing Mechanism Fitting and Endmember Constraints](https://doi.org/10.1109/IGARSS55030.2025.11242663) | IEEE IGARSS | nonlinear blind unmixing; autoencoder | TBD | TBD |
| 2025 | [Pixel-Level and Global Similarity-Based Adversarial Autoencoder Network for Hyperspectral Unmixing](https://doi.org/10.1109/JSTARS.2025.3542228) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | nonlinear blind unmixing; autoencoder; transformer; GAN | TBD | TBD |
| 2025 | [Refined Tokens Vision Transformer Network for Hyperspectral Image Unmixing](https://doi.org/10.1109/IGARSS55030.2025.11243764) | IEEE IGARSS | nonlinear blind unmixing; transformer | TBD | TBD |
| 2025 | [Structure Low-Rank and Self-Representation Learning for Hyperspectral Nonlinear Unmixing](https://doi.org/10.1109/IGARSS55030.2025.11242895) | IEEE IGARSS | nonlinear blind unmixing; NMF; sparse; low-rank | TBD | TBD |
| 2024 | [A Two-Stream Stacked Autoencoder With Inter-Class Separability for Bilinear Hyperspectral Unmixing](https://doi.org/10.1109/TCI.2024.3369410) | IEEE Transactions on Computational Imaging | nonlinear blind unmixing; autoencoder; attention; multiscale; bilinear | TBD | TBD |
| 2024 | [An Abundance-Guided Attention Network for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2024.3353259) | IEEE Transactions on Geoscience and Remote Sensing | nonlinear blind unmixing; graph; attention; kernel | TBD | TBD |
| 2024 | [DAAN: A Deep Autoencoder-Based Augmented Network for Blind Multilinear Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2024.3381632) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | nonlinear blind unmixing; multilinear mixing model; augmented autoencoder | TBD | TBD |
| 2024 | [Deep NMF and Autoencoder: A Comparative Analysis for Hyperspectral Unmixing Using Prisma Real Images](https://doi.org/10.1109/IGARSS53475.2024.10642930) | IEEE IGARSS | nonlinear blind unmixing; autoencoder; NMF; low-rank | TBD | TBD |
| 2024 | [EMLM-Net: An Extended Multilinear Mixing Model-Inspired Dual-Stream Network for Unsupervised Nonlinear Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2024.3363427) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | nonlinear blind unmixing; EMLM-inspired dual-stream network; unfolded ADMM | TBD | TBD |
| 2024 | [Hyperspectral Image Endmember Extraction Algorithm Based on Manifold Learning and Superpixel Feature Extraction](https://doi.org/10.1109/CISCE62493.2024.10653429) | TBD | nonlinear blind unmixing | TBD | TBD |
| 2024 | [Hyperspectral Unmixing Based on Multilinear Mixing Model Using Convolutional Autoencoders](https://doi.org/10.1109/TGRS.2024.3360714) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | nonlinear blind unmixing; multilinear mixing model; convolutional autoencoder | TBD | TBD |
| 2024 | [Hyperspectral Unmixing via Multi-scale Representation by CNN-BiLSTM and Transformer Network](https://doi.org/10.1109/ICSIDP62679.2024.10868234) | TBD | nonlinear blind unmixing; autoencoder; transformer; graph | TBD | TBD |
| 2024 | [Hyperspectral Unmixing With Multi-Scale Convolution Attention Network](https://doi.org/10.1109/JSTARS.2023.3335907) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | nonlinear blind unmixing; autoencoder; attention | TBD | TBD |
| 2024 | [Identifiable Solutions to Foreground Signature Extraction From Hyperspectral Images in an Intimate Mixing Scenario](https://doi.org/10.1109/ICASSP40776.2020.9053456) | IEEE ICASSP | nonlinear blind unmixing | TBD | TBD |
| 2024 | [Improving Spectral Unmixing Performance by Frequency Component Reduction](https://doi.org/10.1109/WHISPERS65427.2024.10876530) | WHISPERS | nonlinear blind unmixing; Hapke; bilinear | TBD | TBD |
| 2024 | [Multiscale Convolutional Mask Network for Hyperspectral Unmixing](https://doi.org/10.1109/JSTARS.2024.3352080) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | nonlinear blind unmixing; autoencoder; graph; spectral variability; multiscale | TBD | TBD |
| 2024 | [Proportional Perturbation Model for Hyperspectral Unmixing Accounting for Endmember Variability](https://doi.org/10.1109/LGRS.2024.3350889) | IEEE Geoscience and Remote Sensing Letters | nonlinear blind unmixing; spectral variability | TBD | TBD |
| 2024 | [Semi-NMF Regularization-Based Autoencoder Training for Hyperspectral Unmixing](https://doi.org/10.1109/NCC60321.2024.10485752) | TBD | nonlinear blind unmixing; autoencoder; NMF | TBD | TBD |
| 2024 | [Sparse Coding Inspired GAN for Hyperspectral Unmixing](https://doi.org/10.1109/WHISPERS65427.2024.10876499) | WHISPERS | nonlinear blind unmixing; sparse; GAN | TBD | TBD |
| 2024 | [Spectral Variability Augmented Multilinear Mixing Model for Hyperspectral Nonlinear Unmixing](https://doi.org/10.1109/LGRS.2024.3482103) | IEEE Geoscience and Remote Sensing Letters | nonlinear blind unmixing; sparse; spectral variability; low-rank; multilinear | TBD | TBD |
| 2024 | [Superpixel-Based Low-Rank Tensor Factorization for Blind Nonlinear Hyperspectral Unmixing](https://doi.org/10.1109/JSEN.2024.3373477) | TBD | nonlinear blind unmixing; spectral variability; low-rank; tensor; multilinear | TBD | TBD |
| 2024 | [Two-Stream Autoencoder-Based Hyperspectral Unmixing Using Hapke Model](https://doi.org/10.1109/IGARSS53475.2024.10640399) | IEEE International Geoscience and Remote Sensing Symposium (IGARSS) | nonlinear blind unmixing; Hapke model; two-stream autoencoder | TBD | TBD |
| 2024 | [Unsupervised Nonlinear Hyperspectral Unmixing Based on an Extended Multilinear Mixing Model-Inspired Dual-Stream Network](https://doi.org/10.1109/IGARSS53475.2024.10641679) | IEEE IGARSS | nonlinear blind unmixing; autoencoder; ADMM; multilinear; bilinear | TBD | TBD |
| TBD | Maximum Correntropy-Based Kurtosis Regularization Constrained Non-negative Matrix Factorization For Hyperspectral Unmixing | TBD | nonlinear blind unmixing; NMF; sparse | TBD | TBD |

### Nonlinear Non-Blind / Semi-Supervised Unmixing

| Year | Title | Venue | Method | Code | Notes |
|---:|---|---|---|---|---|
| 2026 | [A Physics-Guided Diffusion Unmixing Model for Global Lunar Mineral Abundance Mapping](https://doi.org/10.1109/JSTARS.2026.3657892) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | nonlinear semi-supervised unmixing; diffusion; spectral variability; Hapke | TBD | TBD |
| 2026 | [AD-HKFCM: A Robust Nonlinear Spectral Variability-Aware Unmixing via Intra/Inter-Class Affinity Cohesion](https://doi.org/10.1109/JSTARS.2026.3659984) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | nonlinear semi-supervised unmixing; spectral variability; kernel | TBD | TBD |
| 2025 | [Robust Sparse Unmixing via Continuous Mixed Norm to Address Mixed Noise](https://doi.org/10.1109/LGRS.2025.3548697) | IEEE Geoscience and Remote Sensing Letters | nonlinear semi-supervised unmixing; sparse; ADMM; attention | TBD | TBD |
| 2024 | [A Multimodal Hyperspectral Unmixing Method Under Spectral Variability](https://doi.org/10.1109/IGARSS53475.2024.10641781) | IEEE IGARSS | nonlinear semi-supervised unmixing; sparse; spectral variability; attention; multimodal | TBD | TBD |
| 2024 | [A New Version of an Endmember-Guided Autoencoder (EGAE-V2) with Improved Architecture and Regularization by Correlation Between Ground Truths and Latent Activations](https://doi.org/10.1109/WHISPERS65427.2024.10876451) | WHISPERS | nonlinear semi-supervised unmixing; autoencoder; GAN | TBD | TBD |
| 2024 | [A Supervised Approach for Estimating Fractional Abundances of Binary Intimate Mixtures](https://doi.org/10.1109/JSTARS.2024.3387750) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | nonlinear semi-supervised unmixing; spectral variability | TBD | TBD |
| 2024 | [Nonlinear Unmixing of Hyperspectral Images via Regularized Wasserstein Dictionary Learning](https://doi.org/10.1109/IGARSS53475.2024.10642450) | IEEE IGARSS | nonlinear semi-supervised unmixing; Wasserstein dictionary learning | TBD | TBD |
| 2024 | [Robust Blind Linear Unmixing for Correlated Multimodal Images in Medical Applications](https://doi.org/10.1109/URUCON63440.2024.10850209) | TBD | nonlinear semi-supervised unmixing; sparse; graph; multimodal | TBD | TBD |
| 2024 | [Theoretical and Practical Progress in Hyperspectral Pixel Unmixing with Large Spectral Libraries from a Sparse Perspective](https://doi.org/10.1109/WHISPERS65427.2024.10876427) | WHISPERS | nonlinear semi-supervised unmixing; sparse | TBD | TBD |

### Hybrid / Cross-Model Unmixing

| Year | Title | Venue | Method | Code | Notes |
|---:|---|---|---|---|---|
| 2026 | [DTU-Net: A Multi-Scale Dilated Transformer Network for Nonlinear Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2026.3658361) | IEEE Transactions on Geoscience and Remote Sensing | hybrid blind unmixing; autoencoder; transformer; attention; multiscale | TBD | TBD |
| 2025 | [Hybrid Linear-Nonlinear Hyperspectral Unmixing of Homogeneous Solutions](https://doi.org/10.1109/ICECER65523.2025.11401230) | TBD | hybrid blind unmixing; NMF; bilinear | TBD | TBD |
| 2025 | [Hyperspectral Unmixing Network Based on Hybrid Spectral Variability Model](https://doi.org/10.1109/IGARSS55030.2025.11243760) | IEEE IGARSS | hybrid blind unmixing; autoencoder; NMF; sparse; spectral variability | TBD | TBD |
| 2025 | Robust and Unified Semi-Supervised Unmixing of Hyperspectral Imaging for Linear and Multilinear Models | TBD | hybrid semi-supervised unmixing; multilinear | TBD | TBD |
| 2024 | [A Regional Adaptive Autoencoder Network for Hyperspectral Unmixing](https://doi.org/10.1109/IAECST64597.2024.11117391) | TBD | hybrid blind unmixing; autoencoder; attention | TBD | TBD |
| 2024 | [AE-RED: A Hyperspectral Unmixing Framework Powered by Deep Autoencoder and Regularization by Denoising](https://doi.org/10.1109/TGRS.2024.3377472) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | blind unmixing; autoencoder; regularization by denoising; nonlinear-capable | TBD | TBD |
| 2024 | [Hyperspectral Blind Unmixing Using a Double Deep Image Prior](https://doi.org/10.1109/TNNLS.2023.3294714) | IEEE Transactions on Neural Networks and Learning Systems, vol. 35, no. 11 | blind unmixing; double deep image prior; linear and nonlinear models | TBD | TBD |
| 2024 | [Spatial-Spectral Twin Autoencoders for Hyperspectral Unmixing Via Superpixel-Hypergraph-Augmented Feature Representation](https://doi.org/10.1109/IGARSS53475.2024.10642904) | IEEE IGARSS | hybrid blind unmixing; autoencoder; sparse; graph; Hapke | TBD | TBD |
| TBD | [Unified Unsupervised Unmixing With Sparse Noise Estimation for Linear and Multilinear Models](https://doi.org/10.1109/LSP) | IEEE Signal Processing Letters | hybrid blind unmixing; sparse noise estimation; linear and multilinear models | TBD | TBD |

### Surveys, Benchmarks, Datasets, and Tools

| Year | Title | Venue | Method | Code | Notes |
|---:|---|---|---|---|---|
| 2025 | [A Benchmark Linear Unmixing Dataset With Spectral Variability and Ground Truth](https://doi.org/10.1109/WHISPERS69515.2025.11501633) | WHISPERS | survey/dataset/tool | TBD | TBD |
| 2024 | [A Detailed Analysis of Datasets Used in HSI in the Context of Mixture Models for Unmixing](https://doi.org/10.1109/MERCon63886.2024.10689093) | TBD | survey/dataset/tool | TBD | TBD |
| 2024 | [A New Hyperspectral Unmixing Benchmark for Weak Signal Meat Contamination Detection](https://doi.org/10.1109/DICTA63115.2024.00088) | TBD | survey/dataset/tool | TBD | TBD |
| 2024 | [Evaluation of Hyperspectral Unmixing Methods: A Comparative Study for Very-High Spatial Resolution Hyperspectral Images](https://doi.org/10.1109/SSIAI59505.2024.10508656) | TBD | survey/dataset/tool | TBD | TBD |
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
| SUMamba | Jasper Ridge | 4 | Mean SAD | 0.046 +/- 0.0018 | soil / tree / water / road |
| SUMamba | Jasper Ridge | 4 | RMSE | 0.061 +/- 0.0032 | abundance estimation |
| SUMamba | Jasper Ridge | 4 | SAD by endmember | 0.056 / 0.050 / 0.031 / 0.046 | soil / tree / water / road |

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
