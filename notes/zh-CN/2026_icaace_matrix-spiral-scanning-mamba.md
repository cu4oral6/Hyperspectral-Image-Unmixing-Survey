# A Hyperspectral Unmixing Method Based on Matrix Spiral Scanning Mamba

## 元信息

- **年份**：2026
- **会议**：2026 9th International Conference on Advanced Algorithms and Control Engineering (ICAACE)
- **作者**：Haoyan Deng
- **论文**：https://doi.org/10.1109/ICAACE69793.2026.11508730
- **代码**：TBD
- **项目页**：TBD
- **本地 PDF**：../../pdfs/A Hyperspectral Unmixing Method Based on Matrix Spiral Scanning Mamba.pdf
- **数据集**：Jasper Ridge
- **标签**：线性，盲解混，Mamba，状态空间模型，螺旋扫描，空谱建模，Jasper Ridge

## 速读要点

- **这篇论文讲了什么**：SUMamba 把 Mamba 改造成更适合高光谱解混的空谱模型：空间上围绕中心像元做矩阵螺旋扫描，光谱上用双向 SSM 建模波段依赖。
- **是不是线性盲解混**：是。按本仓库分类，它属于线性盲解混：不预先给定端元光谱，而是从高光谱图像中估计端元和丰度，并以线性/重构式解混设置为主。
- **用了哪些数据集**：Jasper Ridge。
- **实验效果怎么样**：Jasper Ridge：Mean SAD 0.046 +/- 0.0018，RMSE 0.061 +/- 0.0032；已抽取表中最优。

## 一句话总结

SUMamba 把 Mamba 改造成更适合高光谱解混的空谱模型：空间上围绕中心像元做矩阵螺旋扫描，光谱上用双向 SSM 建模波段依赖。

## 问题

Mamba/状态空间模型适合用线性复杂度捕捉长程依赖，但原始 Mamba 更偏向一维序列；常见的单向、双向、交叉或多方向扫描并不是围绕高光谱 patch 中的中心像元设计的。对解混任务来说，中心像元是丰度估计的目标，它和邻域像元的关系会影响端元一致性与丰度图连续性，因此普通视觉扫描方式可能不够贴合任务结构。

## 方法

- 核心思想：以目标中心像元为起点或中心构造矩阵螺旋扫描序列，让空间 SSM 更强调中心像元与周围像元之间的相关性，再融合两个方向的扫描结果。
- 空间分支：先做降维、线性投影、深度可分离卷积和 SiLU 激活，然后进入使用矩阵螺旋扫描的 Spatial SSM (Spa-SSM)，最后做特征融合和 Layer Normalization。
- 光谱分支：提出 SpeAEM / SpeSSM，把光谱序列分组后做双向扫描；一个方向更关注连续波段相关性，另一个方向增强离散波段差异，从而兼顾端元光谱完整性和可区分性。
- 损失函数：使用重构 MSE 与 SAD 光谱角距离，并额外加入端元均值 MSE 约束，使端元矩阵更接近全局平均光谱分布。

## 实验

- 数据集：Jasper Ridge
- 对比方法：uDAS、DAEU、SIDAEU、CyCU-Net、MTAEU、UST-Net、A2SAN、UNMamba。
- 指标：端元 SAD 与丰度 RMSE。
- 主要结果：表格中 SUMamba 在 Jasper Ridge 上取得最好的整体结果，Mean SAD 为 0.046 +/- 0.0018，RMSE 为 0.061 +/- 0.0032；Soil / Tree / Water / Road 的 SAD 分别为 0.056、0.050、0.031、0.046。

## 优点

- 螺旋扫描机制和解混任务比较贴合，因为中心像元是目标，邻域像元提供空间连续性约束。
- Mamba/SSM 可以在较低计算复杂度下做长程空谱依赖建模，是 Transformer 之外的一条轻量路线。
- 和已有 Mamba 解混方法 UNMamba 直接比较，Mean SAD 与 RMSE 都更低。

## 局限 / 问题

- 摘要声称在四个 benchmark datasets 上验证，但正文抽取到的实验主要只有 Jasper Ridge。
- 论文篇幅较短，没有看到对螺旋扫描、光谱双向扫描、端元均值损失的细粒度消融。
- 未给出官方代码链接。
- 这里暂归为线性盲解混，因为实验和损失形式更接近常见重构式线性解混设置，但论文没有完整展开所有物理约束。

## 和我的工作有什么关系

- 可作为 Mamba 解混方向的一个短论文样例：重点不是简单套用 Mamba，而是重新设计扫描顺序以匹配高光谱局部结构。
- 适合和 UNMamba、Efficient Progressive Mamba、Frequency-Adaptive Convolutional-Mamba 等 2025-2026 年 Mamba 解混工作放在一起比较。
- “中心像元优先”的螺旋扫描思路，对设计保持丰度图局部连续性的空间模块有参考价值。

## BibTeX

```bibtex
@inproceedings{deng2026hyperspectral,
  title={A Hyperspectral Unmixing Method Based on Matrix Spiral Scanning Mamba},
  author={Deng, Haoyan},
  booktitle={2026 9th International Conference on Advanced Algorithms and Control Engineering (ICAACE)},
  year={2026},
  doi={10.1109/ICAACE69793.2026.11508730}
}
```
