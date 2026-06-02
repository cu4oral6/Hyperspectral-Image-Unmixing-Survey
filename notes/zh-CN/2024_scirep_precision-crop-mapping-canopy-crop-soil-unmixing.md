# Precision Crop Mapping: Within Plant Canopy Discrimination of Crop and Soil Using Multi-Sensor Hyperspectral Imagery

## 元信息

- **年份**：2024
- **出版源**：Scientific Reports, vol. 14, article 24903
- **作者**：C. V. S. S. Manohar Kumar; Sudhanshu Shekhar Jha; Rama Rao Nidamanuri; Vinay Kumar Dadhwal
- **论文**：https://doi.org/10.1038/s41598-024-75394-1
- **代码**：TBD
- **项目页**：TBD
- **本地 PDF**：../../pdfs/s41598-024-75394-1.pdf
- **数据集**：cabbage crop-soil sub-canopy HSI；terrestrial HSI；drone HSI
- **标签**：数据集，基准，农业，crop-soil，drone，terrestrial HSI

## 速读要点

- **这篇论文讲了什么**：评估光谱解混在冠层内部作物/土壤区分中的作用，并生成多传感器地面/无人机 HSI 参考数据。
- **是不是线性盲解混**：不是。它使用已知端元/光谱库驱动的线性、稀疏和非线性解混方法，本仓库归为数据集/基准/应用论文。
- **用了哪些数据集**：地面 HSI、多高度无人机 HSI、野外光谱库，以及作物/土壤丰度参考。
- **实验效果怎么样**：在合适的端元来源、飞行高度和算法组合下，作物/土壤丰度判别准确率可接近 99-100%。

## 一句话总结

这篇 Scientific Reports 论文适合作为农业作物/土壤二端元解混和验证的参考基准。

## 问题

精准农业需要植物级甚至冠层内部的作物/土壤区分。田块级分类已经很多，但冠层内的叶片、土壤、阴影和传感器几何会造成更复杂的混合。

## 方法

- 采集地面平台和无人机平台的高光谱影像。
- 构建野外实测光谱库和影像端元库。
- 测试线性约束解混、稀疏解混、双线性/广义模型和 Hapke 类 intimate mixture 模型。
- 用实测 crop/soil 丰度参考和 SRE、RMSE 等重构指标评价结果。

## 实验

- 端元：cabbage crop 和 soil。
- 数据：THI、不同高度 DHI、野外光谱、影像端元库。
- 结果：野外光谱库在地面 HSI 上可达到约 86% crop、99% soil 丰度检索；THI 端元库把 crop 检索提升到约 94%；无人机多高度场景在合适设置下 crop/soil 都可接近 99%。
- 论文特别指出，SRE/RMSE 这类重构指标并不总能反映丰度图质量。

## 优点

- 对农业 HU 很有用，因为它提供多平台、多分辨率 crop/soil 参考数据。
- 系统分析端元来源和空间分辨率对丰度估计的影响。
- 提醒真实场景中不能只看重构误差。

## 局限 / 问题

- 这是应用/基准研究，不是新的解混算法。
- 只考虑 crop 和 soil 两个端元。
- PDF 中除论文和补充材料外，数据/代码公开入口不够明确。

## 和我的工作有什么关系

- 可用于设计农业 HU 验证，尤其是 crop/soil fraction 任务。
- 能支撑 README 里“Crop-soil discrimination 数据”的待办。
- 对评估指标选择有启发：丰度准确率、SRE、RMSE 需要一起看。

## BibTeX

```bibtex
@article{kumar2024precision,
  title={Precision crop mapping: within plant canopy discrimination of crop and soil using multi-sensor hyperspectral imagery},
  author={Kumar, C. V. S. S. Manohar and Jha, Sudhanshu Shekhar and Nidamanuri, Rama Rao and Dadhwal, Vinay Kumar},
  journal={Scientific Reports},
  volume={14},
  pages={24903},
  year={2024},
  doi={10.1038/s41598-024-75394-1}
}
```
