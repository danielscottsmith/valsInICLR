# Notebooks

## Subdir Structure
```
01_notebooks/
├── 00_downloadData.ipynb
├── 01_labelData.ipynb
└── README.md
```

## Getting Started
1. `00` downloads ICLR data from the OpenReview API
1. `01` contains the full labeling logic, including tokenization and inference.


## Requirements
Note, `openreview` is incompatible with `transformers` and/or `torch`. So when/if attempting to reproduce all routines in these notebooks, it's better to create a unique conda env for each one. 