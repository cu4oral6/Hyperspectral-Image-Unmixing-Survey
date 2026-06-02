# PICT-Net: A Transformer-Based Network with Prior Information Correction for Hyperspectral Image Unmixing

## Metadata

- **Year**: 2025
- **Venue**: Remote Sensing, vol. 17, no. 5
- **Authors**: Yiliang Zeng; Na Meng; Jinlin Zou; Wenbin Liu
- **Paper**: https://doi.org/10.3390/rs17050869
- **Code**: TBD
- **Project**: TBD
- **Local PDF**: ../pdfs/PICT-NetA Transformer-Based Network with Prior Information Correction for Hyperspectral Image Unmixing.pdf
- **Datasets**: Samson; APEX; Houston; MUUFL
- **Tags**: linear, semi-supervised, transformer, prior-information, spatial-spectral, Samson, APEX, Houston, MUUFL

## Quick Reading

- **What it is about**: PICT-Net is a dual-branch transformer HU network that uses pre-extracted endmember/pure-pixel information to correct the learned unmixing features.
- **Is it linear blind unmixing?** Not purely blind. Because it uses pre-extracted endmember prior information, this survey classifies it as linear semi-supervised / prior-guided unmixing.
- **Datasets used**: Samson, APEX, Houston, and MUUFL.
- **Experimental effect**: It reports the best RMSE and aSAD in the extracted comparison tables against CyCU-Net, EGU, DeepTrans, and Swin-HU.

## One-Sentence Summary

PICT-Net injects endmember prior information into a transformer unmixing network to improve robustness and reduce endmember variability.

## Problem

Transformer-based HU models can retain spatial and spectral context, but they may be unstable when prior information is weak or noisy. The paper argues that explicitly correcting transformer features with pure-pixel/endmember priors improves interpretability and robustness.

## Method

- Dual-branch design: an upper branch receives pre-extracted endmember prior information, while a lower transformer branch performs feature extraction and unmixing.
- Weight sharing lets the two branches exchange information rather than operating independently.
- Uses transformer encoders to capture long-range dependencies inside HSI patches.
- Uses reconstruction-related losses plus SAD-style spectral constraints.

## Experiments

- Datasets: Samson (95 x 95, 156 bands, 3 endmembers), APEX (110 x 110, 285 bands, 4 endmembers), Houston (170 x 170, 144 bands, 4 endmembers), and MUUFL (90 x 90, 64 bands, 5 endmembers).
- Baselines: CyCU-Net, EGU, DeepTrans, and Swin-HU.
- Metrics: abundance RMSE and average SAD (aSAD).
- Proposed RMSE/aSAD values: Samson 0.0531/0.0371, APEX 0.1136/0.0836, Houston 0.1500/0.1203, MUUFL 0.2457/0.0613.

## Strengths

- Strong quantitative results across four real datasets.
- The prior-information branch gives a clear reason for improved endmember stability.
- Directly compares with multiple deep HU baselines, including transformer-style methods.

## Weaknesses / Questions

- Reliance on pre-extracted endmember priors means it is less autonomous than fully blind HU methods.
- No official code link is provided in the local PDF.
- The data availability statement points to existing third-party dataset repositories rather than a self-contained release.

## Relevance To My Work

- Useful as a representative prior-guided transformer HU baseline.
- Important comparison point when deciding whether to use pure-pixel/endmember priors or stay fully blind.
- Its four-dataset benchmark table is handy for sanity-checking new semi-supervised HU results.

## BibTeX

```bibtex
@article{zeng2025pictnet,
  title={PICT-Net: A Transformer-Based Network with Prior Information Correction for Hyperspectral Image Unmixing},
  author={Zeng, Yiliang and Meng, Na and Zou, Jinlin and Liu, Wenbin},
  journal={Remote Sensing},
  volume={17},
  number={5},
  pages={869},
  year={2025},
  doi={10.3390/rs17050869}
}
```
