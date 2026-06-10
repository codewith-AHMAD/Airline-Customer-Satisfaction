# ✈️ Airline Passenger Satisfaction — ML Classification Project

A complete, end-to-end machine learning project that predicts whether an airline passenger will be **satisfied or dissatisfied** based on their travel experience and demographics.

---

## 📌 Project Overview

Airlines operate in a highly competitive market where **customer satisfaction directly impacts retention and business performance**. This project builds a binary classification model to predict passenger satisfaction using real-world survey data — enabling airlines like AirBlue to proactively identify dissatisfied customers and improve service quality.

**Target Variable:** `satisfaction` → `Satisfied` / `Neutral or Dissatisfied`

---

## 📂 Repository Structure

```
airline-satisfaction-ml/
│
├── 2_ml_clean_visualize.ipynb     # Phase 1: EDA, cleaning & visualization
├── Day_3_ML_prep_model.ipynb      # Phase 2: Preprocessing, modeling & evaluation
├── data/
│   └── airline_clnd.csv           # Cleaned airline dataset
└── README.md
```

---

## 🔄 Project Pipeline

### 📊 Notebook 1 — EDA & Visualization

Covers the full **data understanding** phase:

- Loaded and inspected the dataset (`data.info()`, `data.describe()`)
- Identified **310 missing values** in `Arrival_Delay_in_Minutes`
- Analyzed data types: categorical vs numerical features
- **Visualizations produced:**
  - Correlation heatmap (numerical features)
  - Gender distribution (pie chart)
  - Class distribution (bar chart)
  - Customer type distribution (pie chart)
  - Flight distance distribution (histogram)
  - Age vs Flight Distance relationship (scatter plot)
- Key findings:
  - Majority of flights cover **400–3,000 miles**; long-haul flights are rare
  - Mean passenger age is **~39 years**; younger passengers tend to travel further
  - Customers over 75 tend to take shorter flights

---

### 🤖 Notebook 2 — Data Prep & Modeling

Covers **data preparation → modeling → evaluation**:

**Preprocessing**
- Dropped rows with missing values (`dropna`)
- Removed irrelevant columns: `SR`, `id`
- Encoded 5 categorical columns using `LabelEncoder`:
  - `Gender`, `Customer_Type`, `Type_of_Travel`, `Class`, `satisfaction`
- Explored both Label Encoding and One-Hot Encoding (`pd.get_dummies`)

**Modeling**
- Split data: **80% train / 20% test** (`random_state=42`)
- Features: all columns except `satisfaction` and `Arrival_Delay_in_Minutes`
- Algorithm: **Logistic Regression** (`max_iter=10000`)

**Evaluation Metrics**
| Metric | Description |
|---|---|
| Accuracy | Overall correctness |
| Precision | Of predicted satisfied, how many actually were |
| Recall | Of actual satisfied, how many were caught |
| F1-Score | Harmonic mean of precision and recall |
| Confusion Matrix | Full breakdown of predictions |

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python | Core language |
| Pandas | Data manipulation |
| Scikit-learn | Modeling & evaluation |
| Seaborn | Statistical visualization |
| Matplotlib | General plotting |

---

## 🚀 Getting Started

```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/airline-satisfaction-ml.git
cd airline-satisfaction-ml

# Install dependencies
pip install pandas scikit-learn seaborn matplotlib notebook

# Launch Jupyter
jupyter notebook
```

Run **Notebook 1** first for EDA, then **Notebook 2** for modeling.

---

## 📈 Key Insights

- Customer satisfaction is a **binary classification** problem suited for logistic regression as a baseline
- Delay data (`Arrival_Delay_in_Minutes`) was excluded from features due to missingness
- Categorical encoding is a critical preprocessing step for ML readiness
- Loyalty status (`Customer_Type`) and travel class (`Class`) are likely strong predictors

---

## 🔮 Future Improvements

- [ ] Try ensemble models: Random Forest, XGBoost, Gradient Boosting
- [ ] Feature importance analysis to identify top satisfaction drivers
- [ ] Handle `Arrival_Delay_in_Minutes` via imputation instead of dropping
- [ ] Hyperparameter tuning with GridSearchCV
- [ ] Deploy as a simple web app (Streamlit or Flask)

---

## 👤 Author

**[Your Name]**  
Aspiring Data Scientist | ML Enthusiast  
📧 your.email@example.com  
🔗 [LinkedIn](https://linkedin.com/in/yourprofile) | [GitHub](https://github.com/yourusername)

---

*This project was developed as part of a hands-on ML learning series covering data cleaning, EDA, feature engineering, and classification modeling.*
