# Hyperspectral Blind Unmixing via First-Order Graph-Guided Sparse Nonnegative Matrix Factorization

## 元信息

- **年份**：2025
- **Venue**：9th International Conference on Vision, Image and Signal Processing (ICVISP)
- **作者**：Xinyi Zhou; Shaoquan Zhang; Mengxiong Tang; Jiaqiang Zhou; Ye Wu; Fan Li; Chengzhi Deng
- **论文链接**：https://doi.org/10.1109/ICVISP68610.2025.11451711
- **代码链接**：TBD
- **本地 PDF**：../../pdfs/Hyperspectral_Blind_Unmixing_via_First-Order_Graph-Guided_Sparse_Nonnegative_Matrix_Factorization.pdf
- **数据集**：USGS synthetic; Samson
- **标签**：nmf, sparse, graph, spatial-spectral, blind, Samson

## 速读要点

- **这篇论文讲了什么**：论文提出 FoG-SNMF，在稀疏 NMF 盲解混框架中加入一阶图差分空间正则和双权重约束，以提升端元提取和丰度估计精度。
- **是不是线性盲解混**：是。按本仓库分类，它属于线性盲解混：不预先给定端元光谱，而是从高光谱图像中估计端元和丰度，并以线性/重构式解混设置为主。
- **用了哪些数据集**：USGS synthetic; Samson。
- **实验效果怎么样**：USGS synthetic：报告 10/20/30 dB 下的 SAD/RMSE；Samson：Mean SAD 0.0506，RMSE 0.2270。

## 一句话总结

论文提出 FoG-SNMF，在稀疏 NMF 盲解混框架中加入一阶图差分空间正则和双权重约束，以提升端元提取和丰度估计精度。

## 问题

标准 NMF 解混虽然天然满足非负性，也容易加入稀疏约束，但对高光谱图像中的空间拓扑关系利用不足。论文试图更好地建模相邻像元之间的空间结构，同时保持丰度稀疏性和平滑性。

## 方法

- 从线性混合模型和稀疏 NMF 出发。
- 构造一阶图差分算子，用于捕捉空间拓扑关系。
- 加入空间结构正则项和双权重稀疏正则项。
- 在非负约束和 sum-to-one 约束下联合优化端元矩阵和丰度矩阵。

## 实验

- 合成实验使用 USGS 光谱库，224 个波段，75 x 75 像素，5 个端元，并加入 10、20、30 dB 的白噪声。
- 真实实验使用 Samson 数据集，95 x 95 像素，156 个波段，3 个端元：rock、tree、water。
- 指标：端元使用 SAD，丰度使用 RMSE。
- FoG-SNMF 在 Samson 上报告 Mean SAD = 0.0506，RMSE = 0.2270。
- Baseline 包括 GLNMF、l1/2-NMF、TV-RSNMF、SSWNMF 和 SLRTF。

## 优点

- 是一个清晰的经典优化类 baseline，可用于和深度方法对照。
- 同时包含合成数据和真实数据实验。
- 表格给出了 SAD/RMSE 数值，适合放入 benchmark 记录。

## 局限 / 问题

- 需要确认是否有官方代码。
- 会议论文篇幅较短，具体实现和收敛细节可能有限。
- 方法基于线性混合假设，对非线性混合和光谱变异的处理较弱。

## 和我的工作有什么关系

- 可以作为空间图正则 + 稀疏 NMF 的传统方法基线。
- 适合作为 Samson 和 USGS synthetic 实验的 benchmark 条目。

## BibTeX

```bibtex
@inproceedings{zhou2025hyperspectral,
  title={Hyperspectral Blind Unmixing via First-Order Graph-Guided Sparse Nonnegative Matrix Factorization},
  author={Zhou, Xinyi and Zhang, Shaoquan and Tang, Mengxiong and Zhou, Jiaqiang and Wu, Ye and Li, Fan and Deng, Chengzhi},
  booktitle={9th International Conference on Vision, Image and Signal Processing (ICVISP)},
  year={2025},
  doi={10.1109/ICVISP68610.2025.11451711}
}
```

