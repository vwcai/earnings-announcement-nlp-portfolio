# Earnings Announcement Topic Modeling

This repository is a public portfolio version of a machine learning project on earnings announcement text and short-window abnormal stock returns.

The notebook cleans narrative disclosure text, builds text features, fits LDA topic models, evaluates topic-return relationships with Lasso, and compares classifiers for predicting large positive returns.

## Portfolio Version Note

This public version focuses on methodology, modeling choices, and representative results. Original course materials, raw source data, and assignment scaffolding are intentionally omitted.

## Highlights

- Cleans earnings announcement text and normalizes financial numbers
- Builds unigram and bigram features with stop-word filtering
- Tunes LDA topic models across multiple topic counts
- Uses Lasso to identify topics associated with abnormal returns
- Compares classifiers for predicting returns greater than 5%

## Selected Findings

- The source dataset contains **12,500** earnings announcements
- Topic coherence was evaluated from **40 to 150 topics**
- A 50-topic specification was used for the final interpretable model
- The strongest positive topic centers on EPS and adjusted operating language
- The strongest negative topic centers on net loss language
- The best reported classification setup uses combined topic and DTM features

## Repository Contents

- `earnings_announcement_topic_modeling.ipynb`: cleaned notebook with code, modeling workflow, and selected outputs
- `requirements.txt`: Python dependencies used in the project

## Data Note

The raw source data is not included in this repository. The original workflow expects access to:

- `ExpTask2Data.csv.gz`

The notebook also references an intermediate cleaned file generated locally during preprocessing.

## Local Reproduction

Install dependencies:

```bash
pip install -r requirements.txt
```

NLTK resources such as `punkt` and `stopwords` may also need to be available locally.

Then open:

- `earnings_announcement_topic_modeling.ipynb`

## Skills Demonstrated

- NLP preprocessing
- topic modeling with LDA
- model selection and coherence evaluation
- regression with regularization
- classification modeling
- performance interpretation
