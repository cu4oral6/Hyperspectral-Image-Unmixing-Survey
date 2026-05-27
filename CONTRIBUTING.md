# Contributing

This folder is intended as a living survey for hyperspectral image unmixing papers.

## Paper Entry Checklist

- Add the paper to `data/papers.csv`.
- Use a stable title and official venue name.
- Add official paper/code/project links when available.
- Assign one or more tags from the README taxonomy.
- Create a note in `notes/` for papers that are central, surprising, or already read.

## CSV Field Guide

- `year`: Publication year.
- `title`: Paper title.
- `authors`: First author et al. is fine for quick entries.
- `venue`: Journal, conference, arXiv, or workshop.
- `category`: Main method family, such as `deep`, `sparse`, `bayesian`, `nonlinear`.
- `dataset`: Main datasets used.
- `metrics`: Main metrics reported.
- `doi`: DOI without the `https://doi.org/` prefix.
- `paper_url`: DOI, publisher page, arXiv, or OpenReview.
- `code_url`: Official code repository if available.
- `project_url`: Project page if available.
- `pdf_path`: Local PDF path, such as `pdfs/example.pdf`.
- `notes_path`: Local note path, such as `notes/2025_tgrs_short-title.md`.
- `status`: `to-read`, `reading`, `read`, `skimmed`, or `key-paper`.
- `tags`: Comma-separated tags.
