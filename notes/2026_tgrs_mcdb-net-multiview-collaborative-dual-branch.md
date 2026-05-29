# MCDB-Net: Multiview Collaborative Dual-Branch Unmixing Network for Hyperspectral Images

## Metadata

- **Year**: 2026
- **Venue**: IEEE Transactions on Geoscience and Remote Sensing
- **Authors**: Lin Qi; Yao Wu; Feng Gao; Junyu Dong; Qian Du; Xinbo Gao
- **Paper**: https://doi.org/10.1109/TGRS.2026.3672192
- **Code**: TBD
- **Project**: TBD
- **Local PDF**: ../pdfs/MCDB-Net_Multiview_Collaborative_Dual-Branch_Unmixing_Network_for_Hyperspectral_Images.pdf
- **Datasets**: synthetic; Jasper Ridge; Samson; Cuprite
- **Tags**: linear, blind, autoencoder, multiview, dual-branch, attention
- **Note status**: skimmed from the local PDF

## Quick Reading

- **What it is about**: MCDB-Net is an autoencoder-style hyperspectral unmixing network that builds multiview spectral blocks, extracts full-view and local multiview spectral features in two branches, and fuses their abundance estimates dynamically.
- **Is it linear blind unmixing?** Yes. The paper explicitly focuses on the linear mixing model and estimates endmembers/abundances without an externally supplied spectral library.
- **Datasets used**: synthetic data, Jasper Ridge, Samson, and Cuprite.
- **Experimental effect**: The paper reports stronger noise robustness on synthetic data, a 1.46 percentage-point mean-SAD gain over the best compared Jasper Ridge endmember result, best overall Samson abundance/endmember results, and strong Cuprite endmember extraction.

## One-Sentence Summary

MCDB-Net improves linear blind HU by turning each pixel spectrum into multiview spectral blocks and collaboratively combining local and full-view abundance predictions.

## Problem

Many AE-based HU methods use spectral information from a single view or rely mainly on spatial features. The paper argues that high-dimensional HSI spectra contain continuous band relationships that are underused in current deep HU networks.

## Method

- Constructs multiview spectral blocks by partitioning bands with AAP or spectrometer-driven strategies and rearranging the views into a small spectral block.
- Uses a full-view branch for global spectral attention and a local multiview branch for local spectral-view interactions.
- Adds a multiview abundance collaboration module to fuse local and full-view abundance estimates with learned dynamic weights.
- Trains with reconstruction spectral angle distance and an `l1/2` abundance sparsity term.

## Experiments

- Datasets: synthetic, Jasper Ridge, Samson, Cuprite.
- Metrics: SAD for endmembers and RMSE for abundances.
- Baselines: VCA, `L1/2`-NMF, EndNet, TANet, CNNAEU, MAT-Net, MSSR-Net.
- Results: On synthetic data, MCDB-Net is reported to outperform the deep baselines across 20-60 dB SNR. On Jasper Ridge it improves the final endmember score by 1.46 percentage points over TANet and has the best overall abundance performance. On Samson it reaches the best overall endmember and abundance estimates. On Cuprite it is reported to obtain the best endmember extraction, especially for Andradite, Kaolinite1, Montmorillonite, and Nontronite.
- Code status: no official code URL was found in the local PDF.

## Strengths

- Good fit for recent linear blind HU work that emphasizes spectral sequence structure rather than only spatial context.
- The multiview spectral block is a clear architectural idea and connects to earlier multiview HU work.
- Evaluates both controlled noise robustness and common real HU scenes.

## Weaknesses / Questions

- The PDF text extraction does not preserve all table values, so exact per-class SAD/RMSE numbers still need visual/table-level checking.
- Code is not verified, which limits reproducibility.
- It is still a reconstruction-driven linear model, so nonlinear mixing and strong spectral variability are not the main focus.

## Relevance To My Work

Use this paper as a recent linear blind deep HU baseline when comparing Mamba/Transformer/multiview autoencoder designs.

## BibTeX

```bibtex
@article{qi2026mcdb,
  title={MCDB-Net: Multiview Collaborative Dual-Branch Unmixing Network for Hyperspectral Images},
  author={Qi, Lin and Wu, Yao and Gao, Feng and Dong, Junyu and Du, Qian and Gao, Xinbo},
  journal={IEEE Transactions on Geoscience and Remote Sensing},
  year={2026},
  doi={10.1109/TGRS.2026.3672192}
}
```
