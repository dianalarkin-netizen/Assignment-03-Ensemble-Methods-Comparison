# Insurance Claim Prediction — Predictive Analytics Assignment

Link to Google Colab: https://colab.research.google.com/drive/1dOUuPl9mu8nVx9gQfmNyYWTUOVRBkjkY?usp=sharing

## Industry / Domain
This project is situated in the **personal lines property and casualty auto insurance industry**.  
The business problem centers on predicting whether an auto insurance claim will exceed \$10,000, which is critical for reserve planning, underwriting, and financial risk management.

---

## Dataset Description and Source
- **Dataset Size:** 123,294 auto insurance policies  
- **Target Variable:** `CLAIM_OVER_10K` (binary: 1 if claim > \$10,000, else 0)  
- **Positive Class:** 8,034 claims (≈6.5%) exceeded \$10,000  
- **Features:** 301 after one-hot encoding, including premium amount, insured value, production year, vehicle type, engine capacity, seats, carrying capacity, and manufacturer.  
- **Source:** [Vehicle Insurance Data on Kaggle](https://www.kaggle.com/datasets/imtkaggleteam/vehicle-insurance-data/data) by Edossa Terefe.  

---

## Summary of Findings
Three models were built and compared:  
- **Decision Tree (balanced weights):** Recall = 90%, Precision = 13%, Accuracy = 58%.  
  - Captured nearly all costly claims but flagged many false positives.  
- **Random Forest (balanced weights):** Accuracy = 88%, Recall = 22%, Precision = 17%.  
  - More stable overall but missed most costly claims.  
- **Gradient Boosting (with imputation):** Accuracy = 93%, Precision = 50%, Recall ≈ 0%.  
  - Strong accuracy but failed to identify costly claims.  

**Key Insight:**  
- Accuracy alone is misleading in imbalanced datasets.  
- **Recall is the most critical metric** for personal lines auto insurers because missing high-value claims leads to underestimating reserves and financial risk.  
- The **Decision Tree** provided the most business value despite lower accuracy, as it ensured most costly claims were flagged.  

**Business Impact:**  
- Decision Tree identified ~\$108M in costly claims.  
- Random Forest identified ~\$26M.  
- Gradient Boosting identified ~\$150K.  

**Recommendation:**  
Use the **Decision Tree** as the primary model for flagging high-value claims, due to its high recall and interpretability.  
Future work should explore hybrid approaches that combine high recall with improved precision.
