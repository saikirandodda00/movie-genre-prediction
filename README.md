
# Movie Genre Prediction (Multi-Label Classification)

## Objective
The goal of this project is to predict the genre of movies and TV shows using metadata and text information. Since a single title can belong to multiple genres, this is treated as a multi-label classification problem.
--------------------------------------------------------------------------------------------------------------
## Approach

### 1. Data Preprocessing
- Cleaned data quality issues (incorrect values in columns)
- Extracted useful features such as duration and year added
- Handled missing values
- Converted genre column into a list format for multi-label processing

---

### 2. Feature Engineering
We created three types of features:

- Text Features:
  - Used TF-IDF on the `description` column to convert text into numerical form

- Numerical Features:
  - Included fields like release year, duration, and flags such as is_movie

- Categorical Features:
  - Encoded columns like rating and country using one-hot encoding

All features were combined into a single matrix for model training.

---

### 3. Models Used

We trained and compared three models:

- Logistic Regression:
  - Used as a baseline model

- XGBoost:
  - Used to capture non-linear relationships

- Linear SVM:
  - Works well with high-dimensional text data

Each model was wrapped using OneVsRestClassifier to support multi-label classification.

---

### 4. Evaluation

We used F1 score (micro and macro) as the main evaluation metric because:
- The dataset is multi-label
- It balances precision and recall

### Results:

| Model              | F1 Score (Micro) |
|--------------------|------------------|
| Logistic Regression | ~0.55           |
| XGBoost            | ~0.60           |
| Linear SVM         | ~0.64           |

---

### 5. Explainability

To understand model behavior:
- Extracted top features (words) from the SVM model
- Observed that meaningful keywords like "action", "love", "crime" influence predictions

This confirms that the model is learning relevant patterns from the text data.

---

## Final Model

Linear SVM is selected as the final model because:
- It achieved the highest F1 score
- It works well with TF-IDF features
- It handles high-dimensional sparse data effectively

---

## How to Run

1. Install dependencies:
2. Open the notebook:
3.  Run all cells in order

---

## Conclusion


This project demonstrates a complete machine learning pipeline:
- Data cleaning and preprocessing
- Feature engineering
- Model training and comparison
- Evaluation and explainability

The final model (Linear SVM) provides a good balance of performance and interpretability for this problem.
