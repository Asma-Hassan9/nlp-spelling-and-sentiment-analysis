# NLP Spelling Correction and Sentiment Analysis

This repository contains two natural language processing applications developed for an academic group assignment:

1. A domain-aware spelling correction system trained on an economics corpus.
2. A sentiment classifier for women's e-commerce clothing reviews.

It also includes an individual presentation by **Asma Abdiwali Hassan** evaluating both applications, their limitations, and possible improvements.

## Attribution

The two notebooks were completed as **group work** and are shared here for portfolio transparency. This repository does not claim that Asma was the sole author of the group assignment. The PowerPoint presentation in `presentation/` was Asma's individual work.

## Project 1: Spelling Correction

The spelling correction system uses a domain-specific economics corpus and combines:

- Text preprocessing and tokenization
- Unigram and bigram frequencies
- Edit-distance candidate generation
- Context-aware candidate ranking
- A Gradio interface for interactive testing

The corpus is the Project Gutenberg edition of *The Principles of Economics, with Applications to Practical Problems* by Frank A. Fetter (eBook #40077). Its Project Gutenberg license remains included in the text file.

## Project 2: Sentiment Classification

The sentiment notebook classifies women's clothing reviews as negative, neutral, or positive based on review ratings. It includes:

- Exploratory data analysis and text cleaning
- TF-IDF and n-gram feature engineering
- Logistic Regression, Linear SVM, and XGBoost models
- Model tuning and evaluation
- A Gradio prediction interface

## Repository Structure

```text
.
├── data/
│   ├── principles_of_economics.zip
│   └── README.md
├── notebooks/
│   ├── spelling_correction_system.ipynb
│   └── sentiment_classification.ipynb
├── presentation/
│   └── nlp_individual_presentation.pptx
├── .gitignore
├── README.md
└── requirements.txt
```

## Setup

```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -r requirements.txt
python -m spacy download en_core_web_sm
jupyter notebook
```

Extract `data/principles_of_economics.zip` before running the spelling-correction notebook. Then open either notebook from the `notebooks/` directory. The sentiment notebook expects the CSV at `../data/womens_clothing_ecommerce_reviews.csv`.

Download the Women's E-Commerce Clothing Reviews dataset from Kaggle and save it as `data/womens_clothing_ecommerce_reviews.csv`. The raw CSV is not committed because the repository documents external dataset retrieval instead of redistributing it.


## Limitations

- The spelling corrector relies mainly on edit distance and bigram context rather than deeper semantic models.
- The sentiment data is imbalanced, particularly for neutral reviews.
- The sentiment model focuses on English-language fashion reviews and may not generalize to other domains.

## Future Improvements

- Add part-of-speech and transformer-based context to spelling correction.
- Compare semantic embeddings and transformer models for sentiment classification.
- Add model explainability and stronger validation across datasets.
