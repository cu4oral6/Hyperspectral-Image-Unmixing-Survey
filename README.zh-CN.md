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
  <a href="#阅读笔记">阅读笔记</a> |
  <a href="#维护方式">维护方式</a>
</p>

## 动态

- **2026-05-28**：添加 3 篇本地 PDF 的论文信息、DOI、代码链接和中文阅读笔记。
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

其中 `Y` 表示观测到的高光谱数据，`A` 表示端元矩阵，`S` 表示丰度矩阵，`N` 表示噪声或建模误差。实际解混任务通常还需要处理非线性混合、端元光谱变异、空间结构、稀疏先验、噪声退化以及真实标注不足等问题。

## 方法分类

- **经典优化方法**：NMF、稀疏回归、单纯形/几何方法、贝叶斯模型。
- **空间-光谱先验**：总变分、图正则、低秩建模、超像素先验。
- **非线性解混**：核方法、双线性/多线性模型、物理启发的非线性模型。
- **深度解混**：自编码器、CNN、Transformer、展开网络、自监督方法。
- **盲解混 / 无监督解混**：不依赖已知端元或丰度标注。
- **光谱变异建模**：端元束、变异感知字典、域适应。
- **鲁棒解混**：噪声、损坏、低信噪比或混合退化场景。
- **评测与基准**：合成数据、真实数据集、可复现实验协议。

## 论文

完整论文数据库维护在 [data/papers.csv](data/papers.csv)。本 README 只保留精选列表和快速入口。

### 2026

| 标题 | 发表 venue | 任务 | 代码 | 笔记 |
|---|---|---|---|---|
| [Hyperspectral Image Synthesis Through Blind Unmixing Dictionary and Deep Diffusion Models](https://doi.org/10.1109/LGRS.2025.3646054) | IEEE GRSL | 基于盲解混字典和扩散模型的高光谱图像合成 | [GitHub](https://github.com/martinapastorino/HSI_DDPM) | [中文笔记](notes/zh-CN/2026_grsl_hyperspectral-image-synthesis-through-blind-unmixing-dictionary-and-deep-diffusion-models.md) |

### 2025

| 标题 | 发表 venue | 任务 | 代码 | 笔记 |
|---|---|---|---|---|
| [Deep Diffusion Models and Unsupervised Hyperspectral Unmixing for Realistic Abundance Map Synthesis](https://doi.org/10.1109/CVPRW67362.2025.00286) | CVPRW | 基于盲解混和扩散模型的真实丰度图合成 | TBD | [中文笔记](notes/zh-CN/2025_cvprw_deep-diffusion-models-and-unsupervised-hyperspectral-unmixing.md) |
| [Hyperspectral Blind Unmixing via First-Order Graph-Guided Sparse Nonnegative Matrix Factorization](https://doi.org/10.1109/ICVISP68610.2025.11451711) | ICVISP | 一阶图引导稀疏 NMF 盲解混 | TBD | [中文笔记](notes/zh-CN/2025_icvisp_hyperspectral-blind-unmixing-via-fog-snmf.md) |

### 2024

| 标题 | 发表 venue | 任务 | 代码 | 笔记 |
|---|---|---|---|---|
| TBD | TBD | TBD | TBD | TBD |

### 2024 年以前

| 标题 | 发表 venue | 任务 | 代码 | 笔记 |
|---|---|---|---|---|
| TBD | TBD | TBD | TBD | TBD |

## 数据集

| 数据集 | 场景类型 | 真实值 | 常见用途 | 链接 |
|---|---|---|---|---|
| Samson | 遥感 | 端元 / 丰度 | 线性解混基准 | TBD |
| Jasper Ridge | 遥感 | 端元 / 丰度 | 线性解混基准 | TBD |
| Urban | 遥感 | 端元 / 丰度 | 线性解混基准 | TBD |
| Cuprite | 遥感 | 参考矿物 | 端元提取 / 矿物制图 | TBD |

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

建议命名方式：

```text
notes/zh-CN/YYYY_venue_short-title.md
```

## 有用链接

- [All-in-One-Image-Restoration-Survey](https://github.com/Harbinzzy/All-in-One-Image-Restoration-Survey)：本仓库结构参考。
- 后续可继续补充领域综述、benchmark 仓库、数据集主页和经典论文列表。

## 维护方式

添加论文时建议：

1. 在 [data/papers.csv](data/papers.csv) 添加一行。
2. 重要或已读论文，在 `notes/` 或 `notes/zh-CN/` 添加笔记。
3. 尽量补充 DOI、官方代码、项目主页、数据集和实验指标。
4. 公开仓库中不上传出版社 PDF；优先放 DOI、arXiv、OpenReview 或作者项目页链接。

推荐标签：

```text
classical, sparse, nmf, bayesian, spatial-spectral, nonlinear, deep, autoencoder,
transformer, unfolding, self-supervised, blind, spectral-variability, robust,
benchmark, survey
```

