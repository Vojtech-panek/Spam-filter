# Spam Filter

This project explores how to build a machine-learning spam filter from raw email
messages. It follows the examples and techniques from *Hands-On Machine Learning
with Scikit-Learn, Keras & TensorFlow* by Aurélien Géron.

The main implementation is in [spam.ipynb](spam.ipynb). The notebook loads
real email messages, prepares them for machine learning, and develops the
feature-extraction and classification workflow step by step.

## What the notebook does

- Downloads and extracts the Apache SpamAssassin Public Corpus when the local
  dataset is missing.
- Parses raw email files, including MIME headers and multipart messages.
- Extracts readable content from plain-text and HTML emails.
- Normalizes text by lowercasing it, replacing URLs and numbers, removing
  punctuation, and applying Porter stemming.
- Converts each email into word-count features suitable for a classifier.
- Splits the messages into training and test sets for model evaluation.

## Dataset

The project uses the [Apache SpamAssassin Public Corpus](https://spamassassin.apache.org/old/publiccorpus/),
which contains legitimate (`ham`) and spam email messages. The notebook
downloads the `easy_ham` and `spam` archives into `datasets/` if those folders
do not already exist.

The email corpus is stored locally and is not tracked by Git.

## Setup and usage

Create or activate a Python environment, then install the notebook dependencies:

```bash
python -m pip install -r requirements.txt
```

Open and run [spam.ipynb](spam.ipynb) from this directory. The first dataset
download requires an internet connection; later runs reuse the extracted files.

## Project structure

```text
Spam-filter/
├── datasets/       # Local SpamAssassin data (not tracked by Git)
├── spam.ipynb      # Main data preparation and classification notebook
├── README.md       # Project documentation
├── requirements.txt # Python dependencies
├── LICENSE
└── .gitignore
```