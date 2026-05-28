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

二级标签继续记录 NMF、稀疏回归、贝叶斯推断、图正则、自编码器、扩散模型、Transformer、光谱变异、benchmark 等方法族。

## 论文

完整论文数据库维护在 [data/papers.csv](data/papers.csv)。重复文件和版本迭代论文按 DOI/标题折叠；早期版本记录在对应完整版本的笔记中。

### 线性盲解混

| 年份 | 标题 | Venue | 方法 | 代码 | 笔记 |
|---:|---|---|---|---|---|
| 2026 | [Hyperspectral Image Synthesis Through Blind Unmixing Dictionary and Deep Diffusion Models](https://doi.org/10.1109/LGRS.2025.3646054) | IEEE Geoscience and Remote Sensing Letters, vol. 23 | 盲线性解混字典 + 扩散模型；图像合成 | [GitHub](https://github.com/martinapastorino/HSI_DDPM) | [中文笔记](notes/zh-CN/2026_grsl_hyperspectral-image-synthesis-through-blind-unmixing-dictionary-and-deep-diffusion-models.md) |
| 2025 | [A Spectral-Spatial Attention Network for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3576479) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | linear blind unmixing; spectral-spatial attention; denoising | TBD | TBD |
| 2025 | [Hyperspectral Blind Unmixing via First-Order Graph-Guided Sparse Nonnegative Matrix Factorization](https://doi.org/10.1109/ICVISP68610.2025.11451711) | 9th International Conference on Vision, Image and Signal Processing (ICVISP) | 一阶图引导稀疏 NMF | TBD | [中文笔记](notes/zh-CN/2025_icvisp_hyperspectral-blind-unmixing-via-fog-snmf.md) |
| 2025 | [Integrating Recurrent-KAN With SAM Adapter for Blind Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3635216) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | linear blind unmixing; Recurrent-KAN; SAM adapter | TBD | TBD |
| 2025 | [Noise-to-Abundance Translation: Unsupervised Hyperspectral Unmixing Based on Diffusion Models](https://doi.org/10.1109/TGRS.2025.3582029) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | linear blind unmixing; diffusion model; autoencoder | TBD | TBD |
| 2025 | [Unrolling Plug-and-Play Network for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3540992) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | linear blind unmixing; unrolled plug-and-play network | TBD | TBD |
| 2024 | [Blind Unmixing Using Dispersion Model-Based Autoencoder to Address Spectral Variability](https://doi.org/10.1109/TGRS.2024.3399003) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | linear blind unmixing; dispersion model; spectral variability; two-stream autoencoder | TBD | TBD |
| 2024 | [MAT-Net: Multiscale Aggregation Transformer Network for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2024.3494795) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | linear blind unmixing; multiscale aggregation transformer | TBD | TBD |
| 2024 | [Unidirectional Local-Attention Autoencoder Network for Spectral Variability Unmixing](https://doi.org/10.1109/TGRS.2024.3375598) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | linear blind unmixing; spectral variability; local-attention autoencoder | TBD | TBD |
| 2024 | [UnmixDiff: Unmixing-Based Diffusion Model for Hyperspectral Image Synthesis](https://doi.org/10.1109/TGRS.2024.3425517) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | linear blind unmixing; unmixing-based diffusion; image synthesis | TBD | TBD |
| 2023 | [Multiview Spatial-Spectral Two-Stream Network for Hyperspectral Image Unmixing](https://doi.org/10.1109/TGRS.2023.3237556) | IEEE Transactions on Geoscience and Remote Sensing, vol. 61 | 无监督 AE/RNN 多视角空间-光谱网络 | TBD | [中文笔记](notes/zh-CN/2023_tgrs_multiview-spatial-spectral-two-stream-network.md) |

### 线性非盲 / 半盲解混

| 年份 | 标题 | Venue | 方法 | 代码 | 笔记 |
|---:|---|---|---|---|---|
| 2025 | [Adaptive Multitask Autoencoder-Based Hyperspectral Unmixing Exploiting Auxiliary Data via Graph Associations](https://doi.org/10.1109/TGRS.2025.3551119) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | linear unmixing with auxiliary data; adaptive multitask autoencoder; graph associations | TBD | TBD |
| 2025 | [MSSF-Net: A Multimodal Spectral-Spatial Feature Fusion Network for Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3563647) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | linear unmixing with auxiliary modality; multimodal spectral-spatial fusion | TBD | TBD |
| 2024 | [Diffusion-Model-Based Hyperspectral Unmixing Using Spectral Prior Distribution](https://doi.org/10.1109/TGRS.2024.3408475) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | 光谱库先验 + 扩散模型半盲解混 | TBD | TBD |

### 非线性盲解混

| 年份 | 标题 | Venue | 方法 | 代码 | 笔记 |
|---:|---|---|---|---|---|
| 2025 | [A Biobjective Model-Driven Autocoder for Blind Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3577325) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | nonlinear blind unmixing; biobjective model-driven autoencoder; kernel model | TBD | TBD |
| 2025 | [DEAE: Diffusion-Enhanced Autoencoder Network for Unsupervised Nonlinear Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2025.3608084) | IEEE Transactions on Geoscience and Remote Sensing, vol. 63 | nonlinear blind unmixing; diffusion-enhanced autoencoder; EMLM | TBD | TBD |
| 2024 | [DAAN: A Deep Autoencoder-Based Augmented Network for Blind Multilinear Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2024.3381632) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | 多线性混合模型 + 增广自编码器 | TBD | TBD |
| 2024 | [EMLM-Net: An Extended Multilinear Mixing Model-Inspired Dual-Stream Network for Unsupervised Nonlinear Hyperspectral Unmixing](https://doi.org/10.1109/TGRS.2024.3363427) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | EMLM 启发双流网络 + ADMM 展开 | TBD | TBD |
| 2024 | [Hyperspectral Unmixing Based on Multilinear Mixing Model Using Convolutional Autoencoders](https://doi.org/10.1109/TGRS.2024.3360714) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | nonlinear blind unmixing; multilinear mixing model; convolutional autoencoder | TBD | TBD |
| 2024 | [Two-Stream Autoencoder-Based Hyperspectral Unmixing Using Hapke Model](https://doi.org/10.1109/IGARSS53475.2024.10640399) | IEEE International Geoscience and Remote Sensing Symposium (IGARSS) | nonlinear blind unmixing; Hapke model; two-stream autoencoder | TBD | TBD |

### 非线性非盲解混

| 年份 | 标题 | Venue | 方法 | 代码 | 笔记 |
|---:|---|---|---|---|---|
| TBD | TBD | TBD | TBD | TBD | TBD |

### 综述与工具

| 年份 | 标题 | Venue | 方法 | 代码 | 笔记 |
|---:|---|---|---|---|---|
| 2024 | [AE-RED: A Hyperspectral Unmixing Framework Powered by Deep Autoencoder and Regularization by Denoising](https://doi.org/10.1109/TGRS.2024.3377472) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | blind unmixing; autoencoder; regularization by denoising; nonlinear-capable | TBD | TBD |
| 2024 | [Hyperspectral Blind Unmixing Using a Double Deep Image Prior](https://doi.org/10.1109/TNNLS.2023.3294714) | IEEE Transactions on Neural Networks and Learning Systems, vol. 35, no. 11 | blind unmixing; double deep image prior; linear and nonlinear models | TBD | TBD |
| 2024 | [Image Processing and Machine Learning for Hyperspectral Unmixing: An Overview and the HySUPP Python Package](https://doi.org/10.1109/TGRS.2024.3393570) | IEEE Transactions on Geoscience and Remote Sensing, vol. 62 | 综述与 HySUPP Python 工具包 | [GitHub](https://github.com/BehnoodRasti/HySUPP) | TBD |

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
- 后续可继续补充领域综述、benchmark 仓库、数据集主页和经典论文列表。

## 维护方式

添加论文时建议：

1. 在 [data/papers.csv](data/papers.csv) 添加一行。
2. 按 `mixing_model` 和 `supervision` 两个字段分类。
3. 重要论文添加英文和中文笔记。
4. 公开仓库中不上传出版社 PDF；优先放 DOI、arXiv、OpenReview 或作者项目页链接。

