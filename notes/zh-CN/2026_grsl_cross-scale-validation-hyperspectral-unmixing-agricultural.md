# Cross-Scale Validation of Hyperspectral Unmixing Over Agricultural Landscapes

## 元信息

- **年份**：2026
- **出版源**：IEEE Geoscience and Remote Sensing Letters
- **作者**：Haris Ampas; Konstantinos Karyotis; Pierre Guillevic; George Zalidis; Sophia Petridou
- **论文**：https://doi.org/10.1109/LGRS.2026.3687594
- **代码**：TBD
- **项目页**：TBD
- **本地 PDF**：../../pdfs/Cross-Scale Validation of Hyperspectral Unmixing Over Agricultural Landscapes.pdf
- **数据集**：Tanager-1 vineyard; VHR UAV imagery; field spectra
- **标签**：validation, agriculture, linear, mixed, Tanager-1, UAV, field-spectra
- **笔记状态**：基于本地 PDF 速读

## 速读要点

- **这篇论文讲了什么**：提出一个跨尺度验证流程，用 UAV 植被覆盖、实测端元光谱来验证卫星高光谱解混得到的土壤/植被丰度。
- **是不是线性盲解混**：不完全是。它验证了线性解码 AE-SU 和有实测端元的 FCLS；在本仓库中更适合作为线性解混验证/基准类论文。
- **用了哪些数据集**：Planet Tanager-1 葡萄园高光谱影像、超高分辨率 UAV 影像、PSR+ 3500 野外实测光谱。
- **实验效果怎么样**：AE-SU 比 FCLS 更接近 UAV 植被覆盖分布，Overlap 为 0.80 对 0.72，JS divergence 为 0.059 对 0.079；土壤丰度图 Moran's I 为 0.82，空间结构较连贯。

## 一句话总结

这篇论文的价值在于说明当无法逐像素对齐真值时，如何用 UAV 和野外光谱对卫星尺度解混结果做分布级验证。

## 问题

农业区域的卫星像元常混合土壤和植被，但卫星、UAV、野外光谱的尺度不同，直接逐像素验证并不可靠。

## 方法

- 使用 Planet Tanager-1 VSWIR 高光谱数据。
- 用 UAV 正射影像和 ExG 植被 mask 作为高分辨率参考。
- 用野外实测土壤/植被光谱做光谱一致性检查。
- 比较 AE-SU 和 FCLS。
- 从分布相似度、纯像元光谱一致性和空间连贯性三方面验证。

## 实验

- 场景：希腊 Thessaloniki, Epanomi 的 Gerovasiliou Vineyard，Tanager-1 于 2025-07-12 获取。
- 端元：土壤、植被。
- 指标：histogram MAE、L2、EMD、overlap、Bhattacharyya、cosine similarity、JS divergence、Pearson、KGE、Moran's I。
- 结果：AE-SU 的植被丰度分布比 FCLS 更贴近 UAV 参考；高丰度像元与实测端元光谱一致；丰度图保留葡萄园行结构。
- 代码状态：本地 PDF 中未发现官方代码地址。

## 优点

- 对缺少丰度真值的真实 HU 应用很有参考价值。
- 同时使用卫星 HSI、UAV 图像和野外光谱。
- 把跨尺度下的分布级验证讲得比较清楚。

## 局限 / 问题

- 它是验证短文，不是完整的新解混算法。
- 只验证土壤/植被二端元农业场景。
- 数据和代码公开情况在 PDF 中不明确。

## 和我的工作有什么关系

如果后续需要验证真实场景解混结果，而手里只有跨尺度代理真值，这篇可以借鉴验证设计。

## BibTeX

```bibtex
@article{ampas2026crossscale,
  title={Cross-Scale Validation of Hyperspectral Unmixing Over Agricultural Landscapes},
  author={Ampas, Haris and Karyotis, Konstantinos and Guillevic, Pierre and Zalidis, George and Petridou, Sophia},
  journal={IEEE Geoscience and Remote Sensing Letters},
  year={2026},
  doi={10.1109/LGRS.2026.3687594}
}
```
