# GGCT-Net: A Dual-Branch Gated Graph Convolution and Grouped Cross-Attention Transformer Network for Hyperspectral Unmixing

## 元信息

- **年份**：2026
- **出版源**：IEEE Transactions on Geoscience and Remote Sensing
- **作者**：Qingfei Liu; Xiaodong Yu; Hongbin Dong; Shuying Zang
- **论文**：https://doi.org/10.1109/TGRS.2026.3668181
- **代码**：TBD
- **项目页**：TBD
- **本地 PDF**：../../pdfs/GGCT-Net A Dual-Branch Gated Graph Convolution and Grouped Cross-Attention Transformer Network for Hyperspectral Unmixing.pdf
- **数据集**：Simulated; Jasper Ridge; Samson; APEX; Ray-Tracing; Cuprite
- **标签**：linear, blind, deep-learning, unsupervised, graph-convolution, transformer, gated-attention, LMM
- **笔记状态**：基于本地 PDF 和用户提供摘要整理

## 速读要点

- **这篇论文讲了什么**：GGCT-Net 是一个双分支深度高光谱解混网络，把门控图卷积分支和分组交叉注意力 Transformer 分支结合起来，同时估计端元和丰度。
- **是不是线性盲解混**：在本仓库表格里可放入 linear blind / unsupervised 桶，因为它从图像中学习端元和丰度，并使用 LMM 式重构约束。更精确地说，它是 LMM 约束下的深度盲/无监督解混方法，不是 VCA、NMF、FCLSU、SUnSAL 这类传统线性解混算法。
- **用了哪些数据集**：Simulated、Jasper Ridge、Samson、APEX、Ray-Tracing、Cuprite。
- **实验效果怎么样**：多数数据集上报告了最优或较强的平均 aRMSE、aSAD 和 SRE，但运行时间明显高于若干深度学习基线。

## 一句话总结

GGCT-Net 通过超像素引导图卷积、空间-光谱交叉注意力和门控特征融合，在 LMM 重构约束下提升无监督高光谱解混的丰度估计和端元提取效果。

## 问题

论文针对近期深度解混模型的两个局限：CNN 擅长局部空谱特征，但难以关联“空间距离远、光谱很相似”的像素；Transformer 能建模长距离依赖，但容易把空间和光谱特征混在一起处理，缺少显式的空间/光谱解耦。

模型仍需要预先设定端元数量。论文实验设置中说明，端元数根据先验知识给定，是固定输入参数，并不是由模型自动估计。

## 方法

- **预处理**：先用 SLIC 超像素分割，把空间连续且光谱相似的像素聚合起来，为后续构图提供基础。
- **G-GCN 分支**：基于光谱相似性构图，使空间上相距较远但光谱相似的像素或区域也能交互；内部包含偏端元生成和偏丰度估计的子分支。
- **GCAF 模块**：门控交叉注意力融合模块，用于在端元子分支和丰度子分支之间交换信息，抑制冗余特征并强化有用交互。
- **GCA-Transformer 分支**：通过 SCAB 空间-光谱交叉注意力模块分别建模光谱注意力和空间注意力，再进行融合，用于捕获全局长距离依赖。
- **解码 / 重构**：网络估计丰度和端元后重构高光谱图像，训练损失包含重构损失和 KL 散度项。

因此，虽然论文的背景和部分数据生成依托 LMM 线性混合模型，网络编码器本身是非线性的深度特征提取器。

## 实验

| 数据集 | 尺寸 / 波段 | 端元 | Proposed 结果 |
| --- | --- | --- | --- |
| Simulated | 100 x 100，224 bands | Clay、Carbonate、Iron-oxide、Vegetation | mean aRMSE 0.06831，mean aSAD 0.02848，SRE 23.29 |
| Jasper Ridge | 100 x 100，224 bands，预处理后 198 bands | Tree、Water、Soil、Road | mean aRMSE 0.06039，mean aSAD 0.06447，SRE 19.7 |
| Samson | 95 x 95，156 bands | Soil、Tree、Water | mean aRMSE 0.06113，mean aSAD 0.05348，SRE 20.32 |
| APEX | 110 x 110，285 bands | Road、Soil、Tree、Water | mean aRMSE 0.1091，mean aSAD 0.07947，SRE 17.32 |
| Ray-Tracing | 20 x 20，216 bands，预处理后 185 bands | Soil、Weed、Tree | mean aRMSE 0.15945，mean aSAD 0.07432，SRE 18.48 |
| Cuprite | 250 x 190，224 bands，约 188 个有效波段 | 12 种矿物 | 只展示矿物丰度图；无真实丰度图，不能做 RMSE 式定量评价 |

论文对比了 DeepTrans、DGMSSU、CyCU-Net、UnDIP、TCCU-Net、EOT-Net 等方法。可视化结果强调 GGCT-Net 的丰度图边界更清晰、空间细节更好，端元谱曲线更接近参考光谱。计算效率表也显示了代价：GGCT-Net 的运行时间显著更长，例如 APEX 约 214.47 s，Ray-Tracing 约 97.58 s。

## 优点

- 把图建模和 Transformer 注意力结合起来，直接回应 CNN 局部性和 Transformer 空谱混合处理的问题。
- SCAB 显式拆分空间注意力和光谱注意力，比直接把所有特征当作同一种 token 更有针对性。
- 在模拟、经典真实场景、城市、果园 ray-tracing 和矿物制图数据上都报告了较强表现。
- Jasper Ridge 消融实验支持 GCAF 与 SCAB 的互补作用；两个模块同时使用时 RMSE/SAD 最优。

## 局限 / 问题

- 结构明显偏重，模块堆叠较多，运行时间高于多个对比方法。
- 端元数量不能自动估计，仍依赖先验设定。
- Cuprite 因缺少真实丰度图，主要依靠丰度分布图展示，定量证据有限。
- 创新主要在结构组合和模块设计，不是提出新的物理混合模型。
- 代码仍为 `TBD`，可复现性取决于后续是否公开官方实现。

## 和我的工作有什么关系

这篇论文适合作为“深度无监督高光谱解混 / 图卷积与 Transformer 结合的空间-光谱解混方法 / LMM 约束的深度盲解混方法”的代表。综述中不建议把它和 VCA、NMF、FCLSU、SUnSAL 等传统线性优化方法放在同一小类里，而应放在深度盲解混或深度空谱建模方法下讨论。

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
