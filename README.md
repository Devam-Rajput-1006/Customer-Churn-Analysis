# 📊 Customer Churn Prediction using Machine Learning

A complete **Machine Learning project** that predicts whether a customer is likely to churn based on customer demographics, tenure, charges, contract type, and payment method.

The project covers the complete ML workflow — from **data loading and exploratory data analysis (EDA)** to **data preprocessing, model training, evaluation, and feature importance analysis**.

---

## 🚀 Project Overview

Customer churn is a major problem for businesses because losing existing customers can directly affect revenue.

In this project, Machine Learning models are used to identify customers who are likely to leave a service.

The project compares two classification algorithms:

* Logistic Regression
* Random Forest Classifier

The models are trained using customer information such as:

* Age
* Tenure
* Monthly Charges
* Total Charges
* Contract Type
* Payment Method

### 🎯 Objective

> Build a Machine Learning model that can predict customer churn and identify the factors that contribute most to churn.

---

## 🛠️ Technologies & Libraries

| Technology                 | Purpose                        |
| -------------------------- | ------------------------------ |
| Python                     | Programming language           |
| Pandas                     | Data manipulation and analysis |
| NumPy                      | Numerical operations           |
| Matplotlib                 | Data visualization             |
| Seaborn                    | Statistical visualization      |
| Scikit-learn               | Machine Learning               |
| Jupyter Notebook / VS Code | Development environment        |
| Excel                      | Dataset format                 |

---

## 📁 Project Structure

```text
customer-churn-prediction/
│
├── customer_churn_dataset.xlsx
│
├── customer_churn_prediction.ipynb
│
├── README.md

```

---

# 📌 Dataset

The dataset contains **1,000 customer records** and **8 columns**.

### Features

| Column         | Description                       | Type        |
| -------------- | --------------------------------- | ----------- |
| CustomerID     | Unique customer identifier        | ID          |
| Age            | Customer age                      | Numerical   |
| Tenure         | Length of customer relationship   | Numerical   |
| MonthlyCharges | Monthly amount paid by customer   | Numerical   |
| ContractType   | Type of customer contract         | Categorical |
| PaymentMethod  | Customer payment method           | Categorical |
| TotalCharges   | Total amount charged              | Numerical   |
| Churn          | Whether customer left the service | Target      |

### Target Variable

```text
Churn = 0 → Customer did not churn
Churn = 1 → Customer churned
```

---

# 🔎 Exploratory Data Analysis

The project performs several EDA steps to understand the dataset.

### Data quality checks

* Dataset shape
* Column names
* Data types
* Missing values
* Duplicate records
* Statistical summary

### Visual analysis

The project analyzes:

* Churn distribution
* Churn by contract type
* Churn by payment method
* Monthly charges vs churn
* Tenure vs churn
* Correlation between numerical variables

---

# 📊 Key Findings

Some important patterns were identified during the analysis.

### Contract Type

Customers with month-to-month contracts showed substantially higher churn in this dataset compared with customers on one-year and two-year contracts.

### Monthly Charges

Monthly charges showed a positive relationship with churn, meaning customers with higher monthly charges were more likely to churn within this dataset.

### Tenure

Tenure showed a negative relationship with churn. Customers with shorter tenure were more likely to churn.

### Important Features

The Random Forest model identified the following as major predictive features:

1. Contract Type — Month-to-month
2. Monthly Charges
3. Tenure
4. Total Charges
5. Contract Type — One year
6. Contract Type — Two year
7. Age

> Feature importance indicates how useful a feature was to the trained Random Forest model. It does not by itself prove that the feature causes churn.

---

# 🤖 Machine Learning Workflow

The project follows this workflow:

```text
Dataset
   ↓
Data Cleaning
   ↓
Exploratory Data Analysis
   ↓
Feature / Target Separation
   ↓
Train-Test Split
   ↓
Data Preprocessing
   ↓
Feature Scaling
   ↓
Categorical Encoding
   ↓
Model Training
   ↓
Predictions
   ↓
Model Evaluation
   ↓
Feature Importance
```

---

# ⚙️ Data Preprocessing

### Numerical Features

The following numerical features are standardized using `StandardScaler`:

```python
Age
Tenure
MonthlyCharges
TotalCharges
```

### Categorical Features

Categorical variables are converted into numerical values using `OneHotEncoder`:

```python
ContractType
PaymentMethod
```

### CustomerID

`CustomerID` is removed before model training because it is an identifier rather than a meaningful predictive feature.

---

# 🧠 Machine Learning Models

## 1. Logistic Regression

Logistic Regression is used as a baseline classification model.

```python
LogisticRegression(
    max_iter=1000
)
```

It predicts the probability of a customer belonging to the churn class.

---

## 2. Random Forest Classifier

Random Forest is an ensemble learning algorithm that combines multiple decision trees.

