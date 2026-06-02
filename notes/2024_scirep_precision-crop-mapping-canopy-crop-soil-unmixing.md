# Precision Crop Mapping: Within Plant Canopy Discrimination of Crop and Soil Using Multi-Sensor Hyperspectral Imagery

## Metadata

- **Year**: 2024
- **Venue**: Scientific Reports, vol. 14, article 24903
- **Authors**: C. V. S. S. Manohar Kumar; Sudhanshu Shekhar Jha; Rama Rao Nidamanuri; Vinay Kumar Dadhwal
- **Paper**: https://doi.org/10.1038/s41598-024-75394-1
- **Code**: TBD
- **Project**: TBD
- **Local PDF**: ../pdfs/s41598-024-75394-1.pdf
- **Datasets**: cabbage crop-soil sub-canopy HSI; terrestrial HSI; drone HSI
- **Tags**: mixed, dataset, benchmark, agriculture, crop-soil, drone, terrestrial-HSI

## Quick Reading

- **What it is about**: The paper evaluates spectral unmixing for within-canopy crop/soil discrimination and creates multi-sensor terrestrial/drone HSI reference datasets.
- **Is it linear blind unmixing?** No. It uses known/endmember-library-driven spectral unmixing algorithms, including linear, sparse, and nonlinear variants; this survey treats it as a dataset/benchmark/application paper.
- **Datasets used**: terrestrial HSI, drone HSI at multiple flight heights, field spectral libraries, and crop/soil abundance references.
- **Experimental effect**: Crop and soil abundance discrimination can approach 99-100% accuracy depending on endmember source, flight height, and unmixing algorithm.

## One-Sentence Summary

This Scientific Reports paper is useful as an agricultural benchmark for testing whether spectral unmixing can separate crop and soil fractions inside plant canopies.

## Problem

Precision agriculture often needs plant-level or sub-canopy crop/soil discrimination. Field-level crop mapping is common, but within-canopy separation is harder because crop leaves, soil, shadows, and sensor geometry interact at fine spatial scales.

## Method

- Acquires hyperspectral imagery from terrestrial and drone platforms.
- Builds spectral libraries from field measurements and image-derived endmembers.
- Tests multiple spectral unmixing families, including constrained linear methods, sparse methods, bilinear/generalized models, and Hapke-style intimate-mixture modeling.
- Evaluates abundance maps against measured crop/soil abundance references and reconstruction metrics such as SRE and RMSE.

## Experiments

- Endmembers: cabbage crop and soil.
- Data: terrestrial hyperspectral imagery (THI), drone hyperspectral imagery (DHI) at different heights, field spectra, and image-derived spectral libraries.
- Results: field spectral libraries give up to about 86% crop and 99% soil abundance retrieval in terrestrial imagery; THI-based libraries improve crop retrieval to about 94%; drone-based cases can reach around 99% for both crop and soil under favorable library/height choices.
- The paper cautions that reconstruction metrics such as SRE/RMSE do not always track abundance-map quality.

## Strengths

- Strong relevance to agricultural HU because it provides multi-platform, multi-resolution crop/soil reference data.
- Explicitly studies the effect of endmember source and spatial resolution.
- Highlights that abundance accuracy and reconstruction error can disagree, which is important for real-scene HU validation.

## Weaknesses / Questions

- It is an application/benchmark study, not a new HU algorithm.
- Only two endmembers are considered.
- Public data/code access is not obvious from the extracted PDF text beyond the article and supplementary materials.

## Relevance To My Work

- Useful for designing agricultural HU validation where crop/soil fraction is the target.
- Helps motivate evaluation metrics beyond reconstruction error.
- Good candidate reference for the README to-do item on crop-soil discrimination datasets.

## BibTeX

```bibtex
@article{kumar2024precision,
  title={Precision crop mapping: within plant canopy discrimination of crop and soil using multi-sensor hyperspectral imagery},
  author={Kumar, C. V. S. S. Manohar and Jha, Sudhanshu Shekhar and Nidamanuri, Rama Rao and Dadhwal, Vinay Kumar},
  journal={Scientific Reports},
  volume={14},
  pages={24903},
  year={2024},
  doi={10.1038/s41598-024-75394-1}
}
```
