# Underdetermined Blind Source Separation via Weighted Simplex Shrinkage Regularization and Quantum Deep Image Prior

## 元信息

- **年份**：2026
- **出版源**：IEEE Transactions on Image Processing
- **作者**：Chia-Hsiang Lin; Si-Sheng Young
- **论文**：https://doi.org/10.1109/TIP.2026.3673957
- **代码**：TBD
- **项目页**：TBD
- **本地 PDF**：../../pdfs/Underdetermined Blind Source Separation via Weighted Simplex Shrinkage Regularization and Quantum Deep Image Prior.pdf
- **数据集**：synthetic; real MSI/HSI datasets
- **标签**：mixed, blind, multispectral unmixing, deep image prior, quantum, simplex
- **笔记状态**：基于本地 PDF 速读

## 一句话总结

GQ-mu 面向欠定多光谱解混，用 quantum deep image prior 生成虚拟 HSI 波段，再用 weighted simplex shrinkage 正则化盲源分离。

## 问题

当源数量超过多光谱观测波段数时，多光谱解混成为欠定问题，比常规高光谱解混更难。

## 方法

- 用 quantum deep image prior 做虚拟波段分裂，把 MSI 转成虚拟 HSI。
- 在虚拟 HSI 上执行 HU，恢复虚拟高光谱源。
- 基于丰度稀疏模式自适应控制 weighted simplex shrinkage，缓解病态问题。

## 实验

论文通过仿真和真实数据实验评估源恢复与丰度图，报告在欠定多光谱解混中具有实用效果。

## 优点

- 直接处理欠定 MSI/MU，而不只是标准 HU。
- 结合几何 simplex 正则和 deep image prior。
- 对低波段/传感器受限解混有启发。

## 局限 / 问题

- quantum DIP 部分复现和解释门槛较高。
- 本地 PDF 未发现官方代码。
- 横跨 MSI 与 HU，分类上属于混合模型而非纯 HU。

## 和我的工作有什么关系

适合用于思考少波段、欠定或多光谱解混问题。

## BibTeX

```bibtex
@article{lin2026gqmu,
  title={Underdetermined Blind Source Separation via Weighted Simplex Shrinkage Regularization and Quantum Deep Image Prior},
  author={Chia-Hsiang Lin and Si-Sheng Young},
  journal={IEEE Transactions on Image Processing},
  year={2026},
  doi={10.1109/TIP.2026.3673957}
}
```