```python
RandomForestClassifier(
    n_estimators=300,
    random_state=42,
    class_weight="balanced"
)
```

It was used to capture potentially non-linear relationships between customer characteristics and churn.

---

# 📈 Model Performance

The models were evaluated using the held-out test dataset.

| Model               | Accuracy | ROC-AUC |
| ------------------- | -------: | ------: |
| Logistic Regression |   ~90.0% |  ~0.964 |
| Random Forest       |   ~96.5% |  ~0.995 |

### Random Forest

The Random Forest achieved approximately:

```text
Accuracy: 96.5%
ROC-AUC: 0.995
```

The test-set confusion matrix was approximately:

```text
                 Predicted
                 No    Yes

Actual No       126     5
Actual Yes        2    67
```

### Evaluation Metrics

The project uses:

* Accuracy
* Precision
* Recall
* F1-score
* ROC-AUC
* Confusion Matrix

---

# 📌 Why Multiple Metrics?

Accuracy alone does not always provide enough information for a classification problem.

Therefore, the project also evaluates:

### Precision

How many customers predicted as churners actually churned?

### Recall

How many actual churners did the model successfully identify?

### F1-score

A balance between precision and recall.

### ROC-AUC

Measures how well the model separates churners from non-churners across classification thresholds.

---

# 📊 Feature Importance

Random Forest feature importance is extracted using:

```python
rf_model.feature_importances_
```

The importance values are then organized into a DataFrame and visualized using Seaborn.

This helps identify which variables contributed most to the model's predictions.

---

# 💻 Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/customer-churn-prediction.git
```

Move into the project directory:

```bash
cd customer-churn-prediction
```

Install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn openpyxl jupyter
```

---

# ▶️ How to Run

### Option 1 — Jupyter Notebook

Start Jupyter:

```bash
jupyter notebook
```

Open:

```text
customer_churn_prediction.ipynb
```

Run the cells from top to bottom.

### Option 2 — VS Code

1. Open the project folder in VS Code.
2. Install the Python extension.
3. Open `customer_churn_prediction.ipynb`.
4. Select your Python environment.
5. Run each cell sequentially.

---

# 📦 Requirements

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
openpyxl
jupyter
```

---

# 🎯 Project Skills Demonstrated

This project demonstrates practical knowledge of:

### Python

* Variables
* Functions
* Lists
* Data structures
* Libraries
* Basic programming concepts

### Pandas

* Reading Excel files
* DataFrame operations
* Filtering
* `groupby()`
* `value_counts()`
* `describe()`
* Correlation analysis

### NumPy

* Numerical operations
* Arrays
* Statistical calculations

### Data Visualization

* Matplotlib
* Seaborn
* Count plots
* Box plots
* Heatmaps
* Bar plots

### Machine Learning

* Feature and target separation
* Train-test split
* Data preprocessing
* Feature scaling
* One-hot encoding
* Pipelines
* Logistic Regression
* Random Forest
* Model prediction
* Classification metrics
* Confusion matrix
* ROC-AUC
* Feature importance

---

# 🧩 Challenges & Learning

During this project, I learned how to move from basic data analysis to a complete Machine Learning workflow.

Some of the key concepts learned were:

* Why categorical data needs encoding
* Why numerical features may need scaling
* Why training and testing data must be separated
* How Machine Learning models learn patterns from training data
* How to evaluate classification models
* How confusion matrices work
* How feature importance can help interpret a model

---

# 🔮 Future Improvements

Possible improvements for this project include:

* Hyperparameter tuning using `GridSearchCV` or `RandomizedSearchCV`
* Cross-validation
* Additional feature engineering
* Threshold optimization
* Model comparison with additional algorithms
* Explainability using SHAP
* Interactive dashboard using Streamlit
* Deploying the model as an API
* Testing on a larger real-world dataset
* Monitoring model performance after deployment

---

# ⚠️ Limitations

The dataset contains 1,000 records, so the reported performance should not be interpreted as guaranteed performance on real-world customer data.

Before deploying such a model in a real business environment, it should be tested on historical production data and evaluated using an appropriate validation strategy.

---

# 👨‍💻 Author

**Devam Rajput**

B.Tech Computer Science Engineering

### Areas of Interest

* Data Analytics
* Machine Learning
* Artificial Intelligence
* Python
* Data Science

---

# ⭐ Project Highlights

```text
✔ Data Cleaning
✔ Exploratory Data Analysis
✔ Data Visualization
✔ Feature Engineering / Preprocessing
✔ Categorical Encoding
✔ Feature Scaling
✔ Logistic Regression
✔ Random Forest
✔ Model Evaluation
✔ Confusion Matrix
✔ ROC-AUC
✔ Feature Importance
```

---

## 📜 License

This project is created for educational and portfolio purposes.
