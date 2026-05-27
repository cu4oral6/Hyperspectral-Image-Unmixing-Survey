# Deep Diffusion Models and Unsupervised Hyperspectral Unmixing for Realistic Abundance Map Synthesis

## 元信息

- **年份**：2025
- **Venue**：IEEE/CVF Conference on Computer Vision and Pattern Recognition Workshops (CVPRW)
- **作者**：Martina Pastorino; Michael Alibani; Nicola Acito; Gabriele Moser
- **论文链接**：https://doi.org/10.1109/CVPRW67362.2025.00286
- **代码链接**：TBD
- **本地 PDF**：../../pdfs/Deep_Diffusion_Models_and_Unsupervised_Hyperspectral_Unmixing_for_Realistic_Abundance_Map_Synthesis.pdf
- **数据集**：PRISMA，覆盖 Mexico、Spain、Italy 的多类地表场景
- **标签**：deep, diffusion, blind, abundance-synthesis, PRISMA

## 一句话总结

这篇 workshop 论文把盲线性高光谱解混和扩散模型结合起来，在不需要标注丰度图的情况下，从真实 PRISMA 数据中学习并生成逼真的丰度图。

## 问题

高质量合成高光谱数据对算法评测、任务规划和训练数据增强很有价值，但直接生成高维光谱数据成本高、难度大。论文选择先生成低维且可解释的丰度图。

## 方法

- 对原始高光谱图像应用一组盲线性解混算法。
- 将提取出的丰度图作为扩散模型的训练样本。
- 在丰度空间学习空间分布，而不是直接学习完整高维光谱。
- 整个流程是无监督的，不依赖人工标注的丰度图。

## 实验

- 使用 Mexico、Spain、Italy 的 PRISMA 高光谱图像。
- 展示了山地、植被、城市和混合场景的合成丰度图。
- 主要采用定性视觉分析。
- 结论中把完整高光谱图像合成以及 SAD、RMSE、PSNR、SSIM 等量化评估列为后续工作。

## 优点

- 思路清楚：用经典盲解混提供物理可解释中间表示，再用扩散模型建模空间分布。
- 作为后续完整高光谱图像合成工作的前置版本很有参考价值。
- 不绑定单一解混算法。

## 局限 / 问题

- 量化实验较弱，主要是视觉展示。
- 生成目标是丰度图，不是完整高光谱图像。
- 需要继续确认是否有独立代码或训练细节。

## 和我的工作有什么关系

- 可以作为“扩散模型生成丰度图”的背景论文。
- 和 2026 GRSL 版本一起看，能看到作者从丰度图合成到完整 HSI 合成的推进路线。

## BibTeX

```bibtex
@inproceedings{pastorino2025deep,
  title={Deep Diffusion Models and Unsupervised Hyperspectral Unmixing for Realistic Abundance Map Synthesis},
  author={Pastorino, Martina and Alibani, Michael and Acito, Nicola and Moser, Gabriele},
  booktitle={IEEE/CVF Conference on Computer Vision and Pattern Recognition Workshops (CVPRW)},
  pages={3029--3037},
  year={2025},
  doi={10.1109/CVPRW67362.2025.00286}
}
```

