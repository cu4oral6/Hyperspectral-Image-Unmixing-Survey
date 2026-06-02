# PICT-Net: A Transformer-Based Network with Prior Information Correction for Hyperspectral Image Unmixing

## 元信息

- **年份**：2025
- **出版源**：Remote Sensing, vol. 17, no. 5
- **作者**：Yiliang Zeng; Na Meng; Jinlin Zou; Wenbin Liu
- **论文**：https://doi.org/10.3390/rs17050869
- **代码**：TBD
- **项目页**：TBD
- **本地 PDF**：../../pdfs/PICT-NetA Transformer-Based Network with Prior Information Correction for Hyperspectral Image Unmixing.pdf
- **数据集**：Samson；APEX；Houston；MUUFL
- **标签**：线性，半监督，Transformer，prior information，空谱建模

## 速读要点

- **这篇论文讲了什么**：PICT-Net 是一个带先验信息校正的双分支 Transformer 解混网络，用预提取端元/纯像元信息修正网络特征。
- **是不是线性盲解混**：不是纯盲解混。它使用预提取端元先验，因此本仓库归为线性半监督/先验引导解混。
- **用了哪些数据集**：Samson、APEX、Houston、MUUFL。
- **实验效果怎么样**：在提取到的 RMSE 和 aSAD 表中，PICT-Net 都优于 CyCU-Net、EGU、DeepTrans、Swin-HU。

## 一句话总结

PICT-Net 把端元先验注入 Transformer 解混网络，用来增强端元稳定性和跨数据集鲁棒性。

## 问题

Transformer HU 模型可以保留空谱上下文，但在缺少可靠先验时可能不够稳定。论文认为，通过纯像元/端元先验对 Transformer 特征进行校正，可以提升可解释性和鲁棒性。

## 方法

- 双分支结构：上分支输入预提取端元先验，下分支用 Transformer 做特征提取和解混。
- 两个分支共享权重，使先验信息和图像特征可以交互。
- Transformer encoder 建模 patch 内长程依赖。
- 损失函数包含重构相关项和 SAD 光谱约束。

## 实验

- 数据集：Samson、APEX、Houston、MUUFL。
- 对比方法：CyCU-Net、EGU、DeepTrans、Swin-HU。
- 指标：丰度 RMSE 和端元 aSAD。
- PICT-Net 的 RMSE/aSAD：Samson 0.0531/0.0371，APEX 0.1136/0.0836，Houston 0.1500/0.1203，MUUFL 0.2457/0.0613。

## 优点

- 四个真实数据集上都有较强定量结果。
- 先验分支让端元稳定性的改进更容易解释。
- 和多个深度解混 baseline，尤其是 Transformer 类方法，做了直接比较。

## 局限 / 问题

- 依赖预提取端元先验，因此自主性弱于完全盲解混。
- 本地 PDF 未提供官方代码链接。
- 数据可用性说明主要指向第三方数据仓库。

## 和我的工作有什么关系

- 可作为先验引导 Transformer HU 的代表 baseline。
- 适合用来判断是否值得引入纯像元/端元先验。
- 四数据集表格可用于半监督 HU 方法的结果 sanity check。

## BibTeX

```bibtex
@article{zeng2025pictnet,
  title={PICT-Net: A Transformer-Based Network with Prior Information Correction for Hyperspectral Image Unmixing},
  author={Zeng, Yiliang and Meng, Na and Zou, Jinlin and Liu, Wenbin},
  journal={Remote Sensing},
  volume={17},
  number={5},
  pages={869},
  year={2025},
  doi={10.3390/rs17050869}
}
```
