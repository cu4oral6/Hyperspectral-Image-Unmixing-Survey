# Multi-modal and multi-objective hyperspectral unmixing model based on multi-source data

## 元信息

- **年份**：2024
- **出版源**：Computers and Electronics in Agriculture
- **作者**：Jiewen Lin; Jian Chen
- **论文**：https://doi.org/10.1016/j.compag.2024.109505
- **代码**：TBD
- **项目页**：TBD
- **本地 PDF**：../../pdfs/1-s2.0-S0168169924008962-main.pdf
- **数据集**：MUUFL; Houston
- **标签**：linear, blind, multimodal, DSM, endmember-bundle, PSO, spectral-variability
- **笔记状态**：基于本地 PDF 速读

## 速读要点

- **这篇论文讲了什么**：提出 MMO-CDPSO-RSADRDSM，把 HSI 和 DSM 融入多目标粒子群优化，用于端元束提取。
- **是不是线性盲解混**：是。论文明确说主要关注线性混合模型，并从图像/DSM 数据中提取端元束，没有使用外部光谱库。
- **用了哪些数据集**：MUUFL 和 Houston，二者都带有 HSI 与 DSM/LiDAR 类辅助高程信息。
- **实验效果怎么样**：MUUFL 上 mRMSE 0.1853、re-min mSAD 0.0325，综合表中最优；Houston 上 mRMSE 0.1548、re-min mSAD 0.0341，其中 re-min mSAD 最优，但 mRMSE 不如 MOPSOSCD。

## 一句话总结

这篇论文用 DSM 辅助的多模态优化来改善光谱变异下的端元束提取。

## 问题

端元提取在光谱变异或相似光谱材料场景下容易不稳定。作者认为 DSM/高程信息可以辅助区分仅靠光谱难以分开的地物。

## 方法

- 用 HSI 光谱信息和 DSM 信息共同初始化、更新、筛选离散粒子群候选端元。
- 在决策空间 crowding distance 中引入相对光谱角距离和相对 DSM 距离。
- 通过多目标优化提取端元束，并使用 UCLS/FCLS 类重构评价。
- 目标是每类材料的端元束，而不是单一端元代表。

## 实验

- MUUFL：90 x 130 ROI，64 个波段，五类端元：roof、grass、tree、shadow、asphalt。
- Houston：170 x 170 ROI，144 个波段，四类端元：parking lot 1、parking lot 2、running track、healthy grass。
- 对比方法：MOPSOSCD、TSEA、IMPSO-EBE、DPSO、VCA。
- 指标：mRMSE、re-min mSAD、per-class SAD。
- 结果：MUUFL 的 mRMSE/re-min mSAD 为 0.1853/0.0325，提取 35 个端元；Houston 的 mRMSE/re-min mSAD 为 0.1548/0.0341，提取 36 个端元。Houston 中虽然 MOPSOSCD 的 mRMSE 更低，但本文方法的 re-min mSAD 和视觉端元束效果更好。
- 代码状态：本地 PDF 中未发现官方代码地址。

## 优点

- 明确把 HSI 与 DSM 多源数据用于盲端元束提取。
- 用端元束处理光谱变异，比单端元更贴合复杂场景。
- 在两个多模态遥感数据集上给出定量结果。

## 局限 / 问题

- 依赖可用且配准良好的 DSM。
- Houston 上 mRMSE 不是最优。
- 未核验到代码地址，复现需要重实现。

## 和我的工作有什么关系

如果关注多模态线性盲解混，尤其是利用高程/空间辅助信息处理端元变异，这篇值得纳入对比。

## BibTeX

```bibtex
@article{lin2024multimodal,
  title={Multi-modal and multi-objective hyperspectral unmixing model based on multi-source data},
  author={Lin, Jiewen and Chen, Jian},
  journal={Computers and Electronics in Agriculture},
  year={2024},
  doi={10.1016/j.compag.2024.109505}
}
```
