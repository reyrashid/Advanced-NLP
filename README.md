# Advanced-NLP
This repositiry contains codes for projects completed during the Advanced NLP course, focusing on Semantic Role Labeling (SRL).

## **Assignment 1: Feature-Based SRL**
This project involves building a traditional machine learning system to automatically label PropBank semantic roles given a predicate. 
*   **Model:** A **Logistic Regression** classifier trained on the Universal Propbank V1.0 dataset.
    *   **Evaluation:** Precision, Recall, and F1-measures using Scikit-learn’s classification report and a labeled confusion matrix.

## **Assignment 2: Transformer-Based SRL**
This project fine-tunes a Large Language Model (LLM) for sequence labeling.
*   **Model:** Fine-tuned **BERT-family** models (primarily `distilbert-base-uncased`).
*   **Methodology:**
    *   **Input Adaption:** Implementing predicate marking within the transformer input to handle SRL-specific requirements.
    *   **Tokenization:** Managing the relationship between **subword tokenization** and token-level gold labels.
    *   **Post-processing:** Applying heuristics to convert subword-level predictions back to the token-level format required by the shared task.

## **Take-Home Exam: Challenging SRL Models**
The final project focuses on the behavioral testing and evaluation of the models developed in Assignments 1 and 2.
*   **Objective:** To go "beyond accuracy" by identifying model weaknesses using **CheckList-style testing**
