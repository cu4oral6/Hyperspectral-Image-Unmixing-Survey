# EMT-HEE: An Evolutionary Multi-Tasking Method for Hyperspectral Endmember Extraction

## Metadata

- **Year**: 2026
- **Venue**: IEEE Transactions on Emerging Topics in Computational Intelligence
- **Authors**: Qijun Wang; Zilong Zhu; Fan Cheng; Bo Du; Lixia Yang
- **Paper**: https://doi.org/10.1109/TETCI.2025.3634746
- **Code**: TBD
- **Project**: TBD
- **Local PDF**: ../pdfs/EMT-HEE An Evolutionary Multi-Tasking Method for Hyperspectral Endmember Extraction.pdf
- **Datasets**: synthetic; real HSI datasets
- **Tags**: linear, blind, endmember extraction, evolutionary algorithm, multitasking
- **Note status**: skimmed from the local PDF

## One-Sentence Summary

EMT-HEE treats endmember extraction as a constrained sparse large-scale optimization problem and uses evolutionary multitasking to improve global search.

## Problem

Evolutionary endmember extraction can search globally, but the constrained and sparse high-dimensional search space makes efficient optimization difficult.

## Method

- Defines the original EE task as the main task and an unconstrained auxiliary task for broader exploration.
- Evolves main and auxiliary populations with task-specific solution generation strategies.
- Transfers knowledge through assisting-to-main repair and main-to-assisting enhancement.

## Experiments

The paper evaluates synthetic and real hyperspectral scenes and reports higher-quality endmember extraction than compared EE algorithms.

## Strengths

- Interesting optimization perspective for endmember extraction.
- Auxiliary-task design directly addresses constraints and local optima.
- Complements neural AE/Transformer HU baselines.

## Weaknesses / Questions

- Focuses on endmembers rather than full abundance-estimation workflows.
- No official code URL was found in the local PDF.
- Exact per-dataset table values need visual checking.

## Relevance To My Work

Useful as a modern evolutionary optimization baseline for blind endmember extraction.

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
