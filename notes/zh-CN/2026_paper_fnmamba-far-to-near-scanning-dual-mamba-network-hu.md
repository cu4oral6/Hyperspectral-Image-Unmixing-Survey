# FNMamba: A Far-to-Near Scanning Dual Mamba Network for Hyperspectral Image Unmixing

## 元信息

- **年份**：2026
- **出版源**：TBD
- **作者**：Lin Qi; Yili Zeng; Ying Sun; Feng Gao; Junyu Dong
- **论文**：TBD
- **代码**：TBD
- **项目页**：TBD
- **本地 PDF**：../../pdfs/FNMamba__A_Far_to_Near_Scanning_Dual_Mamba_Network_for_Hyperspectral_Image_Unmixing.pdf
- **数据集**：Jasper Ridge；Samson
- **标签**：线性，盲解混，Mamba，状态空间模型，自编码器，空谱建模，Jasper Ridge，Samson

## 速读要点

- **这篇论文讲了什么**：FNMamba 是一个双分支 Mamba 解混网络，把 far-to-near 空间扫描和分组光谱 Mamba 结合起来，用于估计丰度和端元。
- **是不是线性盲解混**：是。它不预先给定端元，而是从 HSI 中学习丰度和端元；解码器是线性端元矩阵形式，因此本仓库归为线性盲解混。
- **用了哪些数据集**：Jasper Ridge 和 Samson。
- **实验效果怎么样**：Jasper Ridge 上 mean SAD 最优，但 mean RMSE 不是最优；Samson 上 mean SAD 和 mean RMSE 都是对比表中最优。

## 一句话总结

FNMamba 用面向解混任务设计的远到近空间扫描和分组光谱序列建模，把 Mamba 引入线性盲高光谱解混的端元/丰度估计。

## 问题

深度盲解混方法通常依赖 CNN、注意力或 Transformer 来融合空间和光谱信息，但这些结构要么计算量较高，要么扫描/建模方式不一定贴合高光谱 patch 与光谱序列。论文认为 Mamba/状态空间模型有线性复杂度优势，不过用于解混时需要重新设计空间 token 顺序和光谱分组方式。

## 方法

- 总体结构：类似自编码器的盲解混网络，包含空间 Mamba 分支、光谱 Mamba 分支、丰度估计头，以及以端元矩阵形式存在的线性解码器。
- FNSM：Far-to-Near Spatial Mamba，把空间 patch token 按从远到近的顺序扫描，希望先引入较大范围上下文，再聚焦目标像元邻域，从而增强丰度图的空间一致性。
- GSMM：Grouped Spectral Mamba Module，把光谱波段分组后做序列建模，兼顾相邻波段连续性和跨波段长程依赖。
- 训练：使用重构损失和稀疏正则；消融实验显示两阶段训练对 RMSE 稳定性影响很大，稀疏正则对 SAD 有明显帮助。

## 实验

- 数据集：Jasper Ridge 和 Samson。
- 指标：端元 SAD 与丰度 RMSE。论文表格数值单位为 x10^-2，本仓库 benchmark CSV 中换算为小数。
- 对比方法：VCA、l1/2-NMF、EndNet、CNN-AEU、TANet、A2SAN、DPCM-HAEM。
- Jasper Ridge：100 x 100，去除水汽/大气影响后 198 个波段，4 个端元 tree / water / soil / road。FNMamba mean SAD 为 0.0340、mean RMSE 为 0.0807；mean SAD 最优，tree 和 water 的 RMSE 最优，但 TANet 的 mean RMSE 0.0754 更低。
- Samson：95 x 95，156 个波段，波长范围 401-889 nm，3 个端元 soil / tree / water。FNMamba mean SAD 为 0.0207、mean RMSE 为 0.0502，二者都是表中最优。

## 优点

- 空间扫描和光谱分组都围绕高光谱解混任务设计，而不是直接套通用视觉扫描。
- Samson 上 SAD 和 RMSE 同时领先，结果比较扎实。
- 消融实验说明两阶段训练、稀疏正则、空间邻域大小和光谱 token 分组都会影响效果。

## 局限 / 问题

- 当前 PDF 和公开检索都未确认 DOI、正式出版源、官方论文页或代码链接。
- 实验只覆盖 Jasper Ridge 和 Samson 两个经典小数据集，缺少 Urban、Cuprite、APEX 或更大农业/真实场景验证。
- Jasper Ridge 的丰度 RMSE 并非最佳，因此评价时要区分端元估计和丰度估计。
- 模型结构和训练策略较多，没有代码时复现难度偏高。

## 和我的工作有什么关系

- 适合放进 2025-2026 年 Mamba 解混方法对比：UNMamba、SUMamba、FACM、ProMU、Mamba-enhanced 空谱模型等。
- far-to-near 扫描可以作为 patch 级丰度估计的一种空间排序设计，值得和中心优先螺旋、普通 raster、Hilbert 或可学习扫描顺序比较。
- 分组光谱 Mamba 对降低 Transformer 式光谱建模成本有参考价值。

## BibTeX

```bibtex
@article{qi2026fnmamba,
  title={FNMamba: A Far-to-Near Scanning Dual Mamba Network for Hyperspectral Image Unmixing},
  author={Qi, Lin and Zeng, Yili and Sun, Ying and Gao, Feng and Dong, Junyu},
  year={2026},
  note={Venue and DOI not verified}
}
```
