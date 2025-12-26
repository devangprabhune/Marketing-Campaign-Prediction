# 📈 Marketing Campaign Optimization using Machine Learning

## 🔍 Problem Statement
Marketing campaigns are expensive. Sending offers to every customer blindly results in wasted budget and low ROI.

This project builds a **machine learning–driven decision system** that predicts:
> **Which customers are worth targeting in a marketing campaign**

Instead of only predicting *yes/no response*, the model estimates **expected monetary value per customer**, enabling profit-driven campaign decisions.

---

## 🎯 Business Objective
- Predict the probability of a customer responding to a marketing campaign
- Convert predictions into **Expected Value (EV)**
- Target only customers where the campaign is **profitable**

---

## 🧠 Solution Approach
This is a **supervised binary classification problem**:
- **Target Variable:** `Response` (1 = Accepted campaign, 0 = Rejected)
- **Model Used:** Logistic Regression (baseline, interpretable, scalable)
- **Evaluation:** ROC-AUC, Precision, Recall + Business Metrics

---

## 🏗️ Project Pipeline

### 1️⃣ Data Cleaning
- Removed irrelevant identifiers (e.g., `ID`, `Dt_Customer`)
- Handled missing values
- Verified data types and distributions

### 2️⃣ Feature Engineering
- Created behavioral signals:
  - `Age` from `Year_Birth`
  - `Total_Spending` across all product categories
  - `Household_Size` from children and teenagers
- These features better capture **customer purchasing behavior**

### 3️⃣ Preprocessing
- One-Hot Encoding for categorical variables
- Numerical features passed without leakage
- Used `ColumnTransformer` + `Pipeline` to ensure clean separation

### 4️⃣ Model Training
- Logistic Regression with:
  - Class imbalance handling (`class_weight='balanced'`)
  - Scaled convergence (`max_iter=1000`)
- Train/Test split with stratification

### 5️⃣ Model Evaluation
- ROC-AUC for ranking customers
- Precision/Recall to control marketing costs
- Confusion Matrix for error analysis

---

## 💰 Business Impact: Expected Value Modeling

Instead of stopping at predictions, the model calculates **Expected Value (EV)** per customer:

\[
EV = P(\text{response}) \times \text{Profit} - \text{Campaign Cost}
\]

### Assumptions:
- Campaign cost per customer: ₹500
- Profit per successful response: ₹5,000

Only customers with **positive EV** are targeted.

This converts the ML model into an **ROI-driven decision engine**.

---

## 📊 Key Outcomes
- Reduced unnecessary campaign spend
- Identified high-value customers
- Enabled budget-constrained targeting (e.g., top 20% most profitable customers)

---

## 🛠️ Tech Stack
- Python
- Pandas, NumPy
- Scikit-Learn
- Matplotlib / Seaborn
- Jupyter Notebook

---

## 🚀 How to Run
1. Open `Marketing_Campaign_ML_project.ipynb` in Google Colab
2. Upload the cleaned dataset
3. Run cells top-to-bottom
4. Review predicted probabilities and Expected Value outputs

---

## 🔮 Future Improvements
- Hyperparameter tuning
- Tree-based models (Random Forest / XGBoost)
- SHAP for explainability
- Profit-based threshold optimization
- Model deployment as an API

---

## 👨‍💻 Author
**Devang Prabhune**  
Computer Science Graduate | Aspiring ML / Data Engineer

---

## ⭐ Why This Project Matters
This project demonstrates how machine learning can:
- Move beyond accuracy metrics
- Drive **real financial decisions**
- Align data science with business strategy

If you can predict it but can’t monetize it, it doesn’t matter.
