# Model Card

## Model Description

**Input:**  
The model takes in a variety of features related to a credit card customer's demographic and financial history. These include:
- Demographic variables: `SEX`, `EDUCATION`, `MARRIAGE`, `AGE`
- Credit attributes: `LIMIT_BAL`, `BILL_AMT1-6`, `PAY_AMT1-6`, `PAY_0-6` (past payment history)
  
All features are numerical or ordinal. The dataset contains no missing values.

**Output:**  
The model outputs a binary classification:
- `1`: Likely to default on the credit card next month
- `0`: Not likely to default

Probabilistic scores are generated and evaluated initially with a classification threshold of 0.5 and then using a custom classification threshold of **0.35** to better balance recall and precision.

**Model Architecture:**  
The model is a **Random Forest Classifier**, an ensemble method that builds multiple decision trees and outputs the class that is the mode of the individual trees. It is:
- Robust to overfitting
- Able to handle non-linear interactions
- Trained using `class_weight='balanced'` to address class imbalance

## Performance

**Metrics Evaluated (at threshold = 0.35):**
- Accuracy: **~77–80%** (expected drop due to more false positives)
- ROC AUC: **0.76**
- F1-score (Class 1 / defaulters): **Improved vs threshold=0.5**
- Recall (Class 1): **Significantly improved** (compared to 0.37 at threshold=0.5)
- Precision (Class 1): **Slightly decreased**, acceptable trade-off

**Evaluation Methodology:**
- 80/20 train-test split
- Evaluation on the test set only
- Threshold optimization based on the precision-recall curve

## Limitations

- **Class imbalance:** Still a limitation, although thresholding helps improve recall.
- **Static data:** Time-invariant features; no updates over customer lifecycle.
- **Bias risk:** Model has not yet been fairness-audited.
- **Interpretability:** Moderate, improved by feature importance but still limited.

## Trade-offs

- **Threshold tuning (0.35):** Helps detect more defaulters (higher recall) at the cost of slightly more false positives.
- **Precision vs Recall:** Priority was given to **recall**, based on the business use case.
- **Model complexity:** More advanced models (e.g., XGBoost) could be tested in future iterations.
