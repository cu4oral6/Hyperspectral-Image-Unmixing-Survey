# Cross-Scale Validation of Hyperspectral Unmixing Over Agricultural Landscapes

## Metadata

- **Year**: 2026
- **Venue**: IEEE Geoscience and Remote Sensing Letters
- **Authors**: Haris Ampas; Konstantinos Karyotis; Pierre Guillevic; George Zalidis; Sophia Petridou
- **Paper**: https://doi.org/10.1109/LGRS.2026.3687594
- **Code**: TBD
- **Project**: TBD
- **Local PDF**: ../pdfs/Cross-Scale Validation of Hyperspectral Unmixing Over Agricultural Landscapes.pdf
- **Datasets**: Tanager-1 vineyard; VHR UAV imagery; field spectra
- **Tags**: validation, agriculture, linear, mixed, Tanager-1, UAV, field-spectra
- **Note status**: skimmed from the local PDF

## Quick Reading

- **What it is about**: The paper proposes a cross-scale validation workflow for soil/vegetation fraction estimates from satellite hyperspectral unmixing using UAV vegetation cover and field spectra.
- **Is it linear blind unmixing?** Not exactly. It validates a linear-decoder autoencoder spectral unmixing model and a supervised FCLS baseline; in this survey it is treated as a validation/benchmark-style linear unmixing paper rather than a pure blind HU method.
- **Datasets used**: Planet Tanager-1 hyperspectral imagery over a vineyard in Epanomi, Greece; VHR UAV imagery; PSR+ 3500 field spectra.
- **Experimental effect**: AE-SU matches the UAV-derived vegetation-cover distribution better than FCLS, with overlap 0.80 versus 0.72 and JS divergence 0.059 versus 0.079. Soil maps also show coherent spatial structure with Moran's I of 0.82.

## One-Sentence Summary

This letter shows how to validate satellite-scale HU fraction maps against finer UAV and field observations when pixelwise alignment is unreliable.

## Problem

Agricultural satellite pixels often mix soil and vegetation, but direct pixelwise validation is difficult because satellite, UAV, and field measurements operate at different resolutions and may be imperfectly coregistered.

## Method

- Uses Planet Tanager-1 VSWIR hyperspectral imagery as the satellite HSI.
- Uses UAV orthomosaic imagery and an ExG-derived vegetation mask as a high-resolution reference.
- Uses field-measured soil/vegetation spectra for spectral consistency checks.
- Compares an autoencoder-based spectral unmixing model with FCLS.
- Validates with distribution metrics, pure-pixel spectral checks, and spatial-coherence inspection.

## Experiments

- Scene: Gerovasiliou Vineyard, Epanomi, Thessaloniki, Greece, acquired by Tanager-1 on July 12, 2025.
- Endmembers: soil and vegetation.
- Metrics: histogram MAE, L2, Earth Mover's distance, overlap, Bhattacharyya coefficient, cosine similarity, JS divergence, Pearson correlation, KGE, and Moran's I.
- Results: AE-SU is closer to UAV-derived vegetation cover than FCLS in distribution-level metrics. High-abundance pixels are spectrally consistent with field spectra, and the resulting maps preserve vineyard-row spatial structure.
- Code status: no official code URL was found in the local PDF.

## Strengths

- Useful because many real HU applications lack exact abundance ground truth.
- Combines satellite HSI, UAV imagery, and field spectroscopy in one validation protocol.
- Makes distribution-level validation explicit, which is more realistic under scale mismatch.

## Weaknesses / Questions

- It is a short validation letter, not a full new HU algorithm paper.
- Evaluation is a two-endmember agricultural case, so generalization to more complex land-cover mixtures needs more evidence.
- Public data/code availability is not established in the local PDF.

## Relevance To My Work

Use this as a reference for validating HU results when only cross-scale proxies or field spectra are available.

## BibTeX

```bibtex
@article{ampas2026crossscale,
  title={Cross-Scale Validation of Hyperspectral Unmixing Over Agricultural Landscapes},
  author={Ampas, Haris and Karyotis, Konstantinos and Guillevic, Pierre and Zalidis, George and Petridou, Sophia},
  journal={IEEE Geoscience and Remote Sensing Letters},
  year={2026},
  doi={10.1109/LGRS.2026.3687594}
}
```
