# valsInICLR
This repo is designed to infer the number of different kinds of epistemic value judgments present in ICLR reviews. Specifically, it:
1. downloads raw ICLR data from the [OpenReviewAPI](openreview.net), 
2. tokenizes it into sentences,
3. then uses two RoBERTa models previously fine-tuned on [ReviewAdvisor](https://github.com/neulab/ReviewAdvisor) and [DISAPERE](https://github.com/nnkennard/DISAPERE) training data to label sentence aspects and polarity, respectivel, and finally
4. combines these labels ("Aspect (polarity)") and aggregates them up to the review level as sentence frequencies. 


## Repo Structure 
```
valsInICLR/
├── 00_rawData
│   ├── README.md
│   ├── iclr_2018_2024.feather
│   ├── iclr_2018_2024_encodings.feather
│   ├── iclr_2018_2024_polarity_predictions.csv
│   ├── iclr_2018_2024_sents.jsonl
│   └── iclr_2018_2024_value_predictions.csv
├── 01_notebooks
│   ├── 00_downloadData.ipynb
│   ├── 01_labelData.ipynb
│   └── README.md
├── 02_tunedModels
│   ├── README.md
│   ├── polarity_roberta
│   └── value_roberta
├── 03_labeledData
│   └── iclr_2018_2024_labeled.jsonl
└── README.md
```

## What is an epistemic value judgment?
An epistemic value judgment occurs at the level of a sentence. A sentence contains a value judgment when it has a judgment (positive or negative evaluation) **and** a target or aspect:
1. __Accuracy__ - Is the proposed approach sound? Are the claims in the paper convincingly supported?
2. __Clarity__ - For a reasonably well-prepared reader, is it clear what was done and why? Is the paper well-written and structured?
3. __Consistency__ - Are the comparisons to prior work sufficient given the space constraints? Are the comparisons fair?
4. __Novelty__ - Are there new topics, technique, methodology, or insights? *AND* Does the paper address an important problem? Are other people (practitioners or researchers) likely to use these ideas or build on them?
5. __Replicability__ - Is it easy to reproduce the results and verify the correctness of the results? Is the supporting dataset and/or software provided?
6. __Thoroughness__ - Does the paper contain substantial experiments to demonstrate the effectiveness of proposed methods? Are there detailed result analyses? Does it contain meaningful ablation studies?

Canonically, a value judgment is represented as "Aspect (polarity)", e.g., "Novelty (–)" which So at the end, this repo produces a review-level dataframe that contains the number of each of these value judgments in each review.


## Repo Requirements

1. This repo doesn't reproduce the fine-tuning of the RoBERTa models. 
1. Generally, `OpenReview` and `torch`/`transformers` are incompatible. So, 1 conda environment should be created for each notebook script. 
1. This repo doesn't contain model weights or data due to size. These are on the VM. These are needed if, for example, different pre-processing decisions are made and sentence-level labels need to be re-inferred.


