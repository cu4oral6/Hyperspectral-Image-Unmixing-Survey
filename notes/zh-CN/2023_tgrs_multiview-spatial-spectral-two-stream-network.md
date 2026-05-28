# Multiview Spatial-Spectral Two-Stream Network for Hyperspectral Image Unmixing

## 元信息

- **年份**：2023
- **Venue**：IEEE Transactions on Geoscience and Remote Sensing
- **作者**：Lin Qi; Zhenwei Chen; Feng Gao; Junyu Dong; Xinbo Gao; Qian Du
- **论文链接**：https://doi.org/10.1109/TGRS.2023.3237556
- **代码链接**：TBD
- **本地文件**：../../pdfs/Qi 等 - 2023 - Multiview spatial–spectral two-stream network for hyperspectral image unmixing.docx
- **数据集**：USGS synthetic; Urban; Jasper Ridge; Cuprite
- **分类**：线性盲解混
- **标签**：linear, blind, autoencoder, RNN, spatial-spectral, multiview, Urban, Jasper-Ridge, Cuprite

## 速读要点

- **这篇论文讲了什么**：论文提出 MSSS-Net，一种无监督自编码器式双流网络，用 RNN 同时建模多视角光谱分组和空间邻域信息，用于线性高光谱图像解混。
- **是不是线性盲解混**：是。按本仓库分类，它属于线性盲解混：不预先给定端元光谱，而是从高光谱图像中估计端元和丰度，并以线性/重构式解混设置为主。
- **用了哪些数据集**：USGS synthetic; Urban; Jasper Ridge; Cuprite。
- **实验效果怎么样**：在 USGS synthetic; Urban; Jasper Ridge; Cuprite 上，实验与解混基线比较，并报告重构、丰度或端元估计有所改善，评价指标包括 SAD/RMSE/MSE。

## 一句话总结

论文提出 MSSS-Net，一种无监督自编码器式双流网络，用 RNN 同时建模多视角光谱分组和空间邻域信息，用于线性高光谱图像解混。

## 问题

很多深度解混方法会利用空间上下文，但高光谱图像本身也包含大量窄波段光谱结构。论文希望在线性混合模型下，同时充分利用多视角光谱信息和局部空间结构。

## 方法

- 采用无监督 AE 解混框架。
- 构建空间流分支，提取像元及邻域 patch 的空间特征。
- 构建多视角光谱流分支，通过光谱分组利用不同波段视角。
- 使用级联双向和单向 RNN 编码器建模光谱与空间依赖。
- 两个 AE 分支共享 decoder，decoder 权重对应估计端元。
- 使用 SAD 相关重建损失，并加入丰度稀疏正则。

## 实验

- 合成数据：64 x 64 像素，5 个端元来自 USGS 光谱库，并设置不同 SNR 的高斯噪声。
- 真实数据：Urban、Jasper Ridge、Cuprite。
- 指标：SAD 和 RMSE。
- Baseline 包括 VCA、L1/2-NMF、Dgs-NMF，以及 EndNet、SNMF-Net、TANet、CNNAEU、MiSiC-Net、SSAE 等 AE-based 方法。

## 优点

- 是一篇典型的深度线性盲解混论文，问题设定清晰。
- 同时利用多视角光谱划分和空间邻域建模。
- 同时在合成数据和多个真实数据集上验证。

## 局限 / 问题

- 当前整理时未确认官方代码。
- 结构比普通 AE 或 NMF baseline 更复杂。
- 方法主要针对线性混合模型，对非线性混合和光谱变异仍需额外建模。

## 和我的工作有什么关系

- 可作为深度线性盲解混代表方法。
- 适合作为空间-光谱深度解混架构的比较对象。

## BibTeX

```bibtex
@article{qi2023multiview,
  title={Multiview Spatial-Spectral Two-Stream Network for Hyperspectral Image Unmixing},
  author={Qi, Lin and Chen, Zhenwei and Gao, Feng and Dong, Junyu and Gao, Xinbo and Du, Qian},
  journal={IEEE Transactions on Geoscience and Remote Sensing},
  year={2023},
  doi={10.1109/TGRS.2023.3237556}
}
```

