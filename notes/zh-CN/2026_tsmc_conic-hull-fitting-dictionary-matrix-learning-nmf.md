# Conic Hull Fitting-Based Dictionary Matrix Learning for Nonnegative Matrix Factorization

## 元信息

- **年份**：2026
- **出版源**：IEEE Transactions on Systems, Man, and Cybernetics: Systems
- **作者**：Zhijie Lin; Zhaoshui He; Hao Liang; Wenqing Su; Beihai Tan; Ji Tan
- **论文**：https://doi.org/10.1109/TSMC.2026.3655184
- **代码**：TBD
- **项目页**：TBD
- **本地 PDF**：../../pdfs/Conic Hull Fitting-Based Dictionary Matrix Learning for Nonnegative Matrix Factorization.pdf
- **数据集**：synthetic; hyperspectral unmixing; facial parts learning
- **标签**：linear, blind, NMF, conic hull, dictionary learning, separability
- **笔记状态**：基于本地 PDF 速读

## 一句话总结

本文提出基于锥包拟合的 NMF 字典学习算法，放宽严格可分性假设，并把高光谱解混作为真实 NMF 应用之一。

## 问题

许多 extreme-ray NMF 方法依赖 1-sparse / separability 假设，但真实混合像元通常不满足纯像元条件。

## 方法

- 把 NMF 从几何上理解为正正交空间中的锥包拟合问题。
- 用 half-hyperplane identification 替代单纯的 extreme-ray 搜索。
- 提出 HICHF、EnhancedHICHF、ExtendedHICHF，并用 EVD 高效实现。

## 实验

实验包括非可分合成 NMF、真实部件学习任务和高光谱解混，并与已有 NMF 方法比较。

## 优点

- 很好地连接了 NMF 几何理论与 HU。
- 直接面向非可分情形。
- 算法解释性较强。

## 局限 / 问题

- HU 是应用之一，不是全文唯一重点。
- 本地 PDF 未发现官方代码。
- 若作为基准引用，需要进一步核对数据集和指标细节。

## 和我的工作有什么关系

适合用于讨论纯像元假设较弱时的 NMF 盲解混理论背景。

## BibTeX

```bibtex
@article{lin2026conic,
  title={Conic Hull Fitting-Based Dictionary Matrix Learning for Nonnegative Matrix Factorization},
  author={Zhijie Lin and Zhaoshui He and Hao Liang and Wenqing Su and Beihai Tan and Ji Tan},
  journal={IEEE Transactions on Systems, Man, and Cybernetics: Systems},
  year={2026},
  doi={10.1109/TSMC.2026.3655184}
}
```
