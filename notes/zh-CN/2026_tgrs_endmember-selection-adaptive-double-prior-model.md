# Endmember Selection With Adaptive Double Prior Model

## 元信息

- **年份**：2026
- **出版源**：IEEE Transactions on Geoscience and Remote Sensing
- **作者**：Rui Wu; Wenfei Luo; Lianru Gao; Longfei Ren; Hongmin Gao
- **论文**：https://doi.org/10.1109/TGRS.2026.3664867
- **代码**：https://github.com/spdelphi/Double-Prior
- **项目页**：TBD
- **本地 PDF**：../../pdfs/Endmember Selection With Adaptive Double Prior Model.pdf
- **数据集**：USGS synthetic; Cuprite; Urban; Jasper Ridge; Samson
- **标签**：linear, semi-supervised, sparse, spectral-library, prior, endmember-selection
- **笔记状态**：基于本地 PDF 速读

## 速读要点

- **这篇论文讲了什么**：提出 ADSU，用两个先验模型和自适应决策参数做稀疏解混端元选择，避免单一错误先验把解混结果带偏。
- **是不是线性盲解混**：不是。它是线性半监督/非盲稀疏解混，因为端元来自已知光谱库，并且使用外部先验权重。
- **用了哪些数据集**：基于 USGS 光谱库的两个模拟数据集，以及 Cuprite、Urban、Jasper Ridge、Samson。
- **实验效果怎么样**：ADSU 在多种先验错误场景下多数为最优或次优；在 Dataset 2 上整体分数最好；真实数据上能减轻错误先验导致的丰度图伪影。

## 一句话总结

ADSU 的核心是让稀疏解混不要完全信任单一先验，而是在两个先验模型之间自适应选择。

## 问题

稀疏解混依赖大光谱库，常用先验权重鼓励或抑制候选端元。但实际先验可能不完整甚至错误，单先验模型容易选错材料。

## 方法

- 从带非负约束的 weighted sparse unmixing 目标出发。
- 引入两组先验和决策参数，在优化过程中自适应混合。
- 使用 ADMM 风格求解，并分析错误先验下的鲁棒条件。
- 主模型放松丰度和为一约束，以适应端元选择和光谱变异。

## 实验

- 模拟数据：USGS 光谱库和合成丰度图，设置不同 SNR 与先验错误类型。
- 真实数据：Cuprite、Urban、Jasper Ridge、Samson。
- 指标：模拟数据用 SRE、RMSE；真实数据主要看丰度图和定性比较。
- 对比方法：SU/SUnSAL、WSU、JSpBLRU、BiJSpLRU、BMSPI、SUnCNN、LSU。
- 结果：论文报告 ADSU 在大多数先验场景下保持最优或次优；Dataset 2 上整体分数最好；Cuprite/Urban 上能减少错误先验带来的误选，Jasper Ridge/Samson 在先验可靠时表现稳定。
- 代码状态：PDF 中给出官方代码 `https://github.com/spdelphi/Double-Prior`。

## 优点

- 直接处理稀疏解混里“先验可能错”这个现实问题。
- 有理论分析、模拟实验和真实场景实验。
- 代码可用，复现条件好于多数新论文。

## 局限 / 问题

- 它不是盲解混，依赖光谱库和先验构造。
- 真实数据缺少完整丰度真值，评价偏定性。
- PDF 表格数值自动抽取不完整，精确表格后续需要视觉核对。

## 和我的工作有什么关系

如果研究方向涉及光谱库、稀疏解混或不可靠先验，这篇适合作为近期重点参考。

## BibTeX

```bibtex
@article{wu2026endmember,
  title={Endmember Selection With Adaptive Double Prior Model},
  author={Wu, Rui and Luo, Wenfei and Gao, Lianru and Ren, Longfei and Gao, Hongmin},
  journal={IEEE Transactions on Geoscience and Remote Sensing},
  year={2026},
  doi={10.1109/TGRS.2026.3664867}
}
```
