# W8 Wednesday Assignment – CNN + Embeddings

## Overview
This assignment covers:
- CNN model on MNIST dataset
- Hate speech detection using Twitter data
- Semantic search using embeddings
- TF-IDF vs Embedding comparison
- Two-stage moderation pipeline

---

## Dataset
- Twitter_Data.csv
  - clean_text → text
  - category → hate_speech

---

## How to Run
1. Open notebook in Google Colab
2. Upload Twitter_Data.csv
3. Run all cells

---

## Steps

### 1. Data Understanding
- Checked class distribution
- Found class imbalance
- Handled missing values

### 2. CNN (MNIST)
- Built CNN with 2 Conv layers + MaxPooling
- Normalized images
- Trained model

### 3. Hate Speech Model
- TF-IDF vectorization
- Logistic Regression
- Balanced handling

### 4. Semantic Search
- Sentence Transformers used
- Cosine similarity applied

### 5. Moderation Pipeline
- Stage 1: Classifier
- Stage 2: Semantic similarity

---

## TF-IDF vs Embeddings
- TF-IDF: keyword-based
- Embeddings: context-based (better)

---

## Requirements
- Python 3.8+
- pandas, numpy
- scikit-learn
- tensorflow / keras
- sentence-transformers

---

## AI Usage
Prompt used: Create CNN + NLP pipeline  
Changes made: Fixed dataset columns, improved pipeline

---

## Author
Hiten Mistry
