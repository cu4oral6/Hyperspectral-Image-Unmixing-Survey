# Hyperspectral Image Synthesis Through Blind Unmixing Dictionary and Deep Diffusion Models

## Metadata

- **Year**: 2026
- **Venue**: IEEE Geoscience and Remote Sensing Letters, vol. 23
- **Authors**: Martina Pastorino; Michael Alibani; Nicola Acito; Gabriele Moser
- **Paper**: https://doi.org/10.1109/LGRS.2025.3646054
- **Code**: https://github.com/martinapastorino/HSI_DDPM
- **Local PDF**: ../pdfs/Hyperspectral_Image_Synthesis_Through_Blind_Unmixing_Dictionary_and_Deep_Diffusion_Models.pdf
- **Datasets**: PRISMA imagery over Mexico, Spain, and Italy
- **Tags**: deep, diffusion, blind, unmixing-dictionary, image-synthesis, PRISMA
- **Related earlier version**: "Deep Diffusion Models and Unsupervised Hyperspectral Unmixing for Realistic Abundance Map Synthesis", CVPRW 2025, DOI: https://doi.org/10.1109/CVPRW67362.2025.00286

## One-Sentence Summary

Uses a dictionary of blind linear unmixing algorithms to extract abundance maps from real PRISMA data, then trains a guided diffusion model in abundance space to synthesize realistic hyperspectral images.

## Problem

Direct hyperspectral image synthesis is difficult because HS data are high-dimensional and have coupled spectral-spatial structure. The paper reduces the generation problem to abundance-map synthesis and then reconstructs HS imagery from generated abundances and extracted endmembers.

## Method

- Builds a dictionary of blind linear unmixing methods from least-squares, deep learning, and statistical families.
- Extracts endmembers and abundance maps from real PRISMA data.
- Trains a denoising diffusion probabilistic model on abundance patches.
- Conditions the image generation process on the unmixing-method dictionary, avoiding dependence on a single unmixing algorithm.

## Experiments

- Uses four PRISMA tiles with urban, vegetated, mountainous, and mixed land covers.
- Keeps 201 bands after removing atmospheric absorption channels.
- Crops abundance maps into 256 x 256 patches.
- Compares against direct diffusion-model HS image generation and UnmixDiff.
- Evaluation is mainly qualitative through generated false-color composites.

## Strengths

- More complete than the CVPRW workshop version because it synthesizes full HS images rather than only abundance maps.
- Official code is available.
- The unmixing dictionary is a useful way to inject physical interpretability and algorithmic diversity.

## Weaknesses / Questions

- Quantitative image-quality and spectral-fidelity metrics are not prominent in the extracted text.
- Results may depend strongly on the selected unmixing dictionary and number of endmembers.
- Worth checking whether the released code includes exact PRISMA preprocessing and trained weights.

## Relevance To My Work

- Good key paper for the intersection of HS unmixing and diffusion-based data generation.
- Useful if the project needs synthetic HSI generation, data augmentation, or sensor simulation.

## Deduplication Note

The CVPRW 2025 paper is treated as an earlier workshop version focused on realistic abundance-map synthesis. This 2026 GRSL paper is kept as the main entry because it extends the pipeline to full hyperspectral image synthesis and provides the official code link.

## BibTeX

```bibtex
@article{pastorino2026hyperspectral,
  title={Hyperspectral Image Synthesis Through Blind Unmixing Dictionary and Deep Diffusion Models},
  author={Pastorino, Martina and Alibani, Michael and Acito, Nicola and Moser, Gabriele},
  journal={IEEE Geoscience and Remote Sensing Letters},
  volume={23},
  year={2026},
  doi={10.1109/LGRS.2025.3646054}
}
```
