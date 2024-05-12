# Raw Data Repo

## Subdir Structure
```
00_rawData/
├── README.md
├── iclr_2018_2024.feather                   # review-level data
├── iclr_2018_2024_encodings.feather         # sentence-level roberta encodings
├── iclr_2018_2024_polarity_predictions.csv  # sentence-level predicted lables
├── iclr_2018_2024_sents.jsonl               # sentence-level data
└── iclr_2018_2024_value_predictions.csv     # sentence-level predicted lables
```

## Getting Started
1. Here deposit downloaded data from the OpenReview API using `~/01_notebooks/00_downloadData.ipynb`. 
2. This will also be our directory for interim processed data, including tokenized review sentences and labeled review sentences, both of which get generated during the course of  `~/01_notebooks/01_labelData.ipynb`.


