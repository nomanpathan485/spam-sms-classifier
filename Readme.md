# Spam SMS Classifier

A simple Natural Language Processing (NLP) project that classifies SMS messages as Spam or Ham (Not Spam).

## Project Overview

This project uses the SMS Spam Collection Dataset and applies the Bag of Words technique using CountVectorizer. The text data is converted into numerical features and then classified using Logistic Regression.

## Dataset

SMS Spam Collection Dataset

Classes:

* Ham (0)
* Spam (1)

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-Learn
* CountVectorizer
* Logistic Regression
* Jupyter Notebook

## Workflow

1. Load Dataset
2. Data Cleaning
3. Label Encoding
4. Train-Test Split
5. Text Vectorization using CountVectorizer
6. Train Logistic Regression Model
7. Evaluate using:

   * Accuracy
   * Confusion Matrix
   * Precision
   * Recall
   * F1 Score
8. Save Model using Pickle

## Results

Accuracy: 97.76%

Classification Report:

Spam Class:

* Precision: 0.99
* Recall: 0.84
* F1 Score: 0.91

## Learning Outcomes

Through this project I learned:

* How machines process text data
* Bag of Words representation
* CountVectorizer
* Logistic Regression for NLP
* Precision and Recall
* Confusion Matrix
* Model Serialization using Pickle

## Future Improvements

* TF-IDF Vectorization
* Naive Bayes Comparison
* Streamlit Web App
* Transformer-based Models

## Author

Noaman Ayub pathan
