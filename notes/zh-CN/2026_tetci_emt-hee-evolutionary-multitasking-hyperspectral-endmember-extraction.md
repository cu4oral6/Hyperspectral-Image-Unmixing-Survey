# EMT-HEE: An Evolutionary Multi-Tasking Method for Hyperspectral Endmember Extraction

## 元信息

- **年份**：2026
- **出版源**：IEEE Transactions on Emerging Topics in Computational Intelligence
- **作者**：Qijun Wang; Zilong Zhu; Fan Cheng; Bo Du; Lixia Yang
- **论文**：https://doi.org/10.1109/TETCI.2025.3634746
- **代码**：TBD
- **项目页**：TBD
- **本地 PDF**：../../pdfs/EMT-HEE An Evolutionary Multi-Tasking Method for Hyperspectral Endmember Extraction.pdf
- **数据集**：synthetic; real HSI datasets
- **标签**：linear, blind, endmember extraction, evolutionary algorithm, multitasking
- **笔记状态**：基于本地 PDF 速读

## 一句话总结

EMT-HEE 把端元提取视为受约束、稀疏的大规模优化问题，并用进化多任务提高全局搜索能力。

## 问题

进化算法有全局搜索优势，但端元提取的约束和高维稀疏搜索空间会让优化效率和局部最优问题变得突出。

## 方法

- 把原始端元提取作为主任务，构造无约束辅助任务来扩大搜索。
- 分别维护主种群和辅助种群，并设计任务专属的解生成策略。
- 通过 assisting-to-main repair 和 main-to-assisting enhancement 进行知识迁移。

## 实验

论文在合成和真实高光谱场景上评估，报告端元质量优于若干对比 EE 算法。

## 优点

- 给端元提取提供了有意思的优化视角。
- 辅助任务设计直接针对约束和局部最优。
- 可以补充 AE/Transformer 类深度解混基线。

## 局限 / 问题

- 重点是端元提取，不是完整丰度估计流程。
- 本地 PDF 未发现官方代码。
- 精确表格数值还需要逐图表核对。

## 和我的工作有什么关系

适合作为盲端元提取方向的近期进化优化基线。

## BibTeX

```bibtex
@article{wang2026emthee,
  title={EMT-HEE: An Evolutionary Multi-Tasking Method for Hyperspectral Endmember Extraction},
  author={Qijun Wang and Zilong Zhu and Fan Cheng and Bo Du and Lixia Yang},
  journal={IEEE Transactions on Emerging Topics in Computational Intelligence},
  year={2026},
  doi={10.1109/TETCI.2025.3634746}
}
```
