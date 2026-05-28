# MS^2AE-Net: A Multiscale Spectral-Spatial Autoencoder Network for Hyperspectral Unmixing

## 元信息

- **年份**：2026
- **出版源**：IEEE Transactions on Geoscience and Remote Sensing
- **作者**：TBD
- **论文**：https://doi.org/10.1109/TGRS.2026.3662051
- **代码**：TBD
- **项目页**：TBD
- **本地 PDF**：../../pdfs/MS2AE-Net A Multiscale Spectral-Spatial Autoencoder Network for Hyperspectral Unmixing.pdf
- **数据集**：synthetic
- **标签**：linear,blind,autoencoder,multiscale
- **笔记状态**：基于本地 PDF 元数据和摘要的速读笔记

## 一句话总结

这是一篇关于线性盲解混; 自编码器; 多尺度的速读笔记，重点记录方法思路、实验设置以及代码线索；相关实验数据集为 synthetic。

## 问题

这篇论文归入线性盲高光谱解混方向，即在没有外部端元真值输入的情况下，同时估计端元光谱和丰度图。它关注的具体问题可能包括空谱特征建模、光谱变异、稀疏/低秩先验、深度自编码器、Mamba/Transformer 序列建模，或端元与丰度估计的基准性能提升。

## 方法

- 核心思路：线性盲解混; 自编码器; 多尺度。
- 模型 / 优化：详细公式和网络结构需要回到本地 PDF 深读；本轮先整理方法族、代码状态和复现实验入口。
- 先验或假设：线性盲解混设置，通常涉及非负性、和为一、稀疏性、低秩性、空间平滑或神经网络中的等价约束。
- 训练或推理细节：本批量整理未逐项完整抽取。

## 实验

- 数据集：synthetic
- 指标：SAD; RMSE
- 代码状态：TBD；本地 PDF 与快速核验中未发现官方代码地址。
- 摘要线索：已使用本地 PDF 摘要和元数据完成速读索引；此处不复现摘要原文。

## 优点

- 为线性盲解混主线补充一个可索引的代表性方法。
- 便于和同一分类下的传统优化、稀疏/低秩方法以及深度网络方法比较。
- DOI、本地 PDF、笔记路径和代码状态已经集中记录，方便后续深读。

## 局限 / 问题

- 这是速读笔记，公式、超参数、消融实验和协议细节还需要人工精读补全。
- 代码地址只有在论文或官方页面明确给出并能核验时才填写，否则保留 `TBD`。
- 若论文包含多个合成/真实数据集，当前数据集字段后续还可以继续细化。

## 和我的工作有什么关系

- 可作为线性盲解混基线和近期方法谱系整理的一部分。
- 若该方法族与当前课题相关，或已有代码可复现，适合优先安排深读。

## BibTeX

```bibtex
@article{ms2ae_net_multiscale_spectral_spatial_autoencoder_network_hyperspectral,
  title={MS^2AE-Net: A Multiscale Spectral-Spatial Autoencoder Network for Hyperspectral Unmixing},
  author={TBD},
  year={2026},
  doi={10.1109/TGRS.2026.3662051}
}
```
