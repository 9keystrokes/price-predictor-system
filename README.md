
# 🏠 House Price Prediction – End-to-End ML Pipeline with MLOps

This project is a complete, production-ready machine learning pipeline for house price prediction. It focuses on applying **best practices in MLOps**, using **clean, modular code architecture**, and implementing software engineering concepts like **design patterns**. The goal is to go beyond the typical "fit and predict" approach and build something scalable, reproducible, and production-friendly.

---

## 🚀 Tech Stack

### 👨‍💻 Languages & Libraries
- **Python** (primary language)
- **Pandas**, **NumPy** – Data handling and manipulation
- **Seaborn**, **Matplotlib** – Data visualization
- **Scikit-learn** – ML modeling and preprocessing
- **Statsmodels** – Statistical tests and model assumptions

### ⚙️ MLOps & Workflow Tools
- **ZenML** – Workflow orchestration
- **MLflow** – Experiment tracking & model registry
- **Streamlit** – Simple UI for model inference
- **Docker** – Containerization and deployment (optional)
- **Pre-commit**, **Black** – Code formatting and quality

### 🧠 Software Engineering Concepts
- **Factory Pattern** – Modular data ingestion
- **Strategy Pattern** – Flexible EDA operations
- **Template Pattern** – Structured workflows for repeated tasks

---

## 🧰 Key Features

- **Multi-format data ingestion** (e.g., CSV, ZIP) using Factory Pattern
- **Modular EDA system** with Strategy Pattern (data types, distributions, missing values)
- **Assumption testing** for algorithms (e.g., normality, linearity)
- **Single algorithm focus** (Linear Regression) to demonstrate concept depth
- **Reproducible ML pipeline** using ZenML
- **Tracked experiments** using MLflow
- **Frontend interface** with Streamlit for demo/testing
- **Clean and readable code** with comments, docstrings, and type hints

---

## 🔍 EDA & Data Insights

- Performed detailed univariate, bivariate, and multivariate analysis
- Detected skewness, outliers, and missing patterns
- Used `Julius AI` as a helper for visual EDA
- Documented key decisions to inform feature engineering and modeling

---

## 🧪 Modeling & Deployment

- Trained and evaluated a **Linear Regression** model
- Verified model assumptions (multicollinearity, distribution, residuals)
- Logged all experiments with **MLflow**
- Exposed the trained model via a **Streamlit app**
- CI-ready structure that supports future automation and extension

---

## ⚙️ How to Run

### 1. Clone the repository
```bash
git clone https://github.com/yourusername/house-price-mlops.git
cd house-price-mlops
```

### 2. Install ZenML - https://docs.zenml.io/getting-started/installation

### 3. Create a virtual env

### 4. Install dependencies
```bash
pip install -r requirements.txt
```
### 5. Run

If you are running the run_deployment.py script, you will also need to install some integrations using ZenML:

```
zenml integration install mlflow -y 
```

The project can only be executed with a ZenML stack that has an MLflow experiment tracker and model deployer as a component. Configuring a new stack with the two components are as follows:

```
zenml integration install mlflow -y
zenml experiment-tracker register mlflow_tracker --flavor=mlflow
zenml model-deployer register mlflow --flavor=mlflow
zenml stack register local-mlflow-stack -a default -o default -d mlflow -e mlflow_tracker --set
```
