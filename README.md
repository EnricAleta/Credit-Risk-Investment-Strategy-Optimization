# 💳 Credit Risk & Investment Strategy Optimization (Lending Club Data)


## 🎯 Project Overview

This project combines two of my core interests: **data science** and **strategic financial decision-making**. Using real-world Lending Club data, the objective was not just to predict loan defaults — but to **design an optimized, risk-adjusted investment strategy** based on those predictions.

This was not a clean academic dataset. The data was **massive (2M rows, 142 variables)** and **highly imperfect** — with missing values, high cardinality features, low-variance noise, and overlapping variable meaning. The core challenge was to **extract meaningful signals in a sea of financial noise**, just as real investment professionals must do.

---

## 💡 Business Challenge

We tackled 3 critical questions:

1. **Can we accurately predict which loans are likely to default?**
2. **Can we use these predictions to optimize lending decisions?**
3. **How can we balance return and risk to build a robust investment portfolio?**

---

## 🔍 Key Highlights

- Built a **classification model** (XGBoost) with strong precision (95%) and recall (93%) on unseen data
- Tuned decision thresholds to reflect real lending strategies: conservative vs growth-oriented
- Integrated modeling with a **Sharpe ratio analysis**, **break-even interest rate analysis**, and a **Monte Carlo simulation** to guide portfolio decisions
- Delivered a final **optimal lending strategy** across credit grades (A–G) based on both **risk** and **expected return**

---

## ⚙️ Technical Approach

### 🧹 Data Preprocessing
Real data means real mess. Preprocessing included:

- Removing low-value and highly missing features (>40% missing)
- Handling multicollinearity (correlation >98%) and low variance noise
- Imputing missing values using **median/mean**, depending on feature skew
- Encoding categorical variables:
  - Ordinal: Label Encoding
  - Nominal: One-Hot Encoding
- Normalizing numerical features (Z-Score / Min-Max)
- Converting date/percentage fields to numerical formats
- Detecting and handling outliers using **Z-Score, IQR**, and **threshold capping**
- Final feature selection using **Random Forest feature importance**, reducing from 142 → 42 top features

### ⚖️ Modeling & Evaluation

- **Models tested**: XGBoost, LightGBM, Random Forest, Logistic Regression
- **Best performer**: **XGBoost** – highest precision & recall balance
- Used precision-recall curve and threshold tuning for business alignment
- Built **2 types of models**:
  - Binary classification (0 = repaid, 1 = defaulted)
  - Probability of default (for portfolio scoring)

---

## 📊 Investment Strategy & Simulation

- Used model outputs to simulate **risk-return tradeoffs** across loan grades
- Ran a **Monte Carlo simulation** with 10,000 loans over 1,000 iterations to predict profit distribution
- Calculated **break-even interest rates** by grade
- Built a final **portfolio allocation strategy** with capital distributed by Sharpe-optimal mix

---

## 💼 Business Takeaways

- Not all high-interest loans are profitable — many E–G grade loans fail to cover risk-adjusted cost
- C–D grade loans offered the best **balance of return and default risk**
- **Model + strategy combined** produced a significantly better outcome than traditional allocation heuristics

---

## 📁 Repository Structure 
- `notebooks/` – full modeling code: preprocessing, training, evaluation (Enric Aletà Classification Jupiter Notebook - Python)
- `data/` – cleaned version of Lending Club dataset (non-confidential)
- `report/` – slides & business recommendations (Enric Aletà Classification PDF)

---

## 👨‍💼 About Me

I'm Enric Aletà, MSc Business Analytics student with a strong interest in combining **finance and machine learning**. Projects like this one reflect my drive to tackle messy, real-world problems with structure, logic, and impact.

Feel free to connect on [LinkedIn](https://www.linkedin.com/in/enricaletacumellas/) or reach out if you're interested in finance, credit modeling, or ML for strategic decisions.
