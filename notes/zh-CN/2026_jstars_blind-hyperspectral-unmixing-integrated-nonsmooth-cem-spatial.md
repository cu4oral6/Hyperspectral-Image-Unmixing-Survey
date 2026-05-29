# Blind Hyperspectral Unmixing With Integrated Nonsmooth and CEM Spatial Constraints

## 元信息

- **年份**：2026
- **出版源**：IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing
- **作者**：Shaoquan Zhang; Kexing Li; Xinyi Zhou; Fan Li; Pengfei Lai; Lianhui Liang; Chengzhi Deng; Shengqian Wang
- **论文**：https://doi.org/10.1109/JSTARS.2026.3678308
- **代码**：TBD
- **项目页**：TBD
- **本地 PDF**：../../pdfs/Blind Hyperspectral Unmixing With Integrated Nonsmooth and CEM Spatial Constraints.pdf
- **数据集**：synthetic; real HSI datasets
- **标签**：linear, blind, NMF, CEM, spatial regularization, sparse, noise robust
- **笔记状态**：基于本地 PDF 速读

## 一句话总结

EISNMF 在线性盲解混的 l1-NMF 框架中加入端元非光滑约束和 CEM 引导的空间稀疏丰度正则，以提升噪声场景下的端元/丰度估计。

## 问题

噪声和异常值会同时破坏端元光谱与丰度图，而普通 NMF 往往缺少足够的空间连续性和目标感知稀疏约束。

## 方法

- 在 l1-NMF 中引入 nonsmooth matrix，增强端元稀疏性并抑制噪声。
- 用 CEM detector 与空间权重构造双权重稀疏丰度正则。
- 联合优化端元与丰度，在保留局部连续性的同时增强丰度稀疏表达。

## 实验

论文在合成和真实高光谱场景上用 SAD/RMSE 等指标评估，报告相比若干盲解混方法具有更好的噪声鲁棒性。

## 优点

- 是清晰的模型驱动 NMF 扩展。
- CEM 权重让空间正则带有目标感知含义。
- 适合作为噪声鲁棒盲解混基线。

## 局限 / 问题

- 本地 PDF 未发现官方代码。
- 如果要引用精确表格数值，还需要逐表核对。
- 主要仍假设线性盲解混。

## 和我的工作有什么关系

适合放进鲁棒 NMF/空间正则线性盲解混方向的近期基线。

## BibTeX

```bibtex
@article{zhang2026eisnmf,
  title={Blind Hyperspectral Unmixing With Integrated Nonsmooth and CEM Spatial Constraints},
  author={Shaoquan Zhang and Kexing Li and Xinyi Zhou and Fan Li and Pengfei Lai and Lianhui Liang and Chengzhi Deng and Shengqian Wang},
  journal={IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing},
  year={2026},
  doi={10.1109/JSTARS.2026.3678308}
}
```
