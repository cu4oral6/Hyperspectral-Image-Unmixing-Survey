# Deep Diffusion Models and Unsupervised Hyperspectral Unmixing for Realistic Abundance Map Synthesis

## Metadata

- **Year**: 2025
- **Venue**: IEEE/CVF Conference on Computer Vision and Pattern Recognition Workshops (CVPRW)
- **Authors**: Martina Pastorino; Michael Alibani; Nicola Acito; Gabriele Moser
- **Paper**: https://doi.org/10.1109/CVPRW67362.2025.00286
- **Code**: TBD
- **Local PDF**: ../pdfs/Deep_Diffusion_Models_and_Unsupervised_Hyperspectral_Unmixing_for_Realistic_Abundance_Map_Synthesis.pdf
- **Datasets**: PRISMA imagery over Mexico, Spain, and Italy
- **Tags**: deep, diffusion, blind, abundance-synthesis, PRISMA

## One-Sentence Summary

Combines blind linear hyperspectral unmixing with diffusion models to generate realistic synthetic abundance maps from real PRISMA imagery without labeled training data.

## Problem

Synthetic hyperspectral data are valuable for benchmarking, mission planning, and training data augmentation, but direct generation in spectral space is expensive and difficult. This work focuses on generating realistic abundance maps as a lower-dimensional and physically interpretable intermediate representation.

## Method

- Applies a set of blind linear unmixing methods to raw hyperspectral acquisitions.
- Uses the extracted abundance maps as training samples for a diffusion model.
- Learns spatial distributions of abundance maps rather than directly generating high-dimensional spectra.
- Keeps the pipeline unsupervised, so no labeled abundance maps are required.

## Experiments

- Uses PRISMA hyperspectral images from Mexico, Spain, and Italy.
- Demonstrates generated abundance maps for mountainous, vegetated, urban, and mixed environments.
- Evaluation is largely qualitative visual analysis.
- The conclusion states that full HS image synthesis and quantitative metrics such as SAD, RMSE, PSNR, and SSIM are future work.

## Strengths

- Simple and physically interpretable bridge between classical unmixing and modern generative modeling.
- Useful as a precursor to full hyperspectral image synthesis.
- Does not rely on a single unmixing algorithm.

## Weaknesses / Questions

- Mostly qualitative; limited quantitative validation in the workshop paper.
- The generated object is abundance maps, not full hyperspectral imagery.
- Need to check whether code or full training details are available outside the PDF.

## Relevance To My Work

- Good background paper for diffusion-based abundance-map generation.
- Pair with the 2026 GRSL paper as the earlier workshop version.

## BibTeX

```bibtex
@inproceedings{pastorino2025deep,
  title={Deep Diffusion Models and Unsupervised Hyperspectral Unmixing for Realistic Abundance Map Synthesis},
  author={Pastorino, Martina and Alibani, Michael and Acito, Nicola and Moser, Gabriele},
  booktitle={IEEE/CVF Conference on Computer Vision and Pattern Recognition Workshops (CVPRW)},
  pages={3029--3037},
  year={2025},
  doi={10.1109/CVPRW67362.2025.00286}
}
```

