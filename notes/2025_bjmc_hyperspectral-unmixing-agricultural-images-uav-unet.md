# Hyperspectral Unmixing of Agricultural Images Taken from UAV Using Adapted U-Net Architecture

## Metadata

- **Year**: 2025
- **Venue**: Baltic Journal of Modern Computing, vol. 13, no. 3
- **Authors**: Vytautas Paura; Virginijus Marcinkevicius
- **Paper**: https://doi.org/10.22364/bjmc.2025.13.3.04
- **Code**: https://github.com/VytautasPau/UAVHyperspectral
- **Project / Data**: https://doi.org/10.5281/zenodo.13856357
- **Local PDF**: ../pdfs/Hyperspectral Unmixing of Agricultural Images Taken from UAV Using Adapted U-Net Architecture.pdf
- **Datasets**: APEX; DC Mall; Samson; Blueberry UAV
- **Tags**: linear, blind, UAV, agriculture, U-Net, autoencoder, benchmark, blueberry

## Quick Reading

- **What it is about**: This paper adapts a U-Net-style autoencoder for unsupervised hyperspectral unmixing and expands the authors' UAV blueberry-field benchmark.
- **Is it linear blind unmixing?** Yes. The model is trained without ground-truth abundances and reconstructs the input through learned abundance and endmember factors.
- **Datasets used**: APEX, DC Mall, Samson, and three large Blueberry UAV cubes.
- **Experimental effect**: The adapted U-Net improves most mRMSE/mSAD/RE values over a transformer HU baseline, especially on Samson and the Blueberry UAV cubes; DC Mall remains mixed.

## One-Sentence Summary

The paper turns U-Net into an unsupervised linear HU autoencoder and tests it on both classic HU data and a newly expanded UAV blueberry-field dataset.

## Problem

Agricultural UAV hyperspectral data is large, field-collected, and often lacks clean abundance ground truth. Many HU benchmarks are small remote-sensing scenes, so methods that look good on Samson or APEX may not be practical for full UAV strips or agricultural crops.

## Method

- Starts from a U-Net encoder-decoder idea but reshapes it for HU rather than segmentation.
- Splits latent features into endmember and abundance extraction sub-networks.
- Reconstructs the HSI by matrix multiplication, making the output interpretable as endmembers and abundance maps.
- Uses reconstruction loss, SAD, and cosine-similarity loss to encourage less redundant endmembers.
- Supports optional reference endmembers, but the main model is described as fully unsupervised.

## Experiments

- Data: APEX, DC Mall, Samson, and three Blueberry UAV cubes with six VCA-derived classes: other data, blueberries, water/wet soil, soil, shadows, and grass.
- Metrics: mRMSE, mSAD, and reconstruction error (RE).
- Key results: proposed mRMSE/mSAD/RE values are 0.4705/0.1737/0.0990 on APEX, 0.4301/0.1507/0.0526 on Samson, and 0.3112/0.2737/0.0752 on Blueberry Cube 1.
- The paper reports that mean RMSE is about 27% lower than the transformer baseline on most datasets except DC Mall, while RE and mSAD are lower on average.

## Strengths

- Directly addresses agricultural UAV HU, not only classic small benchmark cubes.
- Provides code and an open Zenodo dataset.
- The architecture is easier to tune than transformer baselines because it removes some latent-size and patch-size choices.

## Weaknesses / Questions

- Ground truth for the Blueberry UAV data is VCA-derived rather than independently measured abundance.
- Hyperparameters are manually tuned, and the paper notes that results may not be optimal.
- DC Mall does not improve across all metrics, so robustness across urban/classification-style data is not uniform.

## Relevance To My Work

- Useful for agricultural HU and UAV-scale benchmark design.
- Good source for comparing a practical U-Net autoencoder against transformer HU methods.
- The Blueberry UAV data and six-class labels are useful if the goal is to test methods beyond toy-sized benchmark scenes.

## BibTeX

```bibtex
@article{paura2025hyperspectral,
  title={Hyperspectral Unmixing of Agricultural Images Taken from UAV Using Adapted U-Net Architecture},
  author={Paura, Vytautas and Marcinkevicius, Virginijus},
  journal={Baltic Journal of Modern Computing},
  volume={13},
  number={3},
  pages={624--640},
  year={2025},
  doi={10.22364/bjmc.2025.13.3.04}
}
```
