# Multiview Spatial-Spectral Two-Stream Network for Hyperspectral Image Unmixing

## Metadata

- **Year**: 2023
- **Venue**: IEEE Transactions on Geoscience and Remote Sensing
- **Authors**: Lin Qi; Zhenwei Chen; Feng Gao; Junyu Dong; Xinbo Gao; Qian Du
- **Paper**: https://doi.org/10.1109/TGRS.2023.3237556
- **Code**: TBD
- **Local file**: ../pdfs/Qi 等 - 2023 - Multiview spatial–spectral two-stream network for hyperspectral image unmixing.docx
- **Datasets**: USGS synthetic; Urban; Jasper Ridge; Cuprite
- **Classification**: Linear blind unmixing
- **Tags**: linear, blind, autoencoder, RNN, spatial-spectral, multiview, Urban, Jasper-Ridge, Cuprite

## One-Sentence Summary

Proposes MSSS-Net, an unsupervised autoencoder-based two-stream network that uses RNNs to jointly exploit multiview spectral partitions and spatial neighborhood information for linear hyperspectral unmixing.

## Problem

Many deep unmixing methods use spatial context, but hyperspectral data also contain rich narrow-band spectral structure. The paper targets better use of both multiview spectral information and local spatial structure under the linear mixing model.

## Method

- Uses an autoencoder-based unsupervised unmixing framework.
- Builds a spatial stream for pixel-neighborhood patch features.
- Builds a multiview spectral stream using spectral partitioning.
- Uses cascaded bidirectional and unidirectional RNN encoders to model spectral and spatial dependencies.
- Shares a decoder whose weights correspond to estimated endmembers.
- Uses SAD-based reconstruction loss and an abundance sparsity regularizer.

## Experiments

- Synthetic dataset: 64 x 64 pixels, 5 endmembers selected from the USGS spectral library, Gaussian noise under different SNR levels.
- Real datasets: Urban, Jasper Ridge, and Cuprite.
- Metrics: SAD and RMSE.
- Baselines include traditional methods such as VCA, L1/2-NMF, Dgs-NMF, and AE-based methods including EndNet, SNMF-Net, TANet, CNNAEU, MiSiC-Net, and SSAE.

## Strengths

- Clear linear blind unmixing formulation with a deep unsupervised architecture.
- Explicitly combines multiview spectral partitioning and spatial neighborhood modeling.
- Evaluates on both synthetic and multiple real datasets.

## Weaknesses / Questions

- Official code was not verified while creating this note.
- The architecture may be more complex than simpler AE or NMF baselines.
- The method is designed for the linear mixing model, so nonlinear mixtures and spectral variability may need additional modeling.

## Relevance To My Work

- Useful as a representative deep linear blind unmixing method.
- Good comparison point for spatial-spectral deep unmixing architectures.

## BibTeX

```bibtex
@article{qi2023multiview,
  title={Multiview Spatial-Spectral Two-Stream Network for Hyperspectral Image Unmixing},
  author={Qi, Lin and Chen, Zhenwei and Gao, Feng and Dong, Junyu and Gao, Xinbo and Du, Qian},
  journal={IEEE Transactions on Geoscience and Remote Sensing},
  year={2023},
  doi={10.1109/TGRS.2023.3237556}
}
```

