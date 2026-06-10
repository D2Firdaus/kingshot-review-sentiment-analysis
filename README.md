# Kingshot Review Sentiment Analysis

This repository contains a sentiment analysis project based on user reviews of the mobile game **Kingshot** from the Google Play Store. The project covers data scraping, preprocessing, sentiment classification, imbalanced data handling, and analysis output documentation.

The main objective of this project is to classify Kingshot user reviews into **positive** and **negative** sentiment classes using text-based machine learning methods, especially **TF-IDF**, **n-gram features**, and several classification algorithms.

## Project Objectives

The objectives of this project are:

* To collect Kingshot user reviews from the Google Play Store.
* To clean and prepare review data for sentiment analysis.
* To convert review ratings into binary sentiment labels.
* To classify user sentiment using TF-IDF and machine learning models.
* To evaluate model performance using classification metrics.
* To analyze the impact of imbalanced data handling on classification performance.

## Repository Structure

```text
kingshot-review-sentiment-analysis/
│
├── data/
│   ├── raw/          # Raw data collected from Google Play Store
│   ├── processed/    # Cleaned and filtered review data
│   └── final/        # Final dataset for sentiment classification
│
├── notebook/
│   ├── 01_scrape_kingshot_reviews.ipynb
│   ├── 02_preprocessing_and_filtering_kingshot_reviews.ipynb
│   ├── 03_sentiment_classification_tfidf_ngram.ipynb
│   └── 04_imbalanced_data_handling.ipynb
│
├── outputs/          # Generated figures, tables, and analysis results
├── reference/        # Supporting research papers
│
├── .gitignore
├── LICENSE
├── README.md
└── requirements.txt
```

## Workflow Overview

The project workflow consists of four main stages:

```text
Google Play Reviews
        ↓
Data Scraping
        ↓
Preprocessing and Filtering
        ↓
Sentiment Classification
        ↓
Imbalanced Data Handling
        ↓
Model Evaluation and Analysis
```

## Notebook Description

### 1. Review Scraping

File:

```text
notebook/01_scrape_kingshot_reviews.ipynb
```

This notebook collects Kingshot user reviews from the Google Play Store. The configured review target is **14,416 reviews**. Scraping is performed incrementally and saved as a checkpoint so the process can be resumed if interrupted.

Main outputs are stored in:

```text
data/raw/
```

The raw dataset contains review text, rating, review date, user information, and other available metadata from Google Play.

### 2. Preprocessing and Filtering

File:

```text
notebook/02_preprocessing_and_filtering_kingshot_reviews.ipynb
```

This notebook prepares the raw review dataset before classification. The preprocessing stage consists of data cleaning, text normalization, review filtering, and binary sentiment labeling.

Preprocessing flow:

```text
Raw Reviews
    ↓
Data Cleaning
    ↓
Text Normalization
    ↓
Review Filtering
    ↓
Binary Sentiment Labeling
    ↓
Processed Dataset
```

Data cleaning includes removing missing values, invalid records, and duplicate reviews.

Text normalization includes case folding, emoji removal, unnecessary symbol removal, and whitespace normalization.

Review filtering includes language filtering and low-quality review removal. This step retains relevant English reviews and removes reviews that are too short, non-informative, invalid, or unsuitable for sentiment analysis.

Main outputs are stored in:

```text
data/processed/
```

### 3. Sentiment Classification

File:

```text
notebook/03_sentiment_classification_tfidf_ngram.ipynb
```

This notebook performs sentiment classification using TF-IDF and n-gram features. Several machine learning models are trained and evaluated to compare their performance.

The classification process includes:

* Feature extraction using TF-IDF.
* N-gram feature representation.
* Model training.
* Model evaluation.
* Comparison of classification performance.
* Analysis of important sentiment-related terms.

Main outputs are stored in:

```text
data/final/
outputs/
```

### 4. Imbalanced Data Handling

File:

```text
notebook/04_imbalanced_data_handling.ipynb
```

This notebook analyzes the effect of imbalanced data handling on sentiment classification performance. The experiment compares model performance before and after applying imbalance handling techniques.

The analysis includes:

* Original imbalanced dataset evaluation.
* Class weighting.
* Random oversampling.
* SMOTE.
* Performance comparison using evaluation metrics.

Main outputs are stored in:

```text
outputs/
```

## Dataset Stages

The dataset is divided into three main stages:

| Folder            | Description                                                  |
| ----------------- | ------------------------------------------------------------ |
| `data/raw/`       | Raw review data collected from Google Play Store             |
| `data/processed/` | Cleaned, filtered, and labeled review data                   |
| `data/final/`     | Final dataset used for sentiment classification and analysis |

## Sentiment Labeling

The sentiment labels are created based on review ratings:

| Rating | Sentiment Label   |
| ------ | ----------------- |
| 1–2    | Negative          |
| 3      | Removed / Neutral |
| 4–5    | Positive          |

Rating 3 is removed because it represents neutral or ambiguous sentiment. Since this project uses binary sentiment classification, only clearly negative and clearly positive reviews are retained.

## Methods Used

This project uses the following methods:

* Google Play review scraping
* Data cleaning
* Text normalization
* Review filtering
* Binary sentiment labeling
* TF-IDF feature extraction
* N-gram feature representation
* Machine learning classification
* Imbalanced data handling
* Model evaluation using classification metrics

## Evaluation Metrics

Model performance is evaluated using several classification metrics, including:

* Accuracy
* Precision
* Recall
* F1-score
* Macro average
* Weighted average
* Confusion matrix

Macro average is especially important in this project because it gives equal attention to both positive and negative sentiment classes, even when the dataset is imbalanced.

## Outputs

Generated analysis results are stored in the `outputs/` directory.

This folder may contain figures, evaluation tables, classification reports, confusion matrices, feature importance results, model comparison results, cross-validation results, and other outputs produced by the notebooks.

## Installation

Clone this repository:

```bash
git clone https://github.com/D2Firdaus/kingshot-review-sentiment-analysis.git
```

Move into the project directory:

```bash
cd kingshot-review-sentiment-analysis
```

Create a virtual environment:

```bash
python -m venv .venv
```

Activate the virtual environment.

For Windows PowerShell:

```bash
.\.venv\Scripts\Activate.ps1
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

## Usage

Run the notebooks in order:

```text
01_scrape_kingshot_reviews.ipynb
02_preprocessing_and_filtering_kingshot_reviews.ipynb
03_sentiment_classification_tfidf_ngram.ipynb
04_imbalanced_data_handling.ipynb
```

Each notebook continues the workflow from the previous stage. The raw dataset is generated in the first notebook, processed in the second notebook, classified in the third notebook, and further analyzed for class imbalance in the fourth notebook.

## References

The `reference/` directory contains supporting research papers and related studies used as references for this project.

All reference materials belong to their respective authors, publishers, or copyright holders. They are included only for academic reference and non-commercial documentation purposes. If you are a copyright holder and would like any material to be removed, please contact the repository owner.

## License

This project is licensed under the MIT License.
