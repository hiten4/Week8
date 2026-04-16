# Hospital Readmission Prediction using Neural Network from Scratch

## Project Overview

This project analyzes hospital patient records, performs full data cleaning, and builds a **3-layer Neural Network in NumPy from scratch** to predict whether a patient will be readmitted within 30 days.

The project also compares the custom model with an equivalent sklearn model and finds the best prediction threshold based on hospital business cost.

File used for implementation:

* `Week-8-Thuesday.ipynb`

---

## Objectives

1. Audit dataset quality and identify issues.
2. Clean and preprocess the hospital records dataset.
3. Build a Neural Network using only NumPy.
4. Train and evaluate the model.
5. Compare results with sklearn MLPClassifier.
6. Optimize threshold using clinical cost assumptions.

---

## Dataset

Input file:

* `hospital_records.csv`

Target column:

* `readmitted_30d`

Features include:

* Age
* Gender
* Department
* Length of stay
* Blood pressure
* Glucose
* Creatinine
* BMI
* Number of medications
* Number of diagnoses
* Insurance type
* ICU stay
* Admission date features

---

## Data Quality Issues Found

* Missing values in clinical columns
* BMI stored as text
* Mixed date formats
* Inconsistent gender labels
* Department formatting issues
* Invalid patient IDs
* Missing insurance values

---

## Cleaning Steps

* Filled missing numeric values using median
* Filled missing categorical values using mode
* Converted BMI to numeric
* Standardized gender labels
* Standardized department names
* Parsed dates correctly
* Fixed invalid patient IDs
* Scaled features before training

---

## Neural Network Architecture

* Input Layer = Number of features
* Hidden Layer 1 = 16 neurons (ReLU)
* Hidden Layer 2 = 8 neurons (ReLU)
* Output Layer = 1 neuron (Sigmoid)

Loss Function:

* Binary Cross Entropy

Optimizer:

* Gradient Descent

Learning Rate:

* 0.01

Epochs:

* 500

---

## Evaluation Metric

Used **F1 Score** because hospital readmission is an imbalanced classification problem. Accuracy alone can be misleading.

---

## Cost Optimization

Clinical cost assumptions:

* False Negative = ₹50,000
  (missed risky patient)

* False Positive = ₹5,000
  (unnecessary follow-up)

The best threshold is selected by minimizing total expected cost.

---

## How to Run

Install dependencies:

```bash
pip install pandas numpy matplotlib scikit-learn
```

Run project:

```bash
python main.py
```

---

## Output

The program will generate:

* Cleaned dataset processing
* Neural network training
* Loss curve plot
* F1 score of NumPy model
* F1 score of sklearn model
* Best threshold
* Minimum expected clinical cost

---

## Learning Outcomes

This project demonstrates:

* Real-world data cleaning
* Neural network fundamentals
* Forward propagation
* Backpropagation
* Model evaluation
* Cost-sensitive decision making

---
