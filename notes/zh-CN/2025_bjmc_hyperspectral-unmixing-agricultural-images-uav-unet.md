# Hyperspectral Unmixing of Agricultural Images Taken from UAV Using Adapted U-Net Architecture

## 元信息

- **年份**：2025
- **出版源**：Baltic Journal of Modern Computing, vol. 13, no. 3
- **作者**：Vytautas Paura; Virginijus Marcinkevicius
- **论文**：https://doi.org/10.22364/bjmc.2025.13.3.04
- **代码**：https://github.com/VytautasPau/UAVHyperspectral
- **项目 / 数据**：https://doi.org/10.5281/zenodo.13856357
- **本地 PDF**：../../pdfs/Hyperspectral Unmixing of Agricultural Images Taken from UAV Using Adapted U-Net Architecture.pdf
- **数据集**：APEX；DC Mall；Samson；Blueberry UAV
- **标签**：线性，盲解混，UAV，农业，U-Net，自编码器，benchmark，blueberry

## 速读要点

- **这篇论文讲了什么**：把 U-Net 风格自编码器改造成无监督高光谱解混模型，并扩展作者之前的 UAV 蓝莓田 benchmark。
- **是不是线性盲解混**：是。模型不使用真实丰度监督，通过学习端元和丰度重构输入 HSI。
- **用了哪些数据集**：APEX、DC Mall、Samson，以及 3 个 Blueberry UAV 大尺度数据 cube。
- **实验效果怎么样**：大多数数据集上 mRMSE、mSAD、RE 优于 Transformer HU baseline；DC Mall 的表现相对混合。

## 一句话总结

这篇论文把 U-Net 改成更实用的无监督线性解混自编码器，并把实验从经典小数据集扩展到农业 UAV 蓝莓田数据。

## 问题

农业 UAV 高光谱数据通常尺度很大、来自真实田间，且缺少干净丰度真值。只在 Samson 或 APEX 这类小数据集上验证，并不能说明方法适合 UAV 农业场景。

## 方法

- 以 U-Net 的多尺度编码思想为基础，但任务从分割改成解混。
- 将压缩特征拆成端元提取和丰度提取两个子网络。
- 用矩阵乘法重构 HSI，使模型输出可以解释为端元和丰度图。
- 训练损失包含重构误差、SAD 和 cosine similarity loss，用来减少端元冗余。
- 可选使用参考端元，但主要设置是无监督训练。

## 实验

- 数据集：APEX、DC Mall、Samson，以及三个 Blueberry UAV cube。
- 指标：mRMSE、mSAD、RE。
- 代表结果：APEX 为 0.4705/0.1737/0.0990，Samson 为 0.4301/0.1507/0.0526，Blueberry Cube 1 为 0.3112/0.2737/0.0752。
- 论文总结称，除 DC Mall 外，多数数据集 mean RMSE 比 Transformer baseline 约低 27%，RE 和 mSAD 平均也更低。

## 优点

- 直接面向农业 UAV 解混，而不只是经典小 benchmark。
- 代码和 Zenodo 数据集都给出了链接。
- 相比 Transformer baseline，模型需要调的结构超参数更少。

## 局限 / 问题

- Blueberry UAV 的真值由 VCA 近似生成，不是独立实测丰度。
- 超参数主要靠手工调节，论文也承认结果未必最优。
- DC Mall 上并非所有指标都提升，说明跨场景鲁棒性还有空间。

## 和我的工作有什么关系

- 适合农业 HU 和 UAV 尺度 benchmark 设计。
- 可以作为 U-Net 自编码器与 Transformer HU 的实用对比。
- Blueberry UAV 六类标签适合测试方法在真实大场景上的可用性。

## BibTeX

```bibtex
@article{paura2025hyperspectral,
  title={Hyperspectral Unmixing of Agricultural Images Taken from UAV Using Adapted U-Net Architecture},
  author={Paura, Vytautas and Marcinkevicius, Virginijus},
  journal={Baltic Journal of Modern Computing},
  volume={13},
  number={3},
  pages={624--640},
  year={2025},
  doi={10.22364/bjmc.2025.13.3.04}
}
```
