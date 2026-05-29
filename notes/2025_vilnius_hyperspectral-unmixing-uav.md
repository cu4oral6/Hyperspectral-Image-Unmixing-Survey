# Hyperspectral Unmixing of Hyperspectral Data Gathered Using an UAV

## Metadata

- **Year**: 2025
- **Venue**: Vilnius University doctoral dissertation
- **Authors**: Vytautas Paura
- **Paper**: https://doi.org/10.15388/vu.thesis.828
- **Code**: https://github.com/VytautasPau/HUBenchmark
- **Project / Dataset**: https://doi.org/10.5281/zenodo.13856357
- **Local PDF**: ../pdfs/Hyperspectral unmixing of hyperspectral data gathered using an UAV.pdf
- **Datasets**: BFHUD; DC Mall; Samson; APEX; USGS synthetic; IEEE GRSS synthetic
- **Tags**: linear, blind, UAV, U-Net, benchmark, dataset, BFHUD
- **Note status**: skimmed from the local PDF

## Quick Reading

- **What it is about**: The dissertation builds a UAV-gathered agricultural HU dataset (BFHUD), a benchmark workflow for HU algorithms, and a U-Net-based unsupervised HU model called HUNET.
- **Is it linear blind unmixing?** Mostly yes in this survey taxonomy. HUNET is an unsupervised deep HU model for estimating endmembers/abundances from HSI, and the benchmark also evaluates traditional linear sparse/NMF methods.
- **Datasets used**: BFHUD, DC Mall, Samson, APEX, USGS/IEEE GRSS synthetic benchmark data.
- **Experimental effect**: On BFHUD, HUNET improves RE/RMSE over a transformer baseline (0.0754/0.3625 versus 0.3129/0.5054) but has worse SAD. Similar RE/RMSE gains are reported on Samson, while DC Mall shows better RMSE/SAD but worse RE.

## One-Sentence Summary

This dissertation is useful for HU survey work because it contributes both a UAV agricultural HU dataset/benchmark and a U-Net-based blind unmixing model.

## Problem

Open HU benchmarks are often satellite/airborne scenes with limited relevance to low-altitude UAV agriculture. The thesis targets data collection, benchmarking, and model design for UAV HSI where high spatial resolution and agricultural materials change the evaluation setting.

## Method

- Collects UAV hyperspectral data over blueberry fields and publishes BFHUD.
- Uses VCA and RMSE-based assignment to derive six approximate classes/endmembers for BFHUD.
- Defines benchmark tests for endmember robustness, noise robustness, and image-size sensitivity.
- Proposes HUNET, a U-Net-like unsupervised HU model with reconstruction and spectral-angle losses plus a cosine-similarity term.

## Experiments

- BFHUD: three UAV cubes, each with 1024 pixel width, about 2815-3177 lines, 224 bands, and six classes: bare soil, blueberries, grass, shadow, water/wet soil, and other.
- Benchmark algorithms: SUnSAL, SUnSAL-TV, S2WSU, CNMF, R-CoNMF, SGSNMF, RSNMF, ALMM, and HUNET.
- Synthetic benchmark: combines IEEE GRSS-style patterns and USGS spectra for robustness tests.
- HUNET comparison: BFHUD, DC Mall, and Samson against a transformer HU model.
- Results: SUnSAL is strongest in the endmember-robustness benchmark; RSNMF/SUnSAL are strong in noise/size tests; HUNET improves reconstruction error on BFHUD and Samson but not all SAD scores.

## Strengths

- Adds a practical UAV agriculture dataset to a field dominated by classic remote-sensing benchmarks.
- Provides a benchmark repository and a dataset DOI.
- Covers both classical HU algorithms and a new deep HU model.

## Weaknesses / Questions

- BFHUD ground truth is approximate because it is derived from VCA and class assignment rather than direct material measurement.
- HUNET improves reconstruction metrics but not consistently SAD.
- As a dissertation, it is broader than a single paper and should be cited with care when comparing against journal methods.

## Relevance To My Work

Use BFHUD and HUBenchmark as practical references for UAV/agricultural HU experiments, especially when designing robustness tests beyond Samson/Urban/Jasper.

## BibTeX

```bibtex
@phdthesis{paura2025uav,
  title={Hyperspectral Unmixing of Hyperspectral Data Gathered Using an UAV},
  author={Paura, Vytautas},
  school={Vilnius University},
  year={2025},
  doi={10.15388/vu.thesis.828}
}
```
