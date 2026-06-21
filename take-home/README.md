# SRL Challenge Dataset — Take-Home Exam
## Rey Rashid

This repository contains the code, dataset, and model outputs for evaluating two SRL systems
(Logistic Regression and fine-tuned DistilBERT) on a CheckList-style challenge dataset.

---

## Structure

```
.
├── take-home.ipynb             # Main notebook: dataset, evaluation, results
├── challenge_dataset.json      # Generated challenge dataset (64 instances, 8 sub-tests)
├── a1_challenge_output.json    # LR model predictions on challenge dataset
├── a2_challenge_output.json    # BERT model predictions on challenge dataset
├── srl_model.joblib            # Logistic Regression model (see Download section)
├── srl_model_seed_42/          # DistilBERT model directory (see Download section)
│   ├── config.json
│   ├── tokenizer_config.json
│   ├── special_tokens_map.json
│   ├── vocab.txt
│   └── model.safetensors (or pytorch_model.bin)
├── requirements.txt
└── README.md
```

---

## Model Downloads

The models are too large to include directly. Download them with the provided links.

### Logistic Regression model (`srl_model.joblib`)
**Download:** https://drive.google.com/file/d/15N5L6AoOLRwKNYTZ0OLwiKphtISqqUe0/view?usp=drive_link

Place the downloaded file in the root of the repository (same folder as the notebook):
```
./srl_model.joblib
```

### DistilBERT model (`srl_model_seed_42/`)
**Download:** https://drive.google.com/file/d/1z3B6FT1yDqhhbTsw__Wmy5q9Omt94ZBQ/view?usp=sharing

The download is a zip archive. Extract it so the folder structure looks like:
```
./srl_model_seed_42/
    config.json
    tokenizer_config.json
    special_tokens_map.json
    vocab.txt
    model.safetensors
```
The notebook loads the BERT model using:
```python
AutoModelForTokenClassification.from_pretrained('./srl_model_seed_42')
AutoTokenizer.from_pretrained('./srl_model_seed_42')
```
So the folder **must be named `srl_model_seed_42`** and placed in the **root of the repository**.

---

## Setup

### 1. Python version
Python 3.9 or higher is recommended.

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Download the spaCy model
The Logistic Regression model uses the `en_core_web_md` spaCy pipeline for dependency parsing,
lemmatization, and POS tagging. Download it after installing spaCy:
```bash
python -m spacy download en_core_web_md
```

---

## Running the Notebook

Open the notebook in Jupyter and run all cells in order:
```bash
jupyter notebook take-home.ipynb
```
Or with JupyterLab:
```bash
jupyter lab take-home.ipynb
```