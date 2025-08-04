# Imperial-Final-Project
Final Project for Imperial Machine Learning Certification - Credit card default prediction
# Project title : Credit Default Prediction using Random Forest

## NON-TECHNICAL EXPLANATION OF YOUR PROJECT
This project uses machine learning to predict whether a credit card customer is likely to default on their next payment. By learning from past payment behavior and demographics, the model helps financial institutions identify high-risk individuals. This can support more informed and fair lending decisions.

## DATA
We use the "Default of Credit Card Clients" dataset from the UCI Machine Learning Repository, containing 30,000 customer records from a Taiwanese bank. Each entry includes demographic information and monthly bill/payment history.  
Source: https://archive.ics.uci.edu/ml/datasets/default+of+credit+card+clients

## MODEL 
We use a Random Forest Classifier, which performs well on tabular data and handles class imbalance using built-in `class_weight='balanced'`. It is also interpretable via feature importance. The model outputs probabilities, which we post-process using a tuned classification threshold.

## HYPERPARAMETER OPTIMSATION
Key hyperparameters explored:
- Number of estimators (trees)
- Max depth
- Class weighting
Threshold tuning was performed by inspecting the precision-recall curve. Based on this, we chose a threshold of **0.35** to improve recall for defaulters.

## RESULTS
- ROC AUC: 0.76
- Accuracy: ~78%
- Recall (defaulters): Improved from 37% to over 50% at threshold 0.35
- Precision (defaulters): Slightly reduced but acceptable

This threshold adjustment helped the model capture more risky customers at the cost of a few more false positives.
