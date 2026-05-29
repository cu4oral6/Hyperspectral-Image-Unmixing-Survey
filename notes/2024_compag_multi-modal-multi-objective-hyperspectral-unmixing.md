# Multi-modal and multi-objective hyperspectral unmixing model based on multi-source data

## Metadata

- **Year**: 2024
- **Venue**: Computers and Electronics in Agriculture
- **Authors**: Jiewen Lin; Jian Chen
- **Paper**: https://doi.org/10.1016/j.compag.2024.109505
- **Code**: TBD
- **Project**: TBD
- **Local PDF**: ../pdfs/1-s2.0-S0168169924008962-main.pdf
- **Datasets**: MUUFL; Houston
- **Tags**: linear, blind, multimodal, DSM, endmember-bundle, PSO, spectral-variability
- **Note status**: skimmed from the local PDF

## Quick Reading

- **What it is about**: The paper proposes MMO-CDPSO-RSADRDSM, a multimodal multi-objective particle-swarm method for endmember bundle extraction that fuses hyperspectral data with a digital surface model.
- **Is it linear blind unmixing?** Yes. The paper states that it focuses on the linear mixture model and extracts endmember bundles from the image/DSM data without a supplied spectral library.
- **Datasets used**: MUUFL and Houston, both with HSI plus auxiliary DSM/LiDAR-style elevation information.
- **Experimental effect**: On MUUFL, the method reports mRMSE 0.1853 and re-min mSAD 0.0325, best in the extracted aggregate table. On Houston, it reports mRMSE 0.1548 and best re-min mSAD 0.0341, although MOPSOSCD has a lower mRMSE.

## One-Sentence Summary

This paper uses DSM-guided multimodal optimization to improve endmember-bundle extraction under spectral variability.

## Problem

Endmember extraction can be unstable when materials have spectral variability or similar spectra. The authors argue that auxiliary DSM/elevation information can help distinguish materials that are difficult to separate spectrally alone.

## Method

- Initializes and updates discrete particle-swarm candidates using both HSI spectral information and DSM-derived information.
- Uses relative spectral angular distance and relative DSM distance in the decision-space crowding calculation.
- Optimizes endmember bundles with multiple objectives and reconstructs abundance/mixed spectra using UCLS/FCLS-style evaluation.
- Targets endmember bundle extraction rather than a single endmember per class.

## Experiments

- MUUFL: 90 x 130 ROI, 64 bands, five endmembers: roof, grass, tree, shadow, asphalt.
- Houston: 170 x 170 ROI, 144 bands, four endmembers: parking lot 1, parking lot 2, running track, healthy grass.
- Baselines: MOPSOSCD, TSEA, IMPSO-EBE, DPSO, VCA.
- Metrics: mRMSE, re-min mSAD, and per-class SAD.
- Results: MUUFL mRMSE/re-min mSAD = 0.1853/0.0325 with 35 extracted endmembers. Houston mRMSE/re-min mSAD = 0.1548/0.0341 with 36 extracted endmembers; the paper reports best visual bundle extraction even though MOPSOSCD is better on mRMSE.
- Code status: no official code URL was found in the local PDF.

## Strengths

- Explicitly uses multi-source HSI plus DSM data for blind endmember-bundle extraction.
- Handles spectral variability by extracting bundles rather than single representatives.
- Reports quantitative results on two multimodal remote-sensing scenes.

## Weaknesses / Questions

- The method depends on available and well-registered DSM data.
- On Houston, the proposed method is not best on mRMSE.
- No code link is verified, so reproduction will require reimplementation.

## Relevance To My Work

Use this paper when comparing multimodal linear blind HU methods, especially those that exploit elevation/spatial side information for endmember variability.

## BibTeX

```bibtex
@article{lin2024multimodal,
  title={Multi-modal and multi-objective hyperspectral unmixing model based on multi-source data},
  author={Lin, Jiewen and Chen, Jian},
  journal={Computers and Electronics in Agriculture},
  year={2024},
  doi={10.1016/j.compag.2024.109505}
}
```
