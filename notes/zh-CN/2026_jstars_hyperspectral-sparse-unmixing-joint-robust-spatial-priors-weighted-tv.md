# Hyperspectral Sparse Unmixing via Joint Robust Spatial Priors and Weighted Total Variation Regularization

## 元信息

- **年份**：2026
- **出版源**：IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing
- **作者**：Fan Li; Xiyu Chen; Shaoquan Zhang; Jiaqiang Zhou; Huasheng Zhu; Yuyang Liu; Hongyu Zhang; Chengzhi Deng; Shengqian Wang
- **论文**：https://doi.org/10.1109/JSTARS.2026.3668120
- **代码**：TBD
- **项目页**：TBD
- **本地 PDF**：../../pdfs/Hyperspectral Sparse Unmixing via Joint Robust Spatial Priors and Weighted Total Variation Regularization.pdf
- **数据集**：synthetic; real HSI datasets
- **标签**：linear, semi-supervised, sparse, total variation, spatial priors, robust
- **笔记状态**：基于本地 PDF 速读

## 一句话总结

RSPWTV 将鲁棒空间先验与自适应加权 TV 结合，用于在噪声和异常值下保持丰度边缘并提升稀疏解混精度。

## 问题

稀疏解混依赖光谱库，但在复杂噪声和异常值下，如果空间正则过弱或过于均匀，丰度图容易丢失细节。

## 方法

- 以鲁棒稀疏解混框架为基础。
- 利用光谱角相似性和空间邻近性构造自适应加权 TV。
- 把 weighted TV 与鲁棒空间先验结合，在同质区域增强平滑，在边缘区域降低过平滑。

## 实验

论文在合成和真实 HSI 上用 SAD、RMSE、SRE 等稀疏解混指标与基线比较。

## 优点

- 很适合光谱库稀疏解混场景。
- 加权 TV 相比全局 TV 更关注边缘保护。
- 重点处理混合噪声和异常值鲁棒性。

## 局限 / 问题

- 效果依赖光谱库质量。
- 本地 PDF 未发现官方代码。
- 引用精确数值前需要视觉核对表格。

## 和我的工作有什么关系

适合用于比较带空间正则的稀疏解混方法，尤其是噪声场景。

## BibTeX

```bibtex
@article{li2026rspwtv,
  title={Hyperspectral Sparse Unmixing via Joint Robust Spatial Priors and Weighted Total Variation Regularization},
  author={Fan Li and Xiyu Chen and Shaoquan Zhang and Jiaqiang Zhou and Huasheng Zhu and Yuyang Liu and Hongyu Zhang and Chengzhi Deng and Shengqian Wang},
  journal={IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing},
  year={2026},
  doi={10.1109/JSTARS.2026.3668120}
}
```
