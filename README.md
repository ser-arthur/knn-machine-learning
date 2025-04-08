# Thief Zone Classification using k-Nearest Neighbours (kNN)

This project applies the K-Nearest Neighbours (KNN) machine learning algorithm to classify a suspected thief zone in the Lismore field using petrophysical data.

A **thief zone** is a high-permeability interval that may divert injected fluids away from productive reservoir zones due to its superior flow capacity. Accurately identifying such zones is critical in reservoir management and enhanced oil recovery.

---

## Project Structure

```
├── KNN-thief-zone-classifier.ipynb      # Main Jupyter Notebook
├── KNN Classification - Report.pdf      # Full written report with workflow and interpretation
├── petrophysical_data.xlsx              # Dataset with petrophysical properties
├── README.md                            # Project summary and guide
```

---

## Problem Overview

The goal was to:
- Define thief zone classification criteria based on geological insight and statistical analysis.
- Apply the KNN algorithm to classify a test zone using training data from known formations.
- Validate model accuracy using cross-validation techniques suited for small datasets.

---

## Methods Used

- **Data Cleaning:** Removed missing values, excluded the Zechstein zone, and standardized numerical inputs.
- **Exploratory Analysis:** Histogram distribution, summary statistics, and correlation matrix were used to define thief zone thresholds.
- **Labeling:** Thief zones were defined as intervals with high permeability (`KLOGH_arithmetic > 66 mD`) and moderate-to-low NTG (`< 0.75`), based on data percentiles and reservoir insights.
- **Modeling:** A KNN classifier (k=3) was trained using 8 petrophysical features.
- **Validation:** LOOCV and Stratified K-Fold were used to ensure robustness despite class imbalance (only 2 thief zones in dataset).
- **Interpretation:** The test zone was classified as a thief zone. Visualization of the classification was included for interpretability.

---

## Key Outcomes

- **Test Zone Prediction:** Classified as a thief zone by majority vote of 3 nearest neighbors.
- **Validation Accuracy:** ~77.8% (LOOCV) and ~77.5% (Stratified K-Fold).
- **Insights:** KNN proved flexible and effective, accounting for multiple feature patterns rather than fixed thresholds.

---

## Learning Highlights

- KNN is useful in small, interpretable datasets where class boundaries are based on feature similarity.
- Combining domain knowledge with statistical thresholds supports better model inputs.
- Model validation methods like LOOCV are critical when data is limited.

---

## How to View

You can explore the notebook directly on GitHub, in JupyterNotebook or [View via nbviewer](https://nbviewer.org/github/ser-arthur/knn-machine-learning/blob/main/knn-thief-zone-classifier.ipynb).

---

## References

- Altman, N. S. (1992). *An introduction to kernel and nearest-neighbour non-parametric regression*. The American Statistician.
- Kohavi, R. (1995). *A study of cross-validation and bootstrap for accuracy estimation and model selection*. IJCAI.
- Liu et al. (2021). *The Characteristics and Origins of Thief Zones in the Cretaceous Limestone Reservoirs...* Journal of Petroleum Science and Engineering, 201.
