# Social Network Ads – Decision Tree Classifier

This repository contains a Machine Learning pipeline that uses a **Decision Tree Classifier** to predict whether a user will purchase a product based on their demographic and financial profile (Age, Gender, and Estimated Salary).

---

## 📌 Table of Contents

* [Overview](https://www.google.com/search?q=%23overview)
* [Dataset Description](https://www.google.com/search?q=%23dataset-description)
* [Requirements & Tech Stack](https://www.google.com/search?q=%23requirements--tech-stack)
* [Workflow & Methodology](https://www.google.com/search?q=%23workflow--methodology)
* [Model Performance](https://www.google.com/search?q=%23model-performance)
* [Installation & Usage](https://www.google.com/search?q=%23installation--usage)

---

## 📖 Overview

Targeted advertising relies heavily on understanding customer purchasing behavior. This project explores the **Social Network Ads** dataset to analyze customer attributes and train a binary classification model that accurately predicts ad conversion (`Purchased`: 1 or 0).

---

## 📊 Dataset Description

The dataset consists of **400 records** with the following features:

| Column Name | Data Type | Description |
| --- | --- | --- |
| **User ID** | Integer | Unique identifier for each user *(Dropped during training)* |
| **Gender** | Object | User gender (`Male` or `Female` — One-Hot Encoded) |
| **Age** | Integer | Age of the user |
| **EstimatedSalary** | Integer | Annual estimated salary of the user |
| **Purchased** | Integer | Target variable (`0` = Did Not Purchase, `1` = Purchased) |

---

## 🛠️ Requirements & Tech Stack

* **Language:** Python 3.x
* **Libraries:**
* `pandas` - Data manipulation & tabular analysis
* `numpy` - Numerical processing
* `matplotlib` - Data visualization & decision tree plotting
* `scikit-learn` - Machine learning model building & evaluation metrics



---

## ⚙️ Workflow & Methodology

1. **Data Loading & Inspection:**
* Loaded `Social_Network_Ads.csv` using `pandas`.
* Verified data integrity and checked for missing values (`0` null values found).


2. **Feature Engineering & Preprocessing:**
* One-Hot Encoded the categorical variable `Gender` (converted to `Gender_Male`).
* Dropped non-predictive identifiers (`User ID`).
* Separated features ($X$) and target variable ($y$).


3. **Data Splitting:**
* Performed an **80/20 train-test split** using stratified sampling (`stratify=y`, `random_state=42`) to maintain class balance.


4. **Model Training:**
* Implemented a `DecisionTreeClassifier` with `max_depth=5` and `criterion='gini'` to prevent overfitting.


5. **Evaluation:**
* Evaluated model accuracy, precision, recall, f1-score, and generated a confusion matrix.



---

## 📈 Model Performance

The tuned Decision Tree Classifier achieved solid performance on the unseen test set ($80$ samples):

* **Test Accuracy:** `82.50%`

### Classification Report

| Class | Precision | Recall | F1-Score | Support |
| --- | --- | --- | --- | --- |
| **Not Purchased (0)** | `0.88` | `0.84` | `0.86` | 51 |
| **Purchased (1)** | `0.74` | `0.79` | `0.77` | 29 |
| **Overall Accuracy** |  |  | **`0.82`** | **80** |

### Confusion Matrix

```text
[[43   8]
 [ 6  23]]

```

* **True Negatives (TN):** 43
* **False Positives (FP):** 8
* **False Negatives (FN):** 6
* **True Positives (TP):** 23

---

## 🚀 Installation & Usage

1. **Install required dependencies:**
```bash
pip install pandas numpy matplotlib scikit-learn jupyter

```


2. **Run the Notebook:**
```bash
jupyter notebook

```

## Conclusion 

The Decision Tree model achieved **82.50%** accuracy on the test dataset. For Not Purchased, the model achieved 88% precision and **86% F1-score**, while for Purchased, it achieved **74% precision** and **77% F1-score**, with a **79% recall**. Overall, the model provides a reliable baseline for predicting customer purchase behavior and supporting data-driven marketing decisions.
