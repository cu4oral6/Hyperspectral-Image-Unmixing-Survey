# MCDB-Net: Multiview Collaborative Dual-Branch Unmixing Network for Hyperspectral Images

## 元信息

- **年份**：2026
- **出版源**：IEEE Transactions on Geoscience and Remote Sensing
- **作者**：Lin Qi; Yao Wu; Feng Gao; Junyu Dong; Qian Du; Xinbo Gao
- **论文**：https://doi.org/10.1109/TGRS.2026.3672192
- **代码**：TBD
- **项目页**：TBD
- **本地 PDF**：../../pdfs/MCDB-Net_Multiview_Collaborative_Dual-Branch_Unmixing_Network_for_Hyperspectral_Images.pdf
- **数据集**：synthetic; Jasper Ridge; Samson; Cuprite
- **标签**：linear, blind, autoencoder, multiview, dual-branch, attention
- **笔记状态**：基于本地 PDF 速读

## 速读要点

- **这篇论文讲了什么**：MCDB-Net 是一个自编码器式高光谱解混网络，把像元光谱构造成多视角 spectral block，再用全视角分支和局部多视角分支共同估计丰度。
- **是不是线性盲解混**：是。论文明确以线性混合模型为基础，不使用外部光谱库输入，端元和丰度由 HSI 自身估计。
- **用了哪些数据集**：合成数据、Jasper Ridge、Samson、Cuprite。
- **实验效果怎么样**：合成噪声实验中整体优于深度基线；Jasper Ridge 端元平均 SAD 比最佳对比方法提升 1.46 个百分点；Samson 的整体端元/丰度估计最优；Cuprite 上端元提取表现较强。

## 一句话总结

MCDB-Net 通过多视角光谱块和局部/全局双分支协同，提升线性盲解混中的光谱特征利用率。

## 问题

不少 AE 解混方法主要从单一视角利用光谱，或者更强调空间特征。本文认为连续高维光谱带之间存在可利用的多视角关系，现有方法没有充分挖掘。

## 方法

- 用 AAP 或光谱仪驱动策略划分波段，并重排成多视角 spectral block。
- 全视角分支负责全谱注意力，局部多视角分支负责不同视角之间的局部交互。
- 通过 multiview abundance collaboration 模块动态融合两个分支的丰度估计。
- 损失函数包含重构 SAD 和 `l1/2` 丰度稀疏项。

## 实验

- 数据集：synthetic、Jasper Ridge、Samson、Cuprite。
- 指标：端元 SAD、丰度 RMSE。
- 对比方法：VCA、`L1/2`-NMF、EndNet、TANet、CNNAEU、MAT-Net、MSSR-Net。
- 结果：合成数据 20-60 dB SNR 下，MCDB-Net 在端元和丰度估计上均表现更稳；Jasper Ridge 提升最终端元分数并获得最佳整体丰度；Samson 获得最佳整体端元和丰度；Cuprite 对 Andradite、Kaolinite1、Montmorillonite、Nontronite 等端元提取较好。
- 代码状态：本地 PDF 中未发现官方代码地址。

## 优点

- 适合作为近期线性盲深度解混基线。
- 多视角 spectral block 思路清晰，并能和已有 multiview HU 工作衔接。
- 同时包含合成噪声和真实场景实验。

## 局限 / 问题

- PDF 文本层没有完整保留所有表格数值，精确 per-class SAD/RMSE 仍需视觉核对。
- 未核验到代码地址。
- 仍以线性重构为主，非线性混合不是重点。

## 和我的工作有什么关系

如果比较 Mamba、Transformer、多视角 AE 这类线性盲解混网络，可以把它作为近期代表方法。

## BibTeX

```bibtex
@article{qi2026mcdb,
  title={MCDB-Net: Multiview Collaborative Dual-Branch Unmixing Network for Hyperspectral Images},
  author={Qi, Lin and Wu, Yao and Gao, Feng and Dong, Junyu and Du, Qian and Gao, Xinbo},
  journal={IEEE Transactions on Geoscience and Remote Sensing},
  year={2026},
  doi={10.1109/TGRS.2026.3672192}
}
```
