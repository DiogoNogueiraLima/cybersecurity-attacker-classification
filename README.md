# Who Was the Attacker? 🔐  
_Attacker classification in cybersecurity incidents (2015–2024)_

## 📌 Context
The **Global Cybersecurity Threats (2015–2024)** dataset compiles digital incidents across various countries and industries.  
Each record describes an attack: type, target industry, financial loss, number of affected users, exploited vulnerability, defense mechanisms, and resolution time.

This project follows the **CRISP-DM** methodology to answer one central business question:

👉 **Who was the attacker?**  
*(Hacker Group, Insider, Nation-state, or Unknown)*

---

## 🛠️ Technologies Used
- **Language:** Python 3  
- **Analysis and Visualization Libraries:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `plotly`  
- **Machine Learning:** `scikit-learn` (RandomForest, ExtraTrees, HistGradientBoosting)  
- **Temporal Validation:** `TimeSeriesSplit`  
- **Hyperparameter Optimization:** `RandomizedSearchCV`, `scipy.stats`  

---

## ⚙️ Methodology (CRISP-DM)

- **Business Understanding:**  
  Definition of the business problem and metrics.  
  - Main metric: **Log Loss** (probabilities useful for investigation)  
  - Secondary metric: **F1-Macro** (class balance)  
  - Baselines: mode and empirical class distribution (priors).  

- **Data Understanding:**  
  Exploratory analysis (attack types, industries, losses, vulnerabilities).  
  Identification of **missing values**, **duplicates**, and temporal patterns.  

- **Data Preparation:**  
  - Categorical variable encoding (`OrdinalEncoder`, `LabelEncoder`)  
  - Pipeline built with `ColumnTransformer`  

- **Modeling:**  
  - Algorithms: **RandomForest**, **ExtraTrees**, **HistGradientBoosting**  
  - Optimization using `RandomizedSearchCV`  
  - Validation via **TimeSeriesSplit** (no shuffle).  

- **Evaluation:**  
  - Metrics: **Log Loss** and **F1-Macro**  
  - Confusion matrices  
  - Comparison with baselines  

- **Deployment / Next Steps:**  
  - Publish the notebook on Kaggle  
  - Extend modeling to **resolution time** and **financial cost** (multi-output regression)  
  - Monitor data drift and robustness  

---

## 📊 Initial Results
- Tree-based models achieved slight improvement over the baselines.  

---

## 🚀 Next Steps
- Predict **Incident Resolution Time** and **Financial Loss**.  
- Experiment with additional models.  
- Explore explainability techniques (SHAP, feature importance).  

---

## 🔗 Access
- [Kaggle Notebook (English)](https://www.kaggle.com/code/diogonoglima/who-attacked)  
- [Kaggle Notebook (Portuguese)](https://www.kaggle.com/code/diogonoglima/quem-atacou)  
---
