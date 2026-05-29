# GGCT-Net: A Dual-Branch Gated Graph Convolution and Grouped Cross-Attention Transformer Network for Hyperspectral Unmixing

## Metadata

- **Year**: 2026
- **Venue**: IEEE Transactions on Geoscience and Remote Sensing
- **Authors**: Qingfei Liu; Xiaodong Yu; Hongbin Dong; Shuying Zang
- **Paper**: https://doi.org/10.1109/TGRS.2026.3668181
- **Code**: TBD
- **Project**: TBD
- **Local PDF**: ../pdfs/GGCT-Net A Dual-Branch Gated Graph Convolution and Grouped Cross-Attention Transformer Network for Hyperspectral Unmixing.pdf
- **Datasets**: Simulated; Jasper Ridge; Samson; APEX; Ray-Tracing; Cuprite
- **Tags**: linear, blind, deep-learning, unsupervised, graph-convolution, transformer, gated-attention, LMM
- **Note status**: read from the local PDF and user-provided summary

## Quick Reading

- **What it is about**: GGCT-Net is a dual-branch deep unmixing network that combines a gated graph convolution branch with a grouped cross-attention Transformer branch to estimate both endmembers and abundance maps.
- **Is it linear blind unmixing?** In this survey table it fits the linear blind / unsupervised bucket because it learns endmembers and abundances from the HSI and uses LMM-style reconstruction. More precisely, it is an LMM-constrained deep blind unmixing method, not a traditional linear algorithm such as VCA, NMF, FCLSU, or SUnSAL.
- **Datasets used**: Simulated, Jasper Ridge, Samson, APEX, Ray-Tracing, and Cuprite.
- **Experimental effect**: It reports the best or strongest average aRMSE, aSAD, and SRE on most evaluated datasets, but with noticeably higher runtime than several deep baselines.

## One-Sentence Summary

GGCT-Net uses superpixel-guided graph convolution, spatial-spectral cross-attention, and gated feature fusion to improve unsupervised hyperspectral unmixing under an LMM reconstruction constraint.

## Problem

The paper targets two limitations in recent deep HU models. CNN-based methods are good at local spatial-spectral patterns but struggle to connect pixels that are spectrally similar and spatially far apart. Transformer-based methods capture long-range dependencies, but the paper argues that they often mix spatial and spectral features without explicitly separating the two dimensions.

The model still assumes that the number of endmembers is known in advance. The paper states that this count is set from prior knowledge and is treated as a fixed model input rather than estimated automatically.

## Method

- **Preprocessing**: SLIC superpixel segmentation is used to group spatially contiguous and spectrally similar pixels, providing the basis for graph construction.
- **G-GCN branch**: Constructs a graph from spectral similarity so that pixels or regions with similar spectra can interact even when they are spatially separated. This branch includes endmember-oriented and abundance-oriented subbranches.
- **GCAF module**: A gated cross-attention fusion module exchanges information between the endmember and abundance subbranches, filtering redundant features and strengthening useful interactions.
- **GCA-Transformer branch**: Uses a spatial-spectral cross-attention block (SCAB) to model spectral attention and spatial attention separately before fusing them, aiming to capture global long-range dependencies without collapsing spatial and spectral cues too early.
- **Decoder / reconstruction**: The network estimates abundances and endmembers and reconstructs the HSI. Training uses reconstruction loss plus a KL-divergence term.

The resulting encoder is clearly nonlinear, even though the objective and data generation in parts of the paper are tied to the linear mixing model.

## Experiments

| Dataset | Size / bands | Endmembers | Proposed result |
| --- | --- | --- | --- |
| Simulated | 100 x 100, 224 bands | Clay, Carbonate, Iron-oxide, Vegetation | mean aRMSE 0.06831, mean aSAD 0.02848, SRE 23.29 |
| Jasper Ridge | 100 x 100, 224 bands, 198 after preprocessing | Tree, Water, Soil, Road | mean aRMSE 0.06039, mean aSAD 0.06447, SRE 19.7 |
| Samson | 95 x 95, 156 bands | Soil, Tree, Water | mean aRMSE 0.06113, mean aSAD 0.05348, SRE 20.32 |
| APEX | 110 x 110, 285 bands | Road, Soil, Tree, Water | mean aRMSE 0.1091, mean aSAD 0.07947, SRE 17.32 |
| Ray-Tracing | 20 x 20, 216 bands, 185 after preprocessing | Soil, Weed, Tree | mean aRMSE 0.15945, mean aSAD 0.07432, SRE 18.48 |
| Cuprite | 250 x 190, 224 bands, about 188 effective bands | 12 minerals | abundance maps only; no GT abundance maps for RMSE-style evaluation |

The paper compares against methods such as DeepTrans, DGMSSU, CyCU-Net, UnDIP, TCCU-Net, and EOT-Net. Reported visual results emphasize clearer abundance boundaries and endmember curves closer to reference spectra. The computational-efficiency table shows the tradeoff: GGCT-Net is slower than the compared methods, with examples including about 214.47 s on APEX and 97.58 s on Ray-Tracing.

## Strengths

- Combines graph modeling and Transformer attention in a way that directly targets the local-vs-global limitation of CNNs and Transformers.
- Explicitly separates spatial and spectral attention through SCAB instead of treating all features as one undifferentiated token stream.
- Reports consistent gains across simulated, classic real, urban, orchard ray-tracing, and mineral-mapping scenes.
- Ablation on Jasper Ridge supports the complementary role of GCAF and SCAB; using both gives the reported best RMSE/SAD.

## Weaknesses / Questions

- The architecture is module-heavy, and the reported runtime is substantially higher than several baselines.
- Endmember count is not estimated automatically, so the method still depends on prior knowledge.
- Cuprite is evaluated mainly by abundance map visualization because ground-truth abundance maps are unavailable.
- The main novelty is architectural integration rather than a new physical mixing model.
- Code remains `TBD`; reproducibility depends on whether an official implementation appears.

## Relevance To My Work

This is a useful representative for deep unsupervised HU methods that combine graph neural networks and Transformers under a linear reconstruction constraint. In a survey, it should be grouped with deep blind / unsupervised spatial-spectral unmixing methods, not with traditional linear optimization methods such as VCA, NMF, FCLSU, or SUnSAL.

## BibTeX

```bibtex
@article{liu2026ggctnet,
  title={GGCT-Net: A Dual-Branch Gated Graph Convolution and Grouped Cross-Attention Transformer Network for Hyperspectral Unmixing},
  author={Liu, Qingfei and Yu, Xiaodong and Dong, Hongbin and Zang, Shuying},
  journal={IEEE Transactions on Geoscience and Remote Sensing},
  volume={64},
  pages={5506715},
  year={2026},
  doi={10.1109/TGRS.2026.3668181}
}
```
