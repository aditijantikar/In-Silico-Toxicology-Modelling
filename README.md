**In Silico Toxicology Modeling for Drug Discovery**

**Project Overview:**

This project builds upon the "In Silico Toxicology Modeling" tutorial originally created by Dr. Layla Hosseini-Gerami and Srijit Seal. While the initial framework is based on their work, this repository has been extended to include the implementation and hyperparameter tuning of a LightGBM model, which is then compared against the original Random Forest baseline.

The goal was to demonstrate a complete machine learning workflow, from reproducing a baseline to optimizing and validating a more advanced algorithm.

**Methodology & Results:**

A baseline Random Forest model was first established, achieving an AUC-ROC of 0.835 and an F1-score of 0.50 for the toxic class. To improve upon this, an advanced LightGBM model was implemented. Its hyperparameters were systematically optimized using a 5-fold cross-validated grid search (GridSearchCV).

Performance Comparison
The final optimized LightGBM model showed a clear improvement in performance across key metrics:
| Metric | Baseline Random Forest | Optimized LightGBM | Outcome |
| :--- | :--- | :--- | :--- |
| **AUC-ROC** | 0.835 | **0.863** |  **Improved** |
| **F1-Score (Toxic)** | 0.50 | **0.54** |  **Improved** |
| **Precision (Toxic)**| 0.39 | **0.68** |  **Significantly Improved** |
| **Recall (Toxic)** | 0.69 | 0.45 |  Decreased |

**Model Strengths & Interpretation:**

The optimized LightGBM model demonstrates several key advantages over the baseline Random Forest:

Higher Predictive Certainty: The most significant improvement is in precision for the toxic class (0.68 vs. 0.39). This means when the LightGBM model flags a compound as toxic, it is far more likely to be correct, reducing the rate of false alarms.

Superior Overall Performance: The higher AUC-ROC (0.863 vs. 0.835) and F1-Score (0.54 vs. 0.50) confirm that the new model is a more robust and reliable classifier overall.

Excellent "Safe" Compound Identification: The model maintains a very high recall (0.97) for non-toxic compounds, making it an effective tool for quickly and reliably filtering out molecules that are likely safe.

In a real-world drug discovery pipeline, this model would serve as a more efficient screening tool. It provides higher confidence in its positive "toxic" predictions, allowing researchers to prioritize better which compounds warrant expensive and time-consuming laboratory follow-ups.

**Technologies Used:**

Python

Pandas

Scikit-learn

LightGBM

RDKit

Matplotlib

Jupyter Notebook/ Google Colab

**Attribution**

Original Work By: Dr. Layla Hosseini-Gerami and Srijit Seal (July 2024)

Original Source: https://colab.research.google.com/drive/1rkt95bjiIw6B0RvG7qs9nN0xUGmMyvGi?usp=sharing

