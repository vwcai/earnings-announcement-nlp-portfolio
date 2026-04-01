# Earnings Announcement NLP

This repository is a public portfolio version of a machine learning project on earnings announcement text and short-window abnormal stock returns.

The project uses earnings announcement disclosures to study whether narrative text can help explain short-window abnormal stock returns.

## Public Portfolio Note

This repository is a portfolio adaptation of a larger academic analysis. It includes selected code, outputs, and summary materials for portfolio review. Raw source data, classroom-specific scaffolding, and non-essential work products are intentionally omitted, and the repository is not intended as a step-by-step instructional solution.

## Start Here

- `PROJECT_SUMMARY.md`: main case-study style overview
- `earnings_announcement_topic_modeling.ipynb`: selected modeling workflow

## At a Glance

- Business question: can earnings announcement language help explain or predict short-window return reactions?
- Methods: text cleaning, document-term matrix construction, LDA topic modeling, Lasso regression, and classification modeling
- Headline takeaway: earnings announcement text contains useful signal, but predictive performance is moderate and strongest when interpreted alongside modeling choices and limitations

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
