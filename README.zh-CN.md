<div align="center">

# 高光谱图像解混论文整理

一个用于整理高光谱图像解混相关论文、数据集、指标和阅读笔记的 survey / awesome 风格仓库。

[English](README.md)

</div>

<p align="center">
  <a href="#动态">动态</a> |
  <a href="#目录">目录</a> |
  <a href="#论文">论文</a> |
  <a href="#数据集">数据集</a> |
  <a href="#实验记录">实验记录</a> |
  <a href="#阅读笔记">阅读笔记</a>
</p>

## 动态

- **2026-05-28**：盘点 229 个本地 PDF，整理为 161 篇唯一收录论文，并新增 inventory 与 skipped 审核表。
- **2026-05-28**：去除主列表中的重复/版本迭代论文，并按线性/非线性、盲/非盲解混重新分类。
- **2026-05-28**：添加本地论文元数据、DOI、双语笔记和实验记录。
- **2026-05-27**：创建高光谱图像解混论文整理仓库骨架。

## 目录

- [问题定义](#问题定义)
- [方法分类](#方法分类)
- [论文](#论文)
- [数据集](#数据集)
- [实验记录](#实验记录)
- [阅读笔记](#阅读笔记)
- [有用链接](#有用链接)
- [维护方式](#维护方式)

## 问题定义

高光谱图像解混旨在从混合像元中估计端元光谱及其丰度图。典型的线性混合模型可以写作：

```text
Y = AS + N
```

其中 `Y` 表示观测到的高光谱数据，`A` 表示端元矩阵，`S` 表示丰度矩阵，`N` 表示噪声或建模误差。

## 方法分类

本仓库采用四类主分类：

- **线性盲解混**：基于线性混合模型，端元和丰度均从图像中估计，不预先给定端元光谱。
- **线性非盲解混**：基于线性混合模型，端元、光谱库或其他材料先验由外部提供。
- **非线性盲解混**：基于非线性混合模型，端元和丰度均未知并从数据中估计。
- **非线性非盲解混**：基于非线性混合模型，同时使用已知端元、光谱库或外部材料先验。

二级标签继续记录 NMF、稀疏回归、贝叶斯推断、图正则、自编码器、扩散模型、Transformer、光谱变异、基准 等方法族。

## 论文

完整论文数据库维护在 [data/papers.csv](data/papers.csv)。本次从本地 `pdfs/` 文件夹索引了 **161 篇唯一收录论文**。重复文件按 DOI/标题折叠；未纳入主表的相关应用论文记录在 [data/skipped.csv](data/skipped.csv)，完整 PDF 盘点在 [data/pdf_inventory.csv](data/pdf_inventory.csv)。

### 线性盲解混

| 年份 | 标题 | 出版源 | 方法 | 代码 | 笔记 |
|---:|---|---|---|---|---|
| 2026 | [A Hyperspectral Unmixing Method Based on Matrix Spiral Scanning Mamba](https://doi.org/10.1109/ICAACE69793.2026.11508730) | 2026 9th International Conference on Advanced Algorithms and Control Engineering (ICAACE) | 线性盲解混; Mamba; 状态空间模型; 螺旋扫描 | TBD | [中文笔记](notes/zh-CN/2026_icaace_matrix-spiral-scanning-mamba.md) |
| 2026 | [GGCT-Net: A Dual-Branch Gated Graph Convolution and Grouped Cross-Attention Transformer Network for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2026.3668181) | IEEE Transactions on Geoscience and Remote Sensing | 线性盲解混; Transformer; 图正则; 注意力 | TBD | [中文笔记](notes/zh-CN/2026_tgrs_ggct-net-dual-branch-gated-graph-convolution-grouped.md) |
| 2026 | [Hyperspectral Image Synthesis Through Blind Unmixing Dictionary and Deep Diffusion Models](https://doi.org/10.1109/LGRS.2025.3646054) | IEEE Geoscience and Remote Sensing Letters, vol. 23 | 线性盲解混; 深度生成式解混; 图像合成 | [GitHub](https://github.com/martinapastorino/HSI_DDPM) | [中文笔记](notes/zh-CN/2026_grsl_hyperspectral-image-synthesis-through-blind-unmixing-dictionary-and-deep-diffusion-models.md) |
| 2026 | [Hyperspectral Unmixing Using Frequency-Adaptive Convolutional-Mamba Network](https://doi.org/10.1109/JSTARS.2026.3677880) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | 线性盲解混; Mamba; 光谱变异 | [GitHub](https://github.com/flyzzie/FACM) | [中文笔记](notes/zh-CN/2026_jstars_hyperspectral-unmixing-frequency-adaptive-convolutional-mamba-network.md) |
| 2026 | [MS^2AE-Net: A Multiscale Spectral-Spatial Autoencoder Network for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2026.3662051) | IEEE Transactions on Geoscience and Remote Sensing | 线性盲解混; 自编码器; 多尺度 | TBD | [中文笔记](notes/zh-CN/2026_tgrs_ms2ae-net-multiscale-spectral-spatial-autoencoder-network-hyperspectral.md) |
| 2026 | [Physics-Guided Vision Transformer Network With Tokens Complementarity for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2026.3676520) | IEEE Transactions on Geoscience and Remote Sensing | 线性盲解混; Transformer; 张量; 展开网络 | TBD | [中文笔记](notes/zh-CN/2026_tgrs_physics-guided-vision-transformer-network-tokens-complementarity-hyperspectral.md) |
| 2026 | [Preprocessing Algorithm Leveraging Geometric Modeling for Scale Correction in Hyperspectral Images for Improved Unmixing Performance](https://doi.org/10.1109/JSTARS.2026.3687834) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | 线性盲解混; KAN; 图正则; 光谱变异 | [GitHub](https://github.com/DMUPraveen/Perspecitve_Transform) | [中文笔记](notes/zh-CN/2026_jstars_preprocessing-algorithm-leveraging-geometric-modeling-scale-correction-hyperspectral.md) |
| 2025 | [A hyperspectral unmixing model for local distance-weighted variation](https://doi.org/10.1109/IGARSS55030.2025.11242428) | IEEE IGARSS | 线性盲解混; 光谱变异 | TBD | [中文笔记](notes/zh-CN/2025_igarss_hyperspectral-unmixing-model-local-distance-weighted-variation.md) |
| 2025 | [A Spectral-Spatial Attention Network for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3576479) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | 线性盲解混; 空谱注意力; denoising | [GitHub](https://github.com/xuanwentao) | [中文笔记](notes/zh-CN/2025_tgrs_spectral-spatial-attention-network-hyperspectral-unmixing.md) |
| 2025 | [A Two-Step Linear Mixing Model for Unmixing Under Hyperspectral Variability](https://doi.org/10.1109/IGARSS55030.2025.11243310) | IEEE IGARSS | 线性盲解混; 自编码器; 光谱变异; 注意力 | [GitHub](https://github.com/XanderHaijen/two_step_lmm) | [中文笔记](notes/zh-CN/2025_igarss_two-step-linear-mixing-model-unmixing-under-hyperspectral.md) |
| 2025 | [ACR-Net: Adaptive Correlation Refined Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3581078) | IEEE Transactions on Geoscience and Remote Sensing | 线性盲解混; 图正则; 注意力 | TBD | [中文笔记](notes/zh-CN/2025_tgrs_acr-net-adaptive-correlation-refined-hyperspectral-unmixing.md) |
| 2025 | [Adaptive Multiorder Graph Regularized NMF With Dual Sparsity for Hyperspectral Unmixing](https://doi.org/10.1109/JSTARS.2025.3602505) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | 线性盲解混; NMF; 图正则; 注意力 | TBD | [中文笔记](notes/zh-CN/2025_jstars_adaptive-multiorder-graph-regularized-nmf-dual-sparsity-hyperspectral.md) |
| 2025 | [An Endmember-Oriented Transformer Network for Bundle-Based Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3530642) | IEEE Transactions on Geoscience and Remote Sensing | 线性盲解混; 自编码器; Transformer; 端元束; 光谱变异 | TBD | [中文笔记](notes/zh-CN/2025_tgrs_endmember-oriented-transformer-network-bundle-hyperspectral-unmixing.md) |
| 2025 | [Band Mask Network with Spatial-Spectral Fusion for Hyperspectral Unmixing](https://doi.org/10.1109/ICAISISAS64483.2025.11051638) | TBD | 线性盲解混; 图正则 | TBD | [中文笔记](notes/zh-CN/2025_paper_band-mask-network-spatial-spectral-fusion-hyperspectral-unmixing.md) |
| 2025 | [Bundle-Based Adaptive Dynamic PSO for Spectral Variability-Aware Endmember Extraction in Hyperspectral Imagery](https://doi.org/10.1109/WHISPERS69515.2025.11501580) | WHISPERS | 线性盲解混; 图正则; 端元束; 光谱变异 | TBD | [中文笔记](notes/zh-CN/2025_whispers_bundle-adaptive-dynamic-pso-spectral-variability-aware-endmember.md) |
| 2025 | [Deep Diffusion Models and Unsupervised Hyperspectral Unmixing for Realistic Abundance Map Synthesis](https://doi.org/10.1109/CVPRW67362.2025.00286) | IEEE/CVF Conference on Computer Vision and Pattern Recognition | 线性盲解混; 扩散模型 | TBD | [中文笔记](notes/zh-CN/2025_ieee_deep-diffusion-models-unsupervised-hyperspectral-unmixing-realistic-abundance.md) |
| 2025 | [Digital Surface Model-Embedded Intrinsic Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3553823) | IEEE Transactions on Geoscience and Remote Sensing | 线性盲解混; 光谱变异 | TBD | [中文笔记](notes/zh-CN/2025_tgrs_digital-surface-model-embedded-intrinsic-hyperspectral-unmixing.md) |
| 2025 | [Dual Embedding Transformer Network for Hyperspectral Unmixing](https://doi.org/10.1109/JSTARS.2024.3523747) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | 线性盲解混; 自编码器; Transformer; 注意力; 多尺度 | TBD | [中文笔记](notes/zh-CN/2025_jstars_dual-embedding-transformer-network-hyperspectral-unmixing.md) |
| 2025 | [Efficient Progressive Mamba Model for Hyperspectral Sequence Unmixing](https://doi.org/10.1109/JSTARS.2025.3593442) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | 线性盲解混; Transformer; Mamba | [GitHub](https://github.com/Liujehong/ProMU) | [中文笔记](notes/zh-CN/2025_jstars_efficient-progressive-mamba-model-hyperspectral-sequence-unmixing.md) |
| 2025 | [Endmember Independence and Bilateral Filtering Regularizations for Blind Hyperspectral Unmixing](https://doi.org/10.1109/JSTARS.2025.3605626) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | 线性盲解混; 张量 | TBD | [中文笔记](notes/zh-CN/2025_jstars_endmember-independence-bilateral-filtering-regularizations-blind-hyperspectral-unmixing.md) |
| 2025 | [Endmember Variation via Swarm Intelligence Optimization for Spatially Weighted Sparse Hyperspectral Unmixing](https://doi.org/10.1109/ICVISP68610.2025.11451704) | TBD | 线性盲解混; 稀疏; ADMM; 光谱变异 | TBD | [中文笔记](notes/zh-CN/2025_paper_endmember-variation-swarm-intelligence-optimization-spatially-weighted-sparse.md) |
| 2025 | [Endmember-Free Hyperspectral Unmixing](https://doi.org/10.1109/JSTARS.2025.3605889) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | 线性盲解混 | TBD | [中文笔记](notes/zh-CN/2025_jstars_endmember-free-hyperspectral-unmixing.md) |
| 2025 | [Hyperspectral Blind Unmixing via First-Order Graph-Guided Sparse Nonnegative Matrix Factorization](https://doi.org/10.1109/ICVISP68610.2025.11451711) | 9th International Conference on Vision, Image and Signal Processing (ICVISP) | 线性盲解混; 图引导 稀疏 NMF | TBD | [中文笔记](notes/zh-CN/2025_icvisp_hyperspectral-blind-unmixing-via-fog-snmf.md) |
| 2025 | [Hyperspectral Unmixing Based on Dual-Graph Manifold Regularization: Joint Preservation of Spatial-Spectral Geometric Structure](https://doi.org/10.1109/ICGMRS66001.2025.11065202) | TBD | 线性盲解混; NMF; 图正则 | TBD | [中文笔记](notes/zh-CN/2025_paper_hyperspectral-unmixing-dual-graph-manifold-regularization-joint-preservation.md) |
| 2025 | [Hyperspectral Unmixing Using l2,1 Norm-Based Robust Deep Nonnegative Matrix Factorization](https://doi.org/10.1109/IGARSS55030.2025.11242377) | IEEE IGARSS | 线性盲解混; NMF | TBD | [中文笔记](notes/zh-CN/2025_igarss_hyperspectral-unmixing-l21-norm-robust-deep-nonnegative-matrix.md) |
| 2025 | [Hyperspectral Unmixing via Nonconvex Low-Rank and Weighted Sparsity Constraints](https://doi.org/10.1109/ICVISP68610.2025.11451684) | TBD | 线性盲解混; 稀疏; ADMM; 低秩 | TBD | [中文笔记](notes/zh-CN/2025_paper_hyperspectral-unmixing-nonconvex-low-rank-weighted-sparsity-constraints.md) |
| 2025 | [Improved Hyperspectral Unmixing Algorithm Involving the Multiplicative NMF Concept for Additive Mixing Model Dealing with Spectral Variability](https://doi.org/10.1109/IGARSS55030.2025.11243233) | IEEE IGARSS | 线性盲解混; NMF; 光谱变异 | TBD | [中文笔记](notes/zh-CN/2025_igarss_improved-hyperspectral-unmixing-algorithm-involving-multiplicative-nmf-concept.md) |
| 2025 | [Integrating 循环 KAN With SAM Adapter for Blind Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3635216) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | 线性盲解混; 循环 KAN; SAM 适配器 | TBD | [中文笔记](notes/zh-CN/2025_tgrs_integrating-recurrent-kan-sam-adapter-blind-hyperspectral-unmixing.md) |
| 2025 | [Linearized ADMM for Simplicial and Nonnegative Component Analyses](https://doi.org/10.1109/IEEECONF67917.2025.11443634) | TBD | 线性盲解混; NMF; ADMM | TBD | [中文笔记](notes/zh-CN/2025_paper_linearized-admm-simplicial-nonnegative-component-analyses.md) |
| 2025 | [Mamba-Enhanced Spatial-Spectral Feature Learning for Hyperspectral Unmixing](https://doi.org/10.1109/JSTARS.2025.3598873) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | 线性盲解混; Mamba | TBD | [中文笔记](notes/zh-CN/2025_jstars_mamba-enhanced-spatial-spectral-feature-learning-hyperspectral-unmixing.md) |
| 2025 | [Multiscale Spatial Graph-Regularized Hierarchical Sparse Unmixing Based on the Framelet Transform](https://doi.org/10.1109/TGRS.2025.3609968) | IEEE Transactions on Geoscience and Remote Sensing | 线性盲解混; 稀疏; 图正则; ADMM; 多尺度 | TBD | [中文笔记](notes/zh-CN/2025_tgrs_multiscale-spatial-graph-regularized-hierarchical-sparse-unmixing-framelet.md) |
| 2025 | [Noise-to-Abundance Translation: Unsupervised Hyperspectral Unmixing Based on Diffusion Models](https://doi.org/10.1109/TGRS.2025.3582029) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | 线性盲解混; 扩散模型; 自编码器 | TBD | [中文笔记](notes/zh-CN/2025_tgrs_noise-abundance-translation-unsupervised-hyperspectral-unmixing-diffusion-models.md) |
| 2025 | [On the Exclusion of Hyperspectral Sources](https://doi.org/10.1109/ICASSP43922.2022.9747709) | IEEE ICASSP | 线性盲解混; 图正则 | TBD | [中文笔记](notes/zh-CN/2025_icassp_exclusion-hyperspectral-sources.md) |
| 2025 | [REDU-Net: Robust and Efficient Dynamic Unfolding Network for Abundance Estimation](https://doi.org/10.1109/TGRS.2025.3540378) | IEEE Transactions on Geoscience and Remote Sensing | 线性盲解混; GAN; 注意力; 展开网络 | TBD | [中文笔记](notes/zh-CN/2025_tgrs_redu-net-robust-efficient-dynamic-unfolding-network-abundance.md) |
| 2025 | [Spectral Variability-Aware Cascaded Autoencoder for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3543566) | IEEE Transactions on Geoscience and Remote Sensing | 线性盲解混; 自编码器; 光谱变异 | TBD | [中文笔记](notes/zh-CN/2025_tgrs_spectral-variability-aware-cascaded-autoencoder-hyperspectral-unmixing.md) |
| 2025 | [SSLT-Net: A Spatial-Spectral Linear Transformer Unmixing Network for Hyperspectral Image](https://doi.org/10.1109/LGRS.2024.3514888) | IEEE Geoscience and Remote Sensing Letters | 线性盲解混; Transformer; 注意力; 多尺度 | [GitHub](https://github.com/HyperSystemAndImageProc/HyperspectrlUnmixing-SSLTNet) | [中文笔记](notes/zh-CN/2025_grsl_sslt-net-spatial-spectral-linear-transformer-unmixing-network.md) |
| 2025 | [Stationary Wavelet Convolutional Network With Generative Feature Learning for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2024.3516114) | IEEE Transactions on Geoscience and Remote Sensing | 线性盲解混; 图正则 | [GitHub](https://github.com/UPCGIT/SWC-Net) | [中文笔记](notes/zh-CN/2025_tgrs_stationary-wavelet-convolutional-network-generative-feature-learning-hyperspectral.md) |
| 2025 | [Superpixel-Based Autoencoder-Like Nonnegative Tensor Factorization for Hyperspectral Unmixing](TBD) | IEEE Transactions on Geoscience and Remote Sensing | 线性盲解混; 自编码器; NMF; 光谱变异; 低秩 | TBD | [中文笔记](notes/zh-CN/2025_tgrs_superpixel-autoencoder-like-nonnegative-tensor-factorization-hyperspectral-unmixing.md) |
| 2025 | [Synthesis of Abundance Maps Through Blind Hyperspectral Unmixing and Deep Diffusion Models](https://doi.org/10.1109/IGARSS55030.2025.11243836) | IEEE IGARSS | 线性盲解混; 扩散模型 | TBD | [中文笔记](notes/zh-CN/2025_igarss_synthesis-abundance-maps-through-blind-hyperspectral-unmixing-deep.md) |
| 2025 | [Transformer for Multitemporal Hyperspectral Image Unmixing](TBD) | TBD | 线性盲解混; Transformer; 注意力 | TBD | [中文笔记](notes/zh-CN/2025_paper_transformer-multitemporal-hyperspectral-image-unmixing.md) |
| 2025 | [UNMamba: Cascaded Spatial-Spectral Mamba for Blind Hyperspectral Unmixing](https://doi.org/10.1109/LGRS.2025.3545505) | IEEE Geoscience and Remote Sensing Letters | 线性盲解混; Mamba | [GitHub](https://github.com/Preston-Dong/UNMamba) | [中文笔记](notes/zh-CN/2025_grsl_unmamba-cascaded-spatial-spectral-mamba-blind-hyperspectral-unmixing.md) |
| 2025 | [Unrolling Plug-and-Play Network for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3540992) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | 线性盲解混; 展开式即插即用网络 | TBD | [中文笔记](notes/zh-CN/2025_tgrs_unrolling-plug-play-network-hyperspectral-unmixing.md) |
| 2025 | [Updated Homogeneity Criteria Based Low-Dimensional Representation for Hyperspectral Unmixing](TBD) | TBD | 线性盲解混; NMF | TBD | [中文笔记](notes/zh-CN/2025_paper_updated-homogeneity-criteria-low-dimensional-representation-hyperspectral-unmixing.md) |
| 2025 | [URDM: Hyperspectral Unmixing Regularized by Diffusion Models](https://doi.org/10.1109/TIP.2025.3638151) | IEEE Transactions on Image Processing | 线性盲解混; 扩散模型; 图正则; ADMM | TBD | [中文笔记](notes/zh-CN/2025_tip_urdm-hyperspectral-unmixing-regularized-diffusion-models.md) |
| 2024 | [A Fast Sparse NMF Optimization Algorithm for Hyperspectral Unmixing](https://doi.org/10.1109/JSTARS.2023.3341583) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | 线性盲解混; NMF; 稀疏; 注意力 | TBD | [中文笔记](notes/zh-CN/2024_jstars_fast-sparse-nmf-optimization-algorithm-hyperspectral-unmixing.md) |
| 2024 | [A Generalized Multiscale Bundle-Based Hyperspectral Sparse Unmixing Algorithm](https://doi.org/10.1109/LGRS.2024.3358694) | IEEE Geoscience and Remote Sensing Letters | 线性盲解混; 稀疏; 端元束; 光谱变异; 多尺度 | [GitHub](https://github.com/lucayress/GMBUA) | [中文笔记](notes/zh-CN/2024_grsl_generalized-multiscale-bundle-hyperspectral-sparse-unmixing-algorithm.md) |
| 2024 | [A New ADMM-Based Hyperspectral Unmixing Algorithm Associated with a Linear Mixing Model Addressing Spectral Variability with a Multiplicative Structure](https://doi.org/10.1109/IGARSS53475.2024.10640925) | IEEE IGARSS | 线性盲解混; ADMM; 光谱变异 | TBD | [中文笔记](notes/zh-CN/2024_igarss_new-admm-hyperspectral-unmixing-algorithm-associated-linear-mixing.md) |
| 2024 | [A New Dual-Feature Fusion Network for Enhanced Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2024.3505292) | IEEE Transactions on Geoscience and Remote Sensing | 线性盲解混; 自编码器 | [GitHub](https://github.com/xuanwentao) | [中文笔记](notes/zh-CN/2024_tgrs_new-dual-feature-fusion-network-enhanced-hyperspectral-unmixing.md) |
| 2024 | [A Novel Endmember Bundle Extraction Framework for Capturing Endmember Variability by Dynamic Optimization](https://doi.org/10.1109/TGRS.2024.3354046) | IEEE Transactions on Geoscience and Remote Sensing | 线性盲解混; 图正则; 端元束; 光谱变异 | TBD | [中文笔记](notes/zh-CN/2024_tgrs_novel-endmember-bundle-extraction-framework-capturing-endmember-variability.md) |
| 2024 | [A Reversible Generative Network for Hyperspectral Unmixing With Spectral Variability](https://doi.org/10.1109/TGRS.2024.3403926) | IEEE Transactions on Geoscience and Remote Sensing | 线性盲解混; 光谱变异; 注意力 | [GitHub](https://github.com/Lab-PANbin/Rev-Net) | [中文笔记](notes/zh-CN/2024_tgrs_reversible-generative-network-hyperspectral-unmixing-spectral-variability.md) |
| 2024 | [A Spectral Variability Attention Autoencoder Network for Hyperspectral Unmixing](https://doi.org/10.1109/IGARSS53475.2024.10641672) | IEEE IGARSS | 线性盲解混; 自编码器; 光谱变异; 注意力 | TBD | [中文笔记](notes/zh-CN/2024_igarss_spectral-variability-attention-autoencoder-network-hyperspectral-unmixing.md) |
| 2024 | [Addressing Spectral Variability in Hyperspectral Unmixing with a Novel Linear Adaptive Additive Mixing Model and an Associated ADMM-Based Approach](https://doi.org/10.1109/M2GARSS57310.2024.10537424) | IEEE Mediterranean and Middle-East Geoscience and Remote Sensing Symposium | 线性盲解混; NMF; 图正则; ADMM; 光谱变异 | TBD | [中文笔记](notes/zh-CN/2024_ieee_addressing-spectral-variability-hyperspectral-unmixing-novel-linear-adaptive.md) |
| 2024 | [An ADMM-Based Approach Associated with a Linear Mixing Model Multiplicatively Tuned to Deal with Spectral Variability in Hyperspectral Unmixing](https://doi.org/10.1109/M2GARSS57310.2024.10537495) | IEEE Mediterranean and Middle-East Geoscience and Remote Sensing Symposium | 线性盲解混; ADMM; 光谱变异 | TBD | [中文笔记](notes/zh-CN/2024_ieee_admm-approach-associated-linear-mixing-model-multiplicatively-tuned.md) |
| 2024 | [An Admm-Based Hyperspectral Unmixing Algorithm For A Modified Almm Addressing Spectral Variability](https://doi.org/10.1109/M2GARSS57310.2024.10537333) | IEEE Mediterranean and Middle-East Geoscience and Remote Sensing Symposium | 线性盲解混; NMF; ADMM; 光谱变异 | TBD | [中文笔记](notes/zh-CN/2024_ieee_admm-hyperspectral-unmixing-algorithm-modified-almm-addressing-spectral.md) |
| 2024 | [Blind Unmixing Using Dispersion Model-Based Autoencoder to Address Spectral Variability](https://doi.org/10.1109/TGRS.2024.3399003) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | 线性盲解混; 色散模型; 光谱变异; 双流自编码器 | TBD | [中文笔记](notes/zh-CN/2024_tgrs_blind-unmixing-dispersion-model-autoencoder-address-spectral-variability.md) |
| 2024 | [Combinatorial Nonnegative Matrix-Tensor Factorization for Hyperspectral Unmixing Using a General lq Norm Regularization](https://doi.org/10.1109/JSTARS.2024.3392497) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | 线性盲解混; NMF; 稀疏; 张量; 注意力 | TBD | [中文笔记](notes/zh-CN/2024_jstars_combinatorial-nonnegative-matrix-tensor-factorization-hyperspectral-unmixing-general.md) |
| 2024 | [Comparative Analysis of Endmember Extraction Methods for Lithological Mapping Using Hyperspectral Imaging](https://doi.org/10.1109/MERCon63886.2024.10688782) | TBD | 线性盲解混; KAN | TBD | [中文笔记](notes/zh-CN/2024_paper_comparative-analysis-endmember-extraction-methods-lithological-mapping-hyperspectral.md) |
| 2024 | [Deep Attention-Guided Spatial-Spectral Network for Hyperspectral Image Unmixing](https://doi.org/10.1109/LGRS.2023.3345959) | IEEE Geoscience and Remote Sensing Letters | 线性盲解混; 自编码器; 注意力 | TBD | [中文笔记](notes/zh-CN/2024_grsl_deep-attention-guided-spatial-spectral-network-hyperspectral-image.md) |
| 2024 | [DSFC-AE: A New Hyperspectral Unmixing Method Based on Deep Shared Fully Connected Autoencoder](https://doi.org/10.1109/JSTARS.2024.3450856) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | 线性盲解混; 自编码器; 图正则; 光谱变异 | TBD | [中文笔记](notes/zh-CN/2024_jstars_dsfc-ae-new-hyperspectral-unmixing-method-deep-shared.md) |
| 2024 | [DSSU: Dual-Stage Sparse Unmixing for Asynchronous Mixed Signal of Infrared Targets](https://doi.org/10.1109/TGRS.2024.3490539) | IEEE Transactions on Geoscience and Remote Sensing | 线性盲解混; 稀疏 | TBD | [中文笔记](notes/zh-CN/2024_tgrs_dssu-dual-stage-sparse-unmixing-asynchronous-mixed-signal.md) |
| 2024 | [Endmember Distinguished Low-Rank and Sparse Representation for Hyperspectral Unmixing](https://doi.org/10.1109/IGARSS53475.2024.10641266) | IEEE IGARSS | 线性盲解混; 稀疏; ADMM; 低秩 | TBD | [中文笔记](notes/zh-CN/2024_igarss_endmember-distinguished-low-rank-sparse-representation-hyperspectral-unmixing.md) |
| 2024 | [Feedback Information-Guided Spectral Variability Attention Network for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2024.3452323) | IEEE Transactions on Geoscience and Remote Sensing | 线性盲解混; 自编码器; 光谱变异; 注意力 | TBD | [中文笔记](notes/zh-CN/2024_tgrs_feedback-information-guided-spectral-variability-attention-network-hyperspectral.md) |
| 2024 | [Frank-Wolfe Algorithm for Simplicial and Nonnegative Component Analysis](https://doi.org/10.1109/SAM60225.2024.10636440) | TBD | 线性盲解混; NMF | TBD | [中文笔记](notes/zh-CN/2024_paper_frank-wolfe-algorithm-simplicial-nonnegative-component-analysis.md) |
| 2024 | [Graph Laplacian Regularization and Local Collaborative Sparse Regression Based on Superpixel Segmentation for Hyperspectral Imagery](https://doi.org/10.1109/IGARSS53475.2024.10640874) | IEEE IGARSS | 线性盲解混; 稀疏; 图正则; ADMM; 注意力 | TBD | [中文笔记](notes/zh-CN/2024_igarss_graph-laplacian-regularization-local-collaborative-sparse-regression-superpixel.md) |
| 2024 | [Hyperspectral Unmixing Based on Chaotic Sequence Optimization of Lp Norm](https://doi.org/10.1109/LGRS.2024.3425839) | IEEE Geoscience and Remote Sensing Letters | 线性盲解混; NMF; 稀疏 | TBD | [中文笔记](notes/zh-CN/2024_grsl_hyperspectral-unmixing-chaotic-sequence-optimization-lp-norm.md) |
| 2024 | [Hyperspectral Unmixing Using Reweighted Unidirectional TV Low-Rank NTF With Multiple-Factor Collaboration Regularization](https://doi.org/10.1109/JSTARS.2024.3392833) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | 线性盲解混; 稀疏; 低秩; 张量 | TBD | [中文笔记](notes/zh-CN/2024_jstars_hyperspectral-unmixing-reweighted-unidirectional-tv-low-rank-ntf.md) |
| 2024 | [Hyperspectral Unmixing With Row-Sparsity Enhancement: A Difference-of-Convex Approach](https://doi.org/10.1109/APSIPAASC63619.2025.10849210) | TBD | 线性盲解混; KAN; 稀疏; GAN | TBD | [中文笔记](notes/zh-CN/2024_paper_hyperspectral-unmixing-row-sparsity-enhancement-difference-convex-approach.md) |
| 2024 | [Locally-Rank-One-Based Joint Unmixing and Demosaicing Methods for Snapshot Spectral Images. Part II: A Filtering-Based Framework](https://doi.org/10.1109/TCI.2024.3402441) | IEEE Transactions on Computational Imaging | 线性盲解混; 低秩 | TBD | [中文笔记](notes/zh-CN/2024_tci_locally-rank-one-joint-unmixing-demosaicing-methods-snapshot.md) |
| 2024 | [MAT-Net: Multiscale Aggregation Transformer Network for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2024.3494795) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | 线性盲解混; 多尺度 aggregation Transformer | TBD | [中文笔记](notes/zh-CN/2024_tgrs_mat-net-multiscale-aggregation-transformer-network-hyperspectral-unmixing.md) |
| 2024 | [MSCC-ViT:A Multiscale Visual-Transformer Network Using Convolution Crossing Attention for Hyperspectral Unmixing](https://doi.org/10.1109/JSTARS.2024.3465227) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | 线性盲解混; Transformer; 注意力; 多尺度 | TBD | [中文笔记](notes/zh-CN/2024_jstars_mscc-vit-multiscale-visual-transformer-network-convolution-crossing.md) |
| 2024 | [Multiple Endmember Extraction Using Spatial-Spectral Information](https://doi.org/10.1109/SPIC62469.2024.10691535) | TBD | 线性盲解混; 光谱变异 | TBD | [中文笔记](notes/zh-CN/2024_paper_multiple-endmember-extraction-spatial-spectral-information.md) |
| 2024 | [On-the-Fly Spectral Unmixing for Real-Time Hyperspectral Data Analysis](https://doi.org/10.1109/WHISPERS65427.2024.10876536) | WHISPERS | 线性盲解混 | TBD | [中文笔记](notes/zh-CN/2024_whispers_fly-spectral-unmixing-real-time-hyperspectral-data-analysis.md) |
| 2024 | [Optimal Transport Based Hyperspectral Unmixing for Highly Mixed Observations](https://doi.org/10.1109/WHISPERS65427.2024.10876524) | WHISPERS | 线性盲解混; 自编码器; NMF | TBD | [中文笔记](notes/zh-CN/2024_whispers_optimal-transport-hyperspectral-unmixing-highly-mixed-observations.md) |
| 2024 | [Pixel-to-Abundance Translation: Conditional Generative Adversarial Networks Based on Patch Transformer for Hyperspectral Unmixing](https://doi.org/10.1109/JSTARS.2024.3368286) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | 线性盲解混; Transformer; GAN; 注意力 | TBD | [中文笔记](notes/zh-CN/2024_jstars_pixel-abundance-translation-conditional-generative-adversarial-networks-patch.md) |
| 2024 | [Plug-and-Play Prior for Sparse Hyperspectral Image Unmixing](https://doi.org/10.1109/ICCWAMTIP64812.2024.10873727) | IEEE Transactions on Image Processing | 线性盲解混; 稀疏; ADMM; 即插即用 | TBD | [中文笔记](notes/zh-CN/2024_tip_plug-play-prior-sparse-hyperspectral-image-unmixing.md) |
| 2024 | [Probabilistic Simplex Component Analysis via Variational Auto-Encoding](https://doi.org/10.1109/ICASSP48485.2024.10448368) | IEEE ICASSP | 线性盲解混; GAN | TBD | [中文笔记](notes/zh-CN/2024_icassp_probabilistic-simplex-component-analysis-variational-auto-encoding.md) |
| 2024 | [Robust Multiscale Spectral-Spatial Regularized Sparse Unmixing for Hyperspectral Imagery](https://doi.org/10.1109/JSTARS.2023.3337130) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | 线性盲解混; 稀疏; 多尺度 | TBD | [中文笔记](notes/zh-CN/2024_jstars_robust-multiscale-spectral-spatial-regularized-sparse-unmixing-hyperspectral.md) |
| 2024 | [SpACNN-LDVAE: Spatial Attention Convolutional Latent Dirichlet Variational Autoencoder for Hyperspectral Pixel Unmixing](https://doi.org/10.1109/IGARSS53475.2024.10640940) | IEEE IGARSS | 线性盲解混; 自编码器; NMF; 注意力 | TBD | [中文笔记](notes/zh-CN/2024_igarss_spacnn-ldvae-spatial-attention-convolutional-latent-dirichlet-variational.md) |
| 2024 | [Toward Robust Hyperspectral Unmixing: Mixed Noise Modeling and Image-Domain Regularization](https://doi.org/10.1109/JSTARS.2024.3379558) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | 线性盲解混; 稀疏; GAN | TBD | [中文笔记](notes/zh-CN/2024_jstars_toward-robust-hyperspectral-unmixing-mixed-noise-modeling-image.md) |
| 2024 | [Transformer-Enhanced CNN Based on Intensive Feature for Hyperspectral Unmixing](https://doi.org/10.1109/LGRS.2024.3485899) | IEEE Geoscience and Remote Sensing Letters | 线性盲解混; 自编码器; Transformer; 稀疏; GAN | TBD | [中文笔记](notes/zh-CN/2024_grsl_transformer-enhanced-cnn-intensive-feature-hyperspectral-unmixing.md) |
| 2024 | [Two-Stage Evolutionary Algorithm Based on Subspace Specified Searching for Hyperspectral Endmember Extraction](https://doi.org/10.1109/JSTARS.2023.3333955) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | 线性盲解混; 图正则 | TBD | [中文笔记](notes/zh-CN/2024_jstars_two-stage-evolutionary-algorithm-subspace-specified-searching-hyperspectral.md) |
| 2024 | [Unidirectional Local-Attention Autoencoder Network for Spectral Variability Unmixing](https://doi.org/10.1109/TGRS.2024.3375598) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | 线性盲解混; 光谱变异; local-注意力 自编码器 | TBD | [中文笔记](notes/zh-CN/2024_tgrs_unidirectional-local-attention-autoencoder-network-spectral-variability-unmixing.md) |
| 2024 | [UnmixDiff: Unmixing-Based Diffusion Model for Hyperspectral Image Synthesis](https://doi.org/10.1109/TGRS.2024.3425517) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | 线性盲解混; unmixing-based 扩散模型; 图像合成 | [GitHub](https://github.com/yuyang95/UnmixingDM) | [中文笔记](notes/zh-CN/2024_tgrs_unmixdiff-unmixing-diffusion-model-hyperspectral-image-synthesis.md) |
| 2024 | [Unmixing Before Fusion: A Generalized Paradigm for Multi-Source-Based Hyperspectral Image Synthesis](https://doi.org/10.1109/CVPR52733.2024.00888) | IEEE/CVF Conference on Computer Vision and Pattern Recognition | 线性盲解混 | [link](https://hsi-synthesis.github.io/) | [中文笔记](notes/zh-CN/2024_ieee_unmixing-before-fusion-generalized-paradigm-multi-source-hyperspectral.md) |
| 2023 | [Multiview Spatial-Spectral Two-Stream Network for Hyperspectral Image Unmixing](https://doi.org/10.1109/TGRS.2023.3237556) | IEEE Transactions on Geoscience and Remote Sensing, vol. 61 | 线性盲解混; unsupervised 自编码器; spatial-spectral network | TBD | [中文笔记](notes/zh-CN/2023_tgrs_multiview-spatial-spectral-two-stream-network.md) |
| TBD | [Generating Synthetic Data to Train a Deep Unrolled Network for Hyperspectral Unmixing](TBD) | TBD | 线性盲解混; 自编码器; 稀疏 | TBD | [中文笔记](notes/zh-CN/tbd_paper_generating-synthetic-data-train-deep-unrolled-network-hyperspectral.md) |

### 线性非盲 / 半盲解混

| 年份 | 标题 | 出版源 | 方法 | 代码 | 笔记 |
|---:|---|---|---|---|---|
| 2026 | [A Multiscale Synergistic Attention Network With Initialized Endmembers for Hyperspectral Unmixing](https://doi.org/10.1109/LGRS.2026.3672340) | IEEE Geoscience and Remote Sensing Letters | 线性半盲/非盲解混; 自编码器; 注意力; 多尺度 | TBD | TBD |
| 2025 | [A New Fast Sparse Unmixing Algorithm Based on Adaptive Spectral Library Pruning and Nesterov Optimization](https://doi.org/10.1109/JSTARS.2025.3541257) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | 线性半盲/非盲解混; 稀疏; 图正则; 注意力 | TBD | TBD |
| 2025 | [Adaptive Multitask Autoencoder-Based Hyperspectral Unmixing Exploiting Auxiliary Data via Graph Associations](https://doi.org/10.1109/TGRS.2025.3551119) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | 线性辅助数据解混; 自适应多任务自编码器; 图关联 | TBD | TBD |
| 2025 | [Double-Weighted Spatial Low-Rank and Superpixel-Guided Adaptive Graph Laplacian Regularization for Sparse Hyperspectral Unmixing](https://doi.org/10.1109/TIM.2025.3548194) | IEEE Transactions on Instrumentation and Measurement | 线性半盲/非盲解混; 稀疏; 图正则; 低秩 | TBD | TBD |
| 2025 | [Dual-Branch Cross Weighting Network for Multimodal Hyperspectral Unmixing](https://doi.org/10.1109/LGRS.2025.3549218) | IEEE Geoscience and Remote Sensing Letters | 线性半盲/非盲解混; 自编码器; 注意力; 多模态 | TBD | TBD |
| 2025 | [Hyperspectral Sparse Unmixing Based on Dual-Population Cooperative Optimization](https://doi.org/10.1109/LGRS.2025.3545776) | IEEE Geoscience and Remote Sensing Letters | 线性半盲/非盲解混; NMF; 稀疏 | TBD | TBD |
| 2025 | [MSSF-Net: A Multimodal Spectral-Spatial Feature Fusion Network for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3563647) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | 线性多模态辅助解混; 多模态空谱融合 | TBD | TBD |
| 2025 | [Sparsity and Total Variation Constrained Multilayer Linear Unmixing for Hyperspectral Imagery](https://doi.org/10.1109/ICET64964.2025.11103336) | TBD | 线性半盲/非盲解混; NMF; 稀疏; 图正则; ADMM | TBD | TBD |
| 2024 | [An Informed ADMM-Based Approach for Hyperspectral Unmixing Addressing Additively-Adapted Spectral Variability](https://doi.org/10.1109/M2GARSS57310.2024.10537402) | IEEE Mediterranean and Middle-East Geoscience and Remote Sensing Symposium | 线性半盲/非盲解混; NMF; ADMM; 光谱变异 | TBD | TBD |
| 2024 | [Diffusion-Model-Based Hyperspectral Unmixing Using Spectral Prior Distribution](https://doi.org/10.1109/TGRS.2024.3408475) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | 线性非盲解混; 光谱库先验; 扩散模型 | TBD | TBD |
| 2024 | [Fast Semisupervised Unmixing Using Nonconvex Optimization](https://doi.org/10.1109/TGRS.2024.3440663) | IEEE Transactions on Geoscience and Remote Sensing | 线性半盲/非盲解混; 非凸优化 | TBD | TBD |
| 2024 | [Hyperspectral Pixel Unmixing With Latent Dirichlet Variational Autoencoder](https://doi.org/10.1109/TGRS.2024.3357589) | IEEE Transactions on Geoscience and Remote Sensing | 线性半盲/非盲解混; 自编码器 | TBD | TBD |
| 2024 | [Hyperspectral Unmixing Using Nonconvex Shrinkage and Total Variation](https://doi.org/10.1109/ICEEE62185.2024.10779271) | TBD | 线性半盲/非盲解混; 稀疏; ADMM; GAN | TBD | TBD |
| 2024 | [Mutual Incoherence and Relative Total Variation Regularizations for Blind Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2024.3388991) | IEEE Transactions on Geoscience and Remote Sensing | 线性半盲/非盲解混; KAN; NMF; 稀疏 | TBD | TBD |

### 非线性盲解混

| 年份 | 标题 | 出版源 | 方法 | 代码 | 笔记 |
|---:|---|---|---|---|---|
| 2026 | [A Swin Transformer-Based Hybrid U-Shape Network for Nonlinear Hyperspectral Unmixing](https://doi.org/10.1109/LGRS.2026.3681172) | IEEE Geoscience and Remote Sensing Letters | 非线性盲解混; Transformer; 注意力; 多尺度 | TBD | TBD |
| 2026 | [Fully Blind Hyperspectral Unmixing Without Explicit Mixing Models or Endmember Initialization](https://doi.org/10.1109/TGRS.2026.3671829) | IEEE Transactions on Geoscience and Remote Sensing | 非线性盲解混; 自编码器; Transformer | TBD | TBD |
| 2026 | [Neural Architecture Search With Spatial-Spectral Attention for Higher-Order Nonlinear Hyperspectral Unmixing](https://doi.org/10.1109/TNNLS.2026.3678170) | IEEE Transactions on Neural Networks and Learning Systems | 非线性盲解混; 自编码器; 稀疏; 注意力; 多尺度 | TBD | TBD |
| 2026 | [Overparameterized Nonnegative Tensor Factorization for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2026.3676754) | IEEE Transactions on Geoscience and Remote Sensing | 非线性盲解混; 低秩; 张量 | TBD | TBD |
| 2026 | [SSST-GAN: A Sampling-Based Spatial-Spectral Transformer and Generative Adversarial Network for Hyperspectral Unmixing](https://doi.org/10.1109/JSTARS.2026.3655512) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | 非线性盲解混; Transformer; 稀疏; GAN; 注意力 | TBD | TBD |
| 2026 | [Superpixel-Guided Matrix-Valued Kernel Functions for Multiscale Nonlinear Hyperspectral Unmixing](https://doi.org/10.1109/JSTARS.2025.3630142) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | 非线性盲解混; 稀疏; 多尺度; 核方法 | TBD | TBD |
| 2025 | [A Biobjective Model-Driven Autocoder for Blind Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3577325) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | 非线性盲解混; 双目标模型驱动自编码器; 核模型 | TBD | TBD |
| 2025 | [A Multiscale Autoencoder Framework for Hyperspectral Unmixing](https://doi.org/10.1109/ICICSP66564.2025.11338376) | TBD | 非线性盲解混; 自编码器; GAN; 注意力; 多尺度 | TBD | TBD |
| 2025 | [A Novel Bundle-Based Autoencoder for Hyperspectral Unmixing with Spectral Variability](https://doi.org/10.1109/IGARSS55030.2025.11242593) | IEEE IGARSS | 非线性盲解混; 自编码器; Transformer; 端元束; 光谱变异 | TBD | TBD |
| 2025 | [A Novel Hyperspectral Unmixing Approach Jointly Addressing Nonlinearity and Spectral Variability in Urban Environments](https://doi.org/10.1109/IGARSS55030.2025.11243933) | IEEE IGARSS | 非线性盲解混; NMF; 光谱变异 | TBD | TBD |
| 2025 | [DEAE: Diffusion-Enhanced Autoencoder Network for Unsupervised Nonlinear Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3608084) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | 非线性盲解混; 扩散增强自编码器; EMLM | TBD | TBD |
| 2025 | [Enhanced Spatial-Spectral Attention Network for Hyperspectral Image Unmixing](https://doi.org/10.1109/LGRS.2025.3551729) | IEEE Geoscience and Remote Sensing Letters | 非线性盲解混; 自编码器; GAN; 注意力; 多尺度 | TBD | TBD |
| 2025 | [Explainable dynamic spectral unmixing](https://doi.org/10.1109/IGARSS55030.2025.11243542) | IEEE IGARSS | 非线性盲解混; 注意力 | TBD | TBD |
| 2025 | [GAN Based Non-Linear Hyperspectral Unmixing Using Patch Transformer on Chandrayaan-2 IIRS Data](https://doi.org/10.1109/IGARSS55030.2025.11242941) | IEEE IGARSS | 非线性盲解混; 自编码器; Transformer; GAN | TBD | TBD |
| 2025 | [Nonlinear Blind Hyperspectral Unmixing Via Generalized Mixing Mechanism Fitting and Endmember Constraints](https://doi.org/10.1109/IGARSS55030.2025.11242663) | IEEE IGARSS | 非线性盲解混; 自编码器 | TBD | TBD |
| 2025 | [Pixel-Level and Global Similarity-Based Adversarial Autoencoder Network for Hyperspectral Unmixing](https://doi.org/10.1109/JSTARS.2025.3542228) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | 非线性盲解混; 自编码器; Transformer; GAN | TBD | TBD |
| 2025 | [Refined Tokens Vision Transformer Network for Hyperspectral Image Unmixing](https://doi.org/10.1109/IGARSS55030.2025.11243764) | IEEE IGARSS | 非线性盲解混; Transformer | TBD | TBD |
| 2025 | [Structure Low-Rank and Self-Representation Learning for Hyperspectral Nonlinear Unmixing](https://doi.org/10.1109/IGARSS55030.2025.11242895) | IEEE IGARSS | 非线性盲解混; NMF; 稀疏; 低秩 | TBD | TBD |
| 2024 | [A Two-Stream Stacked Autoencoder With Inter-Class Separability for Bilinear Hyperspectral Unmixing](https://doi.org/10.1109/TCI.2024.3369410) | IEEE Transactions on Computational Imaging | 非线性盲解混; 自编码器; 注意力; 多尺度; 双线性 | TBD | TBD |
| 2024 | [An Abundance-Guided Attention Network for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2024.3353259) | IEEE Transactions on Geoscience and Remote Sensing | 非线性盲解混; 图正则; 注意力; 核方法 | TBD | TBD |
| 2024 | [DAAN: A Deep Autoencoder-Based Augmented Network for Blind Multilinear Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2024.3381632) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | 非线性盲解混; 多线性混合模型; 增强自编码器 | TBD | TBD |
| 2024 | [Deep NMF and Autoencoder: A Comparative Analysis for Hyperspectral Unmixing Using Prisma Real Images](https://doi.org/10.1109/IGARSS53475.2024.10642930) | IEEE IGARSS | 非线性盲解混; 自编码器; NMF; 低秩 | TBD | TBD |
| 2024 | [EMLM-Net: An Extended Multilinear Mixing Model-Inspired Dual-Stream Network for Unsupervised Nonlinear Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2024.3363427) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | 非线性盲解混; EMLM 启发的双流网络; 展开式 ADMM | TBD | TBD |
| 2024 | [Hyperspectral Image Endmember Extraction Algorithm Based on Manifold Learning and Superpixel Feature Extraction](https://doi.org/10.1109/CISCE62493.2024.10653429) | TBD | 非线性盲解混 | TBD | TBD |
| 2024 | [Hyperspectral Unmixing Based on Multilinear Mixing Model Using Convolutional Autoencoders](https://doi.org/10.1109/TGRS.2024.3360714) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | 非线性盲解混; 多线性混合模型; 卷积自编码器 | TBD | TBD |
| 2024 | [Hyperspectral Unmixing via Multi-scale Representation by CNN-BiLSTM and Transformer Network](https://doi.org/10.1109/ICSIDP62679.2024.10868234) | TBD | 非线性盲解混; 自编码器; Transformer; 图正则 | TBD | TBD |
| 2024 | [Hyperspectral Unmixing With Multi-Scale Convolution Attention Network](https://doi.org/10.1109/JSTARS.2023.3335907) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | 非线性盲解混; 自编码器; 注意力 | TBD | TBD |
| 2024 | [Identifiable Solutions to Foreground Signature Extraction From Hyperspectral Images in an Intimate Mixing Scenario](https://doi.org/10.1109/ICASSP40776.2020.9053456) | IEEE ICASSP | 非线性盲解混 | TBD | TBD |
| 2024 | [Improving Spectral Unmixing Performance by Frequency Component Reduction](https://doi.org/10.1109/WHISPERS65427.2024.10876530) | WHISPERS | 非线性盲解混; Hapke; 双线性 | TBD | TBD |
| 2024 | [Multiscale Convolutional Mask Network for Hyperspectral Unmixing](https://doi.org/10.1109/JSTARS.2024.3352080) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | 非线性盲解混; 自编码器; 图正则; 光谱变异; 多尺度 | TBD | TBD |
| 2024 | [Proportional Perturbation Model for Hyperspectral Unmixing Accounting for Endmember Variability](https://doi.org/10.1109/LGRS.2024.3350889) | IEEE Geoscience and Remote Sensing Letters | 非线性盲解混; 光谱变异 | TBD | TBD |
| 2024 | [Semi-NMF Regularization-Based Autoencoder Training for Hyperspectral Unmixing](https://doi.org/10.1109/NCC60321.2024.10485752) | TBD | 非线性盲解混; 自编码器; NMF | TBD | TBD |
| 2024 | [Sparse Coding Inspired GAN for Hyperspectral Unmixing](https://doi.org/10.1109/WHISPERS65427.2024.10876499) | WHISPERS | 非线性盲解混; 稀疏; GAN | TBD | TBD |
| 2024 | [Spectral Variability Augmented Multilinear Mixing Model for Hyperspectral Nonlinear Unmixing](https://doi.org/10.1109/LGRS.2024.3482103) | IEEE Geoscience and Remote Sensing Letters | 非线性盲解混; 稀疏; 光谱变异; 低秩; 多线性 | TBD | TBD |
| 2024 | [Superpixel-Based Low-Rank Tensor Factorization for Blind Nonlinear Hyperspectral Unmixing](https://doi.org/10.1109/JSEN.2024.3373477) | TBD | 非线性盲解混; 光谱变异; 低秩; 张量; 多线性 | TBD | TBD |
| 2024 | [Two-Stream Autoencoder-Based Hyperspectral Unmixing Using Hapke Model](https://doi.org/10.1109/IGARSS53475.2024.10640399) | IEEE International Geoscience and Remote Sensing Symposium (IGARSS) | 非线性盲解混; Hapke 模型; 双流自编码器 | TBD | TBD |
| 2024 | [Unsupervised Nonlinear Hyperspectral Unmixing Based on an Extended Multilinear Mixing Model-Inspired Dual-Stream Network](https://doi.org/10.1109/IGARSS53475.2024.10641679) | IEEE IGARSS | 非线性盲解混; 自编码器; ADMM; 多线性; 双线性 | TBD | TBD |
| TBD | Maximum Correntropy-Based Kurtosis Regularization Constrained Non-negative Matrix Factorization For Hyperspectral Unmixing | TBD | 非线性盲解混; NMF; 稀疏 | TBD | TBD |

### 非线性非盲 / 半盲解混

| 年份 | 标题 | 出版源 | 方法 | 代码 | 笔记 |
|---:|---|---|---|---|---|
| 2026 | [A Physics-Guided Diffusion Unmixing Model for Global Lunar Mineral Abundance Mapping](https://doi.org/10.1109/JSTARS.2026.3657892) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | 非线性半盲/非盲解混; 扩散模型; 光谱变异; Hapke | TBD | TBD |
| 2026 | [AD-HKFCM: A Robust Nonlinear Spectral Variability-Aware Unmixing via Intra/Inter-Class Affinity Cohesion](https://doi.org/10.1109/JSTARS.2026.3659984) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | 非线性半盲/非盲解混; 光谱变异; 核方法 | TBD | TBD |
| 2025 | [Robust Sparse Unmixing via Continuous Mixed Norm to Address Mixed Noise](https://doi.org/10.1109/LGRS.2025.3548697) | IEEE Geoscience and Remote Sensing Letters | 非线性半盲/非盲解混; 稀疏; ADMM; 注意力 | TBD | TBD |
| 2024 | [A Multimodal Hyperspectral Unmixing Method Under Spectral Variability](https://doi.org/10.1109/IGARSS53475.2024.10641781) | IEEE IGARSS | 非线性半盲/非盲解混; 稀疏; 光谱变异; 注意力; 多模态 | TBD | TBD |
| 2024 | [A New Version of an Endmember-Guided Autoencoder (EGAE-V2) with Improved Architecture and Regularization by Correlation Between Ground Truths and Latent Activations](https://doi.org/10.1109/WHISPERS65427.2024.10876451) | WHISPERS | 非线性半盲/非盲解混; 自编码器; GAN | TBD | TBD |
| 2024 | [A Supervised Approach for Estimating Fractional Abundances of Binary Intimate Mixtures](https://doi.org/10.1109/JSTARS.2024.3387750) | IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing | 非线性半盲/非盲解混; 光谱变异 | TBD | TBD |
| 2024 | [Nonlinear Unmixing of Hyperspectral Images via Regularized Wasserstein Dictionary Learning](https://doi.org/10.1109/IGARSS53475.2024.10642450) | IEEE IGARSS | 非线性半盲/非盲解混; Wasserstein 字典学习 | TBD | TBD |
| 2024 | [Robust Blind Linear Unmixing for Correlated Multimodal Images in Medical Applications](https://doi.org/10.1109/URUCON63440.2024.10850209) | TBD | 非线性半盲/非盲解混; 稀疏; 图正则; 多模态 | TBD | TBD |
| 2024 | [Theoretical and Practical Progress in Hyperspectral Pixel Unmixing with Large Spectral Libraries from a Sparse Perspective](https://doi.org/10.1109/WHISPERS65427.2024.10876427) | WHISPERS | 非线性半盲/非盲解混; 稀疏 | TBD | TBD |

### 混合模型 / 跨模型解混

| 年份 | 标题 | 出版源 | 方法 | 代码 | 笔记 |
|---:|---|---|---|---|---|
| 2026 | [DTU-Net: A Multi-Scale Dilated Transformer Network for Nonlinear Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2026.3658361) | IEEE Transactions on Geoscience and Remote Sensing | 混合模型盲解混; 自编码器; Transformer; 注意力; 多尺度 | TBD | TBD |
| 2025 | [Hybrid Linear-Nonlinear Hyperspectral Unmixing of Homogeneous Solutions](https://doi.org/10.1109/ICECER65523.2025.11401230) | TBD | 混合模型盲解混; NMF; 双线性 | TBD | TBD |
| 2025 | [Hyperspectral Unmixing Network Based on Hybrid Spectral Variability Model](https://doi.org/10.1109/IGARSS55030.2025.11243760) | IEEE IGARSS | 混合模型盲解混; 自编码器; NMF; 稀疏; 光谱变异 | TBD | TBD |
| 2025 | Robust and Unified Semi-Supervised Unmixing of Hyperspectral Imaging for Linear and Multilinear Models | TBD | 混合模型半盲/非盲解混; 多线性 | TBD | TBD |
| 2024 | [A Regional Adaptive Autoencoder Network for Hyperspectral Unmixing](https://doi.org/10.1109/IAECST64597.2024.11117391) | TBD | 混合模型盲解混; 自编码器; 注意力 | TBD | TBD |
| 2024 | [AE-RED: A Hyperspectral Unmixing Framework Powered by Deep Autoencoder and Regularization by Denoising](https://doi.org/10.1109/TGRS.2024.3377472) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | 盲解混; 自编码器; 去噪正则; 支持非线性模型 | TBD | TBD |
| 2024 | [Hyperspectral Blind Unmixing Using a Double Deep Image Prior](https://doi.org/10.1109/TNNLS.2023.3294714) | IEEE Transactions on Neural Networks and Learning Systems, vol. 35, no. 11 | 盲解混; 双深度图像先验; 线性与非线性模型 | TBD | TBD |
| 2024 | [Spatial-Spectral Twin Autoencoders for Hyperspectral Unmixing Via Superpixel-Hypergraph-Augmented Feature Representation](https://doi.org/10.1109/IGARSS53475.2024.10642904) | IEEE IGARSS | 混合模型盲解混; 自编码器; 稀疏; 图正则; Hapke | TBD | TBD |
| TBD | [Unified Unsupervised Unmixing With Sparse Noise Estimation for Linear and Multilinear Models](https://doi.org/10.1109/LSP) | IEEE Signal Processing Letters | 混合模型盲解混; 稀疏噪声估计; 线性与多线性模型 | TBD | TBD |

### 综述、基准、数据集与工具

| 年份 | 标题 | 出版源 | 方法 | 代码 | 笔记 |
|---:|---|---|---|---|---|
| 2025 | [A Benchmark Linear Unmixing Dataset With Spectral Variability and Ground Truth](https://doi.org/10.1109/WHISPERS69515.2025.11501633) | WHISPERS | 综述/数据集/工具 | TBD | TBD |
| 2024 | [A Detailed Analysis of Datasets Used in HSI in the Context of Mixture Models for Unmixing](https://doi.org/10.1109/MERCon63886.2024.10689093) | TBD | 综述/数据集/工具 | TBD | TBD |
| 2024 | [A New Hyperspectral Unmixing Benchmark for Weak Signal Meat Contamination Detection](https://doi.org/10.1109/DICTA63115.2024.00088) | TBD | 综述/数据集/工具 | TBD | TBD |
| 2024 | [Evaluation of Hyperspectral Unmixing Methods: A Comparative Study for Very-High Spatial Resolution Hyperspectral Images](https://doi.org/10.1109/SSIAI59505.2024.10508656) | TBD | 综述/数据集/工具 | TBD | TBD |
| 2024 | [Image Processing and Machine Learning for Hyperspectral Unmixing: An Overview and the HySUPP Python Package](https://doi.org/10.1109/TGRS.2024.3393570) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | 综述与软件; 监督、半监督和盲线性解混 | [GitHub](https://github.com/BehnoodRasti/HySUPP) | TBD |

## 数据集

| 数据集 | 场景类型 | 真实值 | 常见用途 | 链接 |
|---|---|---|---|---|
| Samson | 遥感 | 端元 / 丰度 | 线性解混基准 | TBD |
| Jasper Ridge | 遥感 | 端元 / 丰度 | 线性解混基准 | TBD |
| Urban | 遥感 | 端元 / 丰度 | 线性解混基准 | TBD |
| Cuprite | 遥感 | 参考矿物 | 端元提取 / 矿物制图 | TBD |
| PRISMA | 遥感 | 当前条目未使用公开丰度真值 | 高光谱图像合成 / 丰度图生成 | TBD |
| USGS synthetic | 合成数据 | 端元 / 丰度 | 受控线性解混基准 | TBD |

## 实验记录

实验结果维护在 [data/benchmarks.csv](data/benchmarks.csv)。

| 论文 | 数据集 | 端元数 | 指标 | 结果 | 协议说明 |
|---|---|---:|---|---:|---|
| FoG-SNMF | USGS synthetic | 5 | SAD | 0.1105 / 0.0297 / 0.0065 | SNR 10 / 20 / 30 dB |
| FoG-SNMF | USGS synthetic | 5 | RMSE | 0.0791 / 0.0612 / 0.0224 | SNR 10 / 20 / 30 dB |
| FoG-SNMF | Samson | 3 | Mean SAD | 0.0506 | rock / tree / water |
| FoG-SNMF | Samson | 3 | RMSE | 0.2270 | rock / tree / water |
| SUMamba | Jasper Ridge | 4 | Mean SAD | 0.046 +/- 0.0018 | soil / tree / water / road |
| SUMamba | Jasper Ridge | 4 | RMSE | 0.061 +/- 0.0032 | 丰度估计 |
| SUMamba | Jasper Ridge | 4 | SAD by endmember | 0.056 / 0.050 / 0.031 / 0.046 | soil / tree / water / road |

常见指标：

- `SAD`：光谱角距离，常用于端元估计评估。
- `RMSE`：丰度重建误差。
- `SRE`：信号重建误差。
- `RE`：重建误差。

## 阅读笔记

英文模板：[notes/template.md](notes/template.md)

中文模板：[notes/zh-CN/template.md](notes/zh-CN/template.md)

## 有用链接

- [All-in-One-Image-Restoration-Survey](https://github.com/Harbinzzy/All-in-One-Image-Restoration-Survey)：本仓库结构参考。
- 后续可继续补充领域综述、基准 仓库、数据集主页和经典论文列表。

## 维护方式

添加论文时建议：

1. 在 [data/papers.csv](data/papers.csv) 添加一行。
2. 按 `mixing_model` 和 `supervision` 两个字段分类。
3. 重要论文添加英文和中文笔记。
4. 公开仓库中不上传出版社 PDF；优先放 DOI、arXiv、OpenReview 或作者项目页链接。
