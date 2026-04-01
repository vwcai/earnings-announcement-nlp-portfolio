# Earnings Announcement NLP

This repository is a public portfolio version of a machine learning project on earnings announcement text and short-window abnormal stock returns.

## Public Portfolio Note

This repository is a portfolio adaptation of a larger academic analysis. It includes selected code, outputs, and summary materials for portfolio review. Raw source data, classroom-specific scaffolding, and non-essential work products are intentionally omitted, and the repository is not intended as a step-by-step instructional solution.

## Project Overview

This project uses NLP and machine learning to test whether earnings announcement language helps explain or predict short-window abnormal stock return reactions.

## Business Problem

Narrative disclosure is often one of the earliest public signals available around earnings events. For analysts and decision-makers, the key question is whether that text adds useful information beyond structured financial numbers and whether it can improve event-driven monitoring or market-reaction analysis.

## Data

- Source: earnings announcement text, short-window abnormal return labels, and locally derived text features
- Type: financial narrative text plus event-outcome labels
- Included here: selected notebook workflow and portfolio summary materials
- Not included: the raw source dataset used in the original workflow

## Approach

- Cleaned earnings announcement text and normalized financial numbers
- Built document-term matrix features with unigrams and bigrams
- Fit LDA topic models and compared topic coherence across topic counts
- Used Lasso to identify which topics were most associated with abnormal returns
- Compared classification models to test how much predictive value the text added

## Key Insights

- EPS and adjusted operating performance language aligned more strongly with positive return reactions
- Loss-oriented language aligned more strongly with negative reactions
- The strongest reported setup combined topic and document-term features in a tuned LightGBM model
- Predictive performance was moderate, which means the text was informative but not strong enough to act as a standalone predictor

## Recommendations

- I would use narrative disclosure as a complementary signal in an event-driven analytics workflow, not as a replacement for structured financial inputs
- I would monitor themes related to EPS, adjusted operating performance, and loss language because those carried the clearest directional signal
- I would combine text features with additional structured event or firm-level data before relying on the model in practice

## Start Here

- `PROJECT_SUMMARY.md`: main case-study style overview
- `earnings_announcement_topic_modeling.ipynb`: selected modeling workflow

## Repository Contents

- `earnings_announcement_topic_modeling.ipynb`: selected notebook with code, modeling workflow, and outputs
- `PROJECT_SUMMARY.md`: detailed project narrative with business framing, approach, findings, and limitations
- `requirements.txt`: Python dependencies used in the project

## Data Note

The raw source data is not included in this repository. The underlying workflow depends on earnings announcement text, short-window abnormal return labels, and a locally generated cleaned text file created during preprocessing.

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
