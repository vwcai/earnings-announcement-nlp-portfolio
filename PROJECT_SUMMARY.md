# Project Summary

This summary presents the business question, analytical approach, and selected findings from the public portfolio version of the project. Supporting source materials and classroom-specific scaffolding are intentionally omitted.

## Executive Summary

This project analyzes whether earnings announcement language contains useful signal about short-window abnormal stock returns. The workflow cleans narrative disclosure text, builds text features, fits LDA topic models, evaluates topic-return relationships with Lasso, and compares classification models for predicting large positive returns.

The results suggest that earnings announcement text does contain informative signal, especially at the topic level. Profit-oriented and EPS-related language aligns more strongly with positive return reactions, while loss-oriented language aligns more strongly with negative reactions. At the same time, classification performance remains moderate, which reinforces the idea that text helps explain return variation but does not fully determine it.

From a business analytics perspective, the project shows how narrative disclosure can be converted into structured features and linked to a measurable market outcome.

## Business Question

Can the language used in earnings announcements help explain or predict short-window stock return reactions?

This question matters because narrative disclosure is often one of the earliest and richest public signals available around earnings events. If language patterns capture information about performance, expectations, or tone, they may support market reaction analysis and event-driven decision-making.

## Analytical Approach

- Loaded and cleaned earnings announcement text
- Replaced financial numbers with a normalized token to reduce noise
- Removed low-information sentences
- Built a document-term matrix with unigram and bigram features
- Fit LDA topic models and compared coherence across topic counts
- Used Lasso regression to evaluate which topics were most associated with abnormal returns
- Compared classifiers for predicting whether `BHAR0_2` exceeded 5%

## Data Scope

The original workflow uses:

- earnings announcement text
- short-window abnormal return labels (`BHAR0_2`)
- derived topic features and document-term matrix features

The raw source data is not included in this public repository.

## Key Findings

### Topic Modeling

- The source dataset contains **12,500** earnings announcements
- Topic coherence was evaluated from **40 to 150 topics**
- A **50-topic** specification was chosen for the final interpretable model

Representative topic groups include:

- EPS and adjusted operating performance
- net loss and negative operating performance
- oil and gas production
- restructuring charges
- EBITDA and adjusted results

### Lasso Results

- Best `alpha`: **0.008467898137887975**
- Number of non-zero topic coefficients: **7**
- Most positive topic: **Topic 9**
- Most negative topic: **Topic 31**

The strongest positive topic centers on terms such as:

- `eps`
- `adjusted operating`
- `diluted eps`

The strongest negative topic centers on terms such as:

- `net loss`
- `loss income`
- `operating loss`

### Classification Results

The strongest reported classification setup uses combined topic and document-term features in a tuned LightGBM model.

Selected results:

- Accuracy: **0.6804**
- Macro F1: **0.5395**
- Weighted F1: **0.6728**

The model performs noticeably better on the majority class than on the positive-return class, which suggests that the classification problem remains challenging even after substantial text feature engineering.

Rather than relying on a single model, the workflow compares multiple modeling approaches and treats tuning as a way to evaluate tradeoffs between interpretability and predictive performance.

## Interpretation

The strongest positive topic is centered on EPS and adjusted operating performance, while the strongest negative topic is centered on loss-oriented language. That directional result is intuitive: performance-related language tends to align with more favorable reactions, while explicit loss language tends to align with weaker reactions.

At the same time, the overall predictive performance is moderate. This indicates that textual disclosure provides useful information, but it is only one piece of a broader market reaction process.

## Why This Matters

This project demonstrates a practical analytics pattern:

- convert unstructured text into structured features
- compare unsupervised and supervised modeling approaches
- relate language patterns to a measurable financial target
- communicate both signal and limitation

That same pattern can transfer to other business settings such as:

- earnings call analysis
- customer feedback modeling
- support ticket classification
- document risk screening

## Limitations

- The analysis is constrained by the available text and return window
- Topic models improve interpretability but simplify language structure
- Classification performance is moderate, especially for the positive-return class
- Market reactions are influenced by many factors beyond disclosure text alone

## Files

- `earnings_announcement_topic_modeling.ipynb`: notebook with the selected analysis workflow and outputs
- `requirements.txt`: Python dependencies
