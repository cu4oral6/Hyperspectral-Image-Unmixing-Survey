# Hyperspectral Unmixing of Hyperspectral Data Gathered Using an UAV

## 元信息

- **年份**：2025
- **出版源**：Vilnius University doctoral dissertation
- **作者**：Vytautas Paura
- **论文**：https://doi.org/10.15388/vu.thesis.828
- **代码**：https://github.com/VytautasPau/HUBenchmark
- **项目 / 数据集**：https://doi.org/10.5281/zenodo.13856357
- **本地 PDF**：../../pdfs/Hyperspectral unmixing of hyperspectral data gathered using an UAV.pdf
- **数据集**：BFHUD; DC Mall; Samson; APEX; USGS synthetic; IEEE GRSS synthetic
- **标签**：linear, blind, UAV, U-Net, benchmark, dataset, BFHUD
- **笔记状态**：基于本地 PDF 速读

## 速读要点

- **这篇论文讲了什么**：这篇博士论文构建了 UAV 农业高光谱解混数据集 BFHUD、HU benchmark 流程，并提出 U-Net 式无监督解混模型 HUNET。
- **是不是线性盲解混**：大体可以按线性盲解混收录。HUNET 从 HSI 中无监督估计端元和丰度，benchmark 也评估了多种线性稀疏/NMF 解混算法。
- **用了哪些数据集**：BFHUD、DC Mall、Samson、APEX、USGS/IEEE GRSS 合成数据。
- **实验效果怎么样**：BFHUD 上 HUNET 的 RE/RMSE 优于 Transformer baseline（0.0754/0.3625 对 0.3129/0.5054），但 SAD 更差；Samson 也有 RE/RMSE 优势；DC Mall 的 RMSE/SAD 更好但 RE 更差。

## 一句话总结

这篇论文同时提供 UAV 农业 HU 数据集/基准和一个 U-Net 式盲解混模型，对做真实农业场景解混很有参考价值。

## 问题

开放 HU 基准多来自卫星或机载经典场景，低空 UAV 农业高光谱数据较少。论文围绕数据采集、benchmark 和模型设计解决这一空缺。

## 方法

- 采集蓝莓田 UAV 高光谱数据并发布 BFHUD。
- 用 VCA 和 RMSE 最近端元分配构造六类近似真值。
- 设计端元鲁棒性、噪声鲁棒性、图像尺寸敏感性三类 benchmark。
- 提出 HUNET，使用 U-Net 式无监督结构，并结合重构、SAD 和 cosine similarity loss。

## 实验

- BFHUD：3 个 UAV cube，宽 1024，长度约 2815-3177，224 个波段，六类包括 bare soil、blueberries、grass、shadow、water/wet soil、other。
- benchmark 算法：SUnSAL、SUnSAL-TV、S2WSU、CNMF、R-CoNMF、SGSNMF、RSNMF、ALMM、HUNET。
- 合成 benchmark：组合 IEEE GRSS 风格图案与 USGS 光谱做鲁棒性测试。
- HUNET 对比：在 BFHUD、DC Mall、Samson 上与 Transformer HU 模型比较。
- 结果：SUnSAL 在端元鲁棒性 benchmark 中最强；RSNMF/SUnSAL 在噪声和尺寸测试中表现突出；HUNET 提升 BFHUD 和 Samson 的重构误差，但 SAD 并不总是更好。

## 优点

- 给线性盲解混补充了 UAV 农业场景数据。
- 有 benchmark 仓库和数据集 DOI。
- 同时覆盖传统 HU 算法和新的深度模型。

## 局限 / 问题

- BFHUD 的真值是 VCA 近似生成，不是直接材料测量。
- HUNET 对重构指标更友好，但 SAD 不稳定。
- 作为博士论文，内容很宽，和期刊方法横向比较时要注意实验协议差异。

## 和我的工作有什么关系

如果要做 UAV/农业 HU 或设计鲁棒性实验，BFHUD 和 HUBenchmark 都值得优先看。

## BibTeX

```bibtex
@phdthesis{paura2025uav,
  title={Hyperspectral Unmixing of Hyperspectral Data Gathered Using an UAV},
  author={Paura, Vytautas},
  school={Vilnius University},
  year={2025},
  doi={10.15388/vu.thesis.828}
}
```
