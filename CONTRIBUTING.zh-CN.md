# 维护说明

这个文件夹用于长期维护高光谱图像解混论文列表、数据集、实验结果和阅读笔记。

## 添加论文检查清单

- 在 `data/papers.csv` 添加论文条目。
- 使用稳定的论文标题和正式 venue 名称。
- 尽量添加 DOI、官方论文页、官方代码和项目主页。
- 根据 README 中的方法分类添加标签。
- 对关键论文、已读论文或值得复查的论文，在 `notes/zh-CN/` 创建中文笔记。
- 公开仓库中不要上传出版社 PDF；本地可保留 PDF，仓库只记录链接和笔记。

## CSV 字段说明

- `year`：发表年份。
- `title`：论文标题。
- `authors`：作者；快速记录时可以使用 First Author et al.
- `venue`：期刊、会议、arXiv 或 workshop。
- `mixing_model`：混合模型类型，例如 `linear`、`nonlinear` 或 `hybrid/unclear`。
- `supervision`：监督设定，例如 `blind`、`non-blind`、`semi-supervised` 或 `unclear`。
- `category`：分类与主要方法类别，例如 `linear blind unmixing; graph-guided sparse NMF`。
- `dataset`：主要使用的数据集。
- `metrics`：主要报告的指标。
- `doi`：DOI，不包含 `https://doi.org/` 前缀。
- `paper_url`：DOI、出版社页面、arXiv 或 OpenReview 链接。
- `code_url`：官方代码仓库。
- `project_url`：项目主页。
- `pdf_path`：本地 PDF 路径，例如 `pdfs/example.pdf`。PDF 默认不推送。
- `notes_path`：本地英文笔记路径，例如 `notes/2025_tgrs_short-title.md`。
- `status`：阅读状态，例如 `to-read`、`reading`、`read`、`skimmed`、`key-paper`。
- `tags`：逗号分隔的标签。
