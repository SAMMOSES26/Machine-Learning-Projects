<div align="center">

# 🩺 Fetal Health Classification Using Machine Learning

### Predicting fetal health outcomes from Cardiotocographic (CTG) data with 96.22% accuracy

[![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![XGBoost](https://img.shields.io/badge/XGBoost-189AB4?style=for-the-badge)](https://xgboost.readthedocs.io)
[![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org)
[![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org)

**MSc Data Analytics Dissertation · De Montfort University · 2023–2024**

[View Notebooks](#-project-notebooks) · [Key Results](#-results) · [Skills Demonstrated](#-skills-demonstrated)

</div>

---

## 🎯 Project Overview

Fetal health monitoring is one of the most critical challenges in modern medicine. This project builds and compares multiple machine learning models to **automatically classify fetal health status** from Cardiotocography (CTG) data into three categories: **Normal**, **Suspect**, and **Pathological** — helping clinicians make faster, more reliable decisions.

> **Real-world impact:** Manual CTG interpretation is inconsistent between clinicians. This ML pipeline reduces that subjectivity and is especially valuable in under-resourced healthcare settings.

**What this project covers end-to-end:**
- Exploratory data analysis on real medical data
- Solving class imbalance using SMOTE
- Comparing 6 ML models scientifically
- Feature selection using 4 different techniques
- Hyperparameter tuning to squeeze out maximum performance
- Evaluation with clinical-grade metrics (precision, recall, F1)

---

## 🏆 Results

| Pipeline Stage | Best Model | Accuracy | F1 Score |
|---|---|---|---|
| Raw Data (Baseline) | XGBoost | 92.96% | — |
| + SMOTE Balancing | Random Forest | 92.96% | ↑ Minority class recall |
| + Feature Selection | Random Forest | 95.04% | 94.95% |
| ✅ **+ Hyperparameter Tuning** | **Random Forest** | **96.22%** | **96.18%** |

**Best Model Performance (Tuned Random Forest):**
```
Accuracy:   96.22%
Precision:  96.20%
Recall:     96.17%
F1 Score:   96.18%
```

> Random Forest outperformed all 5 competing models at every stage of the pipeline.

---

## 🛠️ Skills Demonstrated

This project demonstrates a **full production-grade ML workflow** — not just model fitting:

| Skill Area | What I Did |
|---|---|
| **Data Analysis** | EDA with correlation heatmaps, distribution plots, outlier detection |
| **Class Imbalance** | Applied SMOTE to upsample minority classes; evaluated impact on recall |
| **Feature Engineering** | Compared Pearson correlation, Forward Selection, Backward Elimination, RFE |
| **Model Development** | Built and compared 6 classifiers: LR, KNN, Decision Tree, RF, XGBoost, SVM |
| **Hyperparameter Tuning** | Used Randomized Search CV to optimise top 3 models |
| **Model Evaluation** | Confusion matrices, precision/recall/F1, class-wise performance analysis |
| **Scientific Methodology** | Controlled multi-stage experiments with reproducible baselines |

---

## 🔄 ML Pipeline
```
 Raw CTG Data (2,126 records · 21 features)
        │
        ▼
 ┌─────────────────────────────┐
 │  Exploratory Data Analysis  │  ← Distributions, correlations, class imbalance
 └──────────────┬──────────────┘
                │
                ▼
 ┌─────────────────────────────┐
 │     Data Preprocessing      │  ← SMOTE (class balancing) + Min-Max Scaling
 └──────────────┬──────────────┘
                │
                ▼
 ┌─────────────────────────────┐
 │      Feature Selection      │  ← Pearson · Forward · Backward · RFE
 └──────────────┬──────────────┘
                │
                ▼
 ┌─────────────────────────────┐
 │      Model Training ×6      │  ← LR · KNN · DT · RF · XGBoost · SVM
 └──────────────┬──────────────┘
                │
                ▼
 ┌─────────────────────────────┐
 │    Hyperparameter Tuning    │  ← Randomized Search CV on top 3 models
 └──────────────┬──────────────┘
                │
                ▼
 ✅ Final Model: Random Forest · 96.22% Accuracy · 96.18% F1
```

---

## 📊 Dataset

| Property | Detail |
|---|---|
| Source | [Kaggle — Fetal Health Classification](https://www.kaggle.com/datasets/andrewmvd/fetal-health-classification) |
| Records | 2,126 CTG observations |
| Features | 21 (FHR, uterine contractions, accelerations, decelerations, etc.) |
| Target | 3 classes: Normal (77%) · Suspect (14%) · Pathological (9%) |
| Challenge | Heavy class imbalance — addressed using SMOTE |

---

## 📁 Project Notebooks

Run in order for the full pipeline:

| # | Notebook | Description |
|---|---|---|
| 1 | `01_EDA.ipynb` | Data exploration, distributions, correlation heatmaps |
| 2 | `02_Preprocessing.ipynb` | SMOTE class balancing + Min-Max scaling |
| 3 | `03_Feature_Selection.ipynb` | Pearson, Forward, Backward Elimination, RFE |
| 4 | `04_Model_Training.ipynb` | Train and compare all 6 ML models |
| 5 | `05_Hyperparameter_Tuning.ipynb` | Randomized Search CV for top 3 models |

---

## 🚀 Run It Yourself
```bash
# 1. Clone the repo
git clone https://github.com/your-username/fetal-health-classification.git
cd fetal-health-classification

# 2. Create virtual environment
python -m venv venv
source venv/bin/activate       # Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Launch Jupyter
jupyter notebook
```

**Dependencies (`requirements.txt`):**
```
pandas>=1.5
numpy>=1.23
scikit-learn>=1.2
xgboost>=1.7
imbalanced-learn>=0.10
matplotlib>=3.6
seaborn>=0.12
jupyter
```

---

## 📂 Repository Structure
```
fetal-health-classification/
├── 📂 data/
│   └── fetal_health.csv
├── 📂 notebooks/
│   ├── 01_EDA.ipynb
│   ├── 02_Preprocessing.ipynb
│   ├── 03_Feature_Selection.ipynb
│   ├── 04_Model_Training.ipynb
│   └── 05_Hyperparameter_Tuning.ipynb
├── 📂 models/
│   └── random_forest_final.pkl
├── 📂 results/
│   ├── confusion_matrices/
│   └── performance_summary.csv
├── requirements.txt
└── README.md
```

---

## 🔭 What I'd Do Next

- **Deep learning:** Explore LSTM/CNN for sequence-aware CTG signal analysis
- **Explainability:** Apply SHAP values to explain individual predictions for clinicians
- **Deployment:** Wrap the model in a REST API (FastAPI) for real-time clinical use
- **Generalisability:** Validate on external datasets from different hospitals/regions

---

## 👤 About Me

**Sam Moses Ignatius Sathish Kumar**
MSc Data Analytics · De Montfort University, Leicester, UK

I'm a data analyst with hands-on experience in the full ML lifecycle — from messy real-world data to optimised, clinically-relevant models. This project reflects my ability to apply rigorous, scientific methodology to high-stakes domains.

📫 [LinkedIn]([https://linkedin.com/in/your-profile](https://www.linkedin.com/in/sammoseskumar/)) · [Email](mailto:da.sammoses@gmail.com)

---

## 📄 License

MIT License — see [LICENSE](LICENSE) for details.

---

<div align="center">
<sub>Built with Python · Scikit-learn · XGBoost · Pandas · Jupyter</sub>
</div>
