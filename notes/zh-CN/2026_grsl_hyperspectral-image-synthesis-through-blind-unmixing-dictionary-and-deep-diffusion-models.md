# Hyperspectral Image Synthesis Through Blind Unmixing Dictionary and Deep Diffusion Models

## 元信息

- **年份**：2026
- **Venue**：IEEE Geoscience and Remote Sensing Letters, vol. 23
- **作者**：Martina Pastorino; Michael Alibani; Nicola Acito; Gabriele Moser
- **论文链接**：https://doi.org/10.1109/LGRS.2025.3646054
- **代码链接**：https://github.com/martinapastorino/HSI_DDPM
- **本地 PDF**：../../pdfs/Hyperspectral_Image_Synthesis_Through_Blind_Unmixing_Dictionary_and_Deep_Diffusion_Models.pdf
- **数据集**：PRISMA，覆盖 Mexico、Spain、Italy 的多类地表场景
- **标签**：deep, diffusion, blind, unmixing-dictionary, image-synthesis, PRISMA
- **相关早期版本**：Deep Diffusion Models and Unsupervised Hyperspectral Unmixing for Realistic Abundance Map Synthesis，CVPRW 2025，DOI：https://doi.org/10.1109/CVPRW67362.2025.00286

## 一句话总结

这篇论文用多个盲线性解混算法构成字典，从真实 PRISMA 高光谱图像中提取端元和丰度图，再在丰度空间训练引导扩散模型，用于合成更真实的高光谱图像。

## 问题

直接在高维高光谱空间生成图像很困难，因为高光谱图像同时具有高光谱维度和复杂的空间结构。论文将生成问题转移到低维、可解释的丰度空间，再结合端元重建高光谱图像。

## 方法

- 构建盲线性解混方法字典，包含 least-squares、deep learning 和 statistical 三类方法。
- 从真实 PRISMA 数据中提取端元和丰度图。
- 将丰度图裁剪为 patch，训练 denoising diffusion probabilistic model。
- 在扩散模型的概率生成过程中引入解混方法字典作为条件，减少对单一解混算法的依赖。

## 实验

- 使用 4 个 PRISMA tile，覆盖城市、植被、山地和混合地表。
- 去除受大气吸收影响的通道后保留 201 个波段。
- 使用 256 x 256 的丰度 patch 训练扩散模型。
- 对比直接生成高光谱图像的扩散模型和 UnmixDiff。
- 主要通过 false-color composite 进行视觉质量比较。

## 优点

- 相比 CVPRW 版本更完整：从丰度图合成推进到了完整高光谱图像合成。
- 有官方代码，便于复现。
- 用解混字典引入物理可解释性和算法多样性。

## 局限 / 问题

- 从 PDF 抽取内容看，量化的光谱保真度指标不突出。
- 结果可能依赖解混字典的选择和端元数量设置。
- 需要进一步检查代码是否包含完整预处理流程和训练配置。

## 和我的工作有什么关系

- 如果关注“解混 + 扩散模型 + 高光谱数据生成”，这篇可以作为关键论文。
- 适合用于 synthetic HSI generation、数据增强、传感器仿真等方向的文献入口。

## 去重说明

CVPRW 2025 论文可视为早期 workshop 版本，重点是丰度图合成。当前主列表保留 2026 GRSL 版本，因为它扩展到完整高光谱图像合成，并提供官方代码链接。

## BibTeX

```bibtex
@article{pastorino2026hyperspectral,
  title={Hyperspectral Image Synthesis Through Blind Unmixing Dictionary and Deep Diffusion Models},
  author={Pastorino, Martina and Alibani, Michael and Acito, Nicola and Moser, Gabriele},
  journal={IEEE Geoscience and Remote Sensing Letters},
  volume={23},
  year={2026},
  doi={10.1109/LGRS.2025.3646054}
}
```
