# Income Classification using Apache Spark

## Overview
A machine learning pipeline that predicts whether an individual's annual income exceeds $50,000 based on demographic and employment features. Built entirely using Apache Spark (PySpark) for scalable, distributed data processing.

---

## Dataset
| Property | Details |
|---|---|
| **Name** | UCI Adult Census Income Dataset |
| **Source** | UCI Machine Learning Repository (Kohavi, 1996) |
| **File** | `adult.zip` (extract before use) |
| **Records** | 32,561 |
| **Features** | 15 (mix of numerical and categorical) |
| **Target** | `income` — binary (`<=50K` or `>50K`) |

---

## Repository Structure
```
├── adult.zip          # Raw dataset
├── DS_CW-.ipynb       # Main Jupyter Notebook
└── README.md          # Project documentation
```

---

## Requirements
- Python 3.8+
- Java 8+ (required for Spark)
- Apache Spark / PySpark
- Jupyter Notebook

```bash
pip install pyspark jupyter
```

---

## How to Run

**1. Clone the repository**
```bash
git clone <your-repo-url>
cd <repo-folder>
```

**2. Extract the dataset**
```bash
unzip adult.zip
```

**3. Launch Jupyter**
```bash
jupyter notebook
```

**4.** Open `DS_CW-.ipynb` and run cells from top to bottom

---

## Pipeline
| Step | Description |
|---|---|
| Data Loading | Load CSV into Spark DataFrame with schema inference |
| Missing Values | Detect `?` placeholders, impute with column mode |
| Duplicates | Identify and remove 24 duplicate records |
| Outlier Detection | IQR method using `approxQuantile()` |
| Feature Engineering | `capital_net`, `is_high_hours`, `marital_grouped` |
| Encoding | `StringIndexer` Pipeline for categorical columns |
| EDA | Distributions, correlations, class imbalance analysis |
| Modelling | Binary classification with model comparison |
| Evaluation | F1-Score, ROC-AUC, Precision, Recall |

---

## Tech Stack
- **Apache Spark (PySpark)** — distributed data processing
- **Spark ML** — StringIndexer, Pipeline, model training
- **Jupyter Notebook** — interactive development environment
