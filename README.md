# Stunting Status Prediction with Ensemble Learning  
**Based on Anthropometric Factors at Kalijambe Health Center**

## 📌 Overview
Stunting remains a major public health challenge in Indonesia, with a prevalence of **21.5% in 2023**, exceeding the national target of 14%. This repository contains the implementation and documentation of a **machine learning–based stunting classification system** using **anthropometric data** collected from the **Kalijambe Health Center**.

The study evaluates multiple traditional and ensemble machine learning models and demonstrates that **XGBoost combined with SMOTE** achieves the best predictive performance for early stunting detection.

---

## 🧠 Research Objective
The objectives of this study are:
- To analyze **key anthropometric factors** influencing stunting status
- To compare the performance of traditional ML models and **ensemble learning methods**
- To develop a **robust, accurate, and scalable stunting prediction model**
- To support **early detection and decision-making** for healthcare workers in resource-constrained settings

---

## 📄 Paper Information
**Title:**  
Stunting Status Prediction Analysis with Ensemble Learning Method Based on Anthropometric Factors at Kalijambe Health Center  

**Authors:**  
- Azizah Rahmawati K – Telkom University  
- Putu Harry Gunawan – Telkom University  
- Indwiarti – Telkom University  

---

## 📊 Dataset
- **Source:** Kalijambe Health Center  
- **Total Records:** 3,129  
- **Attributes:** 35 anthropometric and demographic features  
- **Target Variable:** Height-for-Age (TB/U) category  
- **Ethics:**  
  - Fully anonymized  
  - No personally identifiable information (PII)  
  - Used strictly for secondary analysis  

---

## ⚙️ Methodology

### 1. Exploratory Data Analysis (EDA)
- Missing value analysis
- Outlier detection using **Isolation Forest**
- Correlation analysis:
  - Pearson correlation (numerical features)
  - Cramér’s V (categorical features)

### 2. Feature Engineering
- Creation of **Age at Measurement (days)**:
- Removal of redundant features (e.g., Z-Score TB/U)
- Outlier handling (≈11.6% removed)

### 3. Preprocessing Pipeline
- Numerical imputation: **KNN Imputer (k=5)**
- Categorical imputation: **Most Frequent**
- Polynomial features (degree = 2)
- Feature scaling: **Min-Max Scaling**
- Encoding:
- One-Hot Encoding (low-cardinality)
- Ordinal Encoding (high-cardinality)

### 4. Data Balancing
- **SMOTE (Synthetic Minority Over-sampling Technique)**
- Applied **only on training data** to prevent data leakage

### 5. Model Development
Models evaluated:
- Logistic Regression
- K-Nearest Neighbors (KNN)
- Support Vector Machine (SVM)
- Random Forest
- **XGBoost**

Training configurations:
1. Base Model  
2. Base Model + SMOTE  
3. SMOTE + GridSearchCV  

### 6. Hyperparameter Tuning
- **Grid Search with 3-Fold Cross-Validation**
- Model-specific parameter grids applied consistently

---

## 📈 Evaluation Metrics
Model performance was evaluated using:
- Accuracy
- Precision (Macro)
- Recall (Macro)
- F1-Score
- Confusion Matrix

Special emphasis was placed on **minority class performance** (Short & Very Short categories).

---

## 🏆 Key Results
- **Best Model:** XGBoost + SMOTE  
- **Accuracy:** 95.9%  
- **F1-Score:** 0.855  
- **95% Confidence Interval:** 0.945 – 0.970  

### Feature Importance (XGBoost)
Top predictors:
1. Z-Score Weight-for-Age
2. Z-Score Weight-for-Height
3. Current Height
4. Weight-for-Age Category
5. Age at Measurement (days)

---

## 🚀 Practical Implications
- Enables **early stunting risk identification**
- Supports integration into **health information systems**
- Suitable for **Posyandu and primary healthcare centers**
- Leverages **routine anthropometric monitoring data**

---

## ⚠️ Limitations
- Dataset from **single health center**
- Excludes socioeconomic, dietary, and environmental factors
- Limited generalizability to other regions

---

## 🔮 Future Work
- Multi-region data collection across Indonesia
- Integration of socioeconomic and environmental variables
- Development of a **clinical decision support interface**
- Real-time alert system for high-risk children

---

## 🛠️ Technologies Used
- Python
- Scikit-learn
- XGBoost
- Imbalanced-learn (SMOTE)
- Pandas, NumPy
- Matplotlib / Seaborn

---

## 📚 References
Key references include:
- WHO Growth Standards
- Random Forest (Breiman, 2001)
- XGBoost (Chen & Guestrin, 2016)
- SMOTE (Chawla et al., 2002)

(See full reference list in the paper)

---

## 📜 License
This project is intended for **academic and research purposes**.  
Please cite the original paper if you use this work.

---

## 🙌 Acknowledgments
We thank **Kalijambe Health Center** and all healthcare workers involved in data collection and routine child growth monitoring.
