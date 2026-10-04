# Sonar Rock vs Mine — Machine Learning Comparison

A comparative Machine Learning project for classifying sonar signals as **Rock (`R`)** or **Mine (`M`)** using **Logistic Regression** and **SVM with an RBF kernel**.

## 📊 Datasets

| Dataset | Rows | Columns | Features |
|---|---:|---:|---:|
| Original Sonar | 208 | 61 | 60 |
| Expanded Sonar | 1,000 | 61 | 60 |

The 1,000-row dataset is an expanded **synthetic** dataset.

## 🤖 Models

- **Logistic Regression**
- **SVM (RBF)** with `StandardScaler`, `C=10`, `gamma="scale"`

Both notebooks use a **90/10 stratified train-test split** and **5-fold stratified cross-validation**.

## 📈 Logistic Regression Results

| Metric | 208 Rows | 1,000 Rows |
|---|---:|---:|
| Test Accuracy | **76.19%** | **85.00%** |
| Mean CV Accuracy | **75.52%** | **88.30%** |

### Logistic Regression Dashboard

<img width="833" height="700" alt="image" src="https://github.com/user-attachments/assets/05b63599-f92b-43b9-b317-88d576e53c0b" />


**Observation:** Expanding the dataset improved both test accuracy and cross-validation performance.

## 📈 SVM (RBF) Results

| Metric | 208 Rows | 1,000 Rows |
|---|---:|---:|
| Test Accuracy | **95.24%** | **99.00%** |
| Mean CV Accuracy | **87.54%** | **99.90%** |

### SVM Dashboard

<img width="833" height="700" alt="image" src="https://github.com/user-attachments/assets/f7060b5b-c6ef-4ea7-84db-cf6185bc2415" />


**Observation:** SVM outperformed Logistic Regression on both datasets.

## 🏆 Model Comparison

### Original 208-row dataset

| Model | Test Accuracy | CV Mean |
|---|---:|---:|
| Logistic Regression | 76.19% | 75.52% |
| **SVM (RBF)** | **95.24%** | **87.54%** |

### Expanded 1,000-row dataset

| Model | Test Accuracy | CV Mean |
|---|---:|---:|
| Logistic Regression | 85.00% | 88.30% |
| **SVM (RBF)** | **99.00%** | **99.90%** |

## 🔎 Key Findings

- **SVM is the strongest model** in the current experiments.
- On 208 rows, SVM improves test accuracy over Logistic Regression by **19.05 percentage points**.
- On 1,000 rows, SVM improves test accuracy by **14.00 percentage points**.
- The 208-row SVM result is **95.24% test accuracy**, but its 5-fold CV mean is **87.54%**, showing that a single small test split can be optimistic.
- The very high **99.90% CV** on the 1,000-row dataset should be interpreted cautiously because the additional records are synthetic.

## 📁 Repository Structure

```text
Rock-vs-Mine-Sonar-ML/
├── README.md
├── Copy of sonar data.csv
├── Sonar_Rock_vs_Mine_1000.csv
├── Sonar_LogisticRegression_208_vs_1000_Analysis.ipynb
├── Sonar_SVM_208_vs_1000_Analysis.ipynb
└── sonar_dashboard_assets/
    ├── logistic_regression_dashboard.png
    └── svm_dashboard.png
```

## 📊 Interactive Analysis

The notebooks include:

- Interactive Plotly dashboards
- Accuracy comparison charts
- 5-fold cross-validation analysis
- Confusion matrices
- Precision, Recall and F1-score
- Sample prediction analysis

For full interactive charts, open the notebooks in **Google Colab or Jupyter**.

## ⚠️ Limitation

The 1,000-row dataset is synthetic/expanded. Its very high validation scores should **not** be interpreted as guaranteed real-world sonar detection accuracy. Independent real-world validation is required.

## 🛠️ Tech Stack

`Python` · `Pandas` · `NumPy` · `Scikit-learn` · `Plotly` · `Jupyter/Colab`

## 👨‍💻 Author

**Mrunal Jadhav**
