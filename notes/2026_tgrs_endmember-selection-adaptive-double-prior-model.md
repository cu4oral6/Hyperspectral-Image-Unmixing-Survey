# Endmember Selection With Adaptive Double Prior Model

## Metadata

- **Year**: 2026
- **Venue**: IEEE Transactions on Geoscience and Remote Sensing
- **Authors**: Rui Wu; Wenfei Luo; Lianru Gao; Longfei Ren; Hongmin Gao
- **Paper**: https://doi.org/10.1109/TGRS.2026.3664867
- **Code**: https://github.com/spdelphi/Double-Prior
- **Project**: TBD
- **Local PDF**: ../pdfs/Endmember Selection With Adaptive Double Prior Model.pdf
- **Datasets**: USGS synthetic; Cuprite; Urban; Jasper Ridge; Samson
- **Tags**: linear, semi-supervised, sparse, spectral-library, prior, endmember-selection
- **Note status**: skimmed from the local PDF

## Quick Reading

- **What it is about**: This paper proposes ADSU, an adaptive sparse unmixing method that uses two prior models and decision-making parameters to avoid being dominated by incorrect prior weights during endmember selection.
- **Is it linear blind unmixing?** No. It is linear semi-supervised/non-blind sparse unmixing because it selects active endmembers from a known spectral library and uses external priors.
- **Datasets used**: two simulated datasets based on USGS spectral libraries, plus Cuprite, Urban, Jasper Ridge, and Samson.
- **Experimental effect**: ADSU is reported as mostly optimal or suboptimal across many simulated prior-noise cases, obtains the best overall scores on Dataset 2, and gives more robust real-data abundance maps when some priors are wrong.

## One-Sentence Summary

ADSU improves sparse library-based HU by adaptively blending two prior models so that wrong prior information is less likely to force incorrect endmember selection.

## Problem

Sparse unmixing depends on a large spectral library and often uses prior weights to encourage or suppress candidate endmembers. If those priors are incomplete or wrong, a single-prior weighted sparse model can choose the wrong active materials.

## Method

- Starts from a weighted sparse unmixing objective with nonnegativity.
- Introduces two prior sets and decision-making parameters to transition between them during optimization.
- Uses an ADMM-style solver and analyzes conditions under which the double-prior model mitigates incorrect priors.
- Leaves the abundance sum-to-one constraint relaxed in the main model, consistent with sparse library selection under spectral variability.

## Experiments

- Simulated data: USGS-based spectral libraries and synthetic abundance maps under different SNR and prior-error cases.
- Real data: Cuprite, Urban, Jasper Ridge, Samson.
- Metrics: SRE and RMSE for simulated data; visual/qualitative abundance maps for real scenes where full abundance truth is unavailable.
- Baselines: SU/SUnSAL, WSU, JSpBLRU, BiJSpLRU, BMSPI, SUnCNN, LSU.
- Results: ADSU is reported to remain optimal or suboptimal across most prior settings. On Dataset 2 it achieves the best overall quantitative scores among the compared algorithms. On Cuprite and Urban it reduces artifacts caused by incorrect priors; on Jasper Ridge and Samson it stays stable when SVM-derived priors are already reliable.
- Code status: official code is listed in the PDF as https://github.com/spdelphi/Double-Prior.

## Strengths

- Directly targets an important sparse-unmixing failure mode: misleading prior knowledge.
- Includes both theoretical robustness analysis and simulated/real experiments.
- Provides code, making it more reproducible than many recent HU papers.

## Weaknesses / Questions

- It is not a blind method; performance depends on the spectral library and prior construction.
- Real-data evaluation is mostly qualitative because full abundance maps are not always available.
- The table values in the PDF are difficult to extract automatically and should be revisited visually for exact benchmark numbers.

## Relevance To My Work

Use this as a strong recent reference for linear semi-supervised sparse HU, especially when the problem includes uncertain prior/endmember-library information.

## BibTeX

```bibtex
@article{wu2026endmember,
  title={Endmember Selection With Adaptive Double Prior Model},
  author={Wu, Rui and Luo, Wenfei and Gao, Lianru and Ren, Longfei and Gao, Hongmin},
  journal={IEEE Transactions on Geoscience and Remote Sensing},
  year={2026},
  doi={10.1109/TGRS.2026.3664867}
}
```
