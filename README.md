# Personal_Finance_Analytics

A data analytics project analyzing 5 years of personal finance data from 3,000 users to uncover spending patterns, savings behavior, and financial health indicators.

---

## 📌 Project Overview

This project analyzes a personal finance dataset containing **3,000 user records** with **25 features** spanning **January 2019 to November 2023**. The goal is to understand why most users fail to meet their savings goals and to build tools that identify financially at-risk individuals.

**Central Question:**
> *Why do most people fail to meet their savings goals — and what can be done about it?*

---

## 🎯 Objectives

1. Analyze income, expenses, and savings trends over time
2. Identify spending categories and behavioral patterns
3. Segment users into financial personas
4. Build a 0–100 financial health scoring system
5. Flag high-risk users for early intervention

---

## 📂 Dataset

| Attribute | Details |
|-----------|---------|
| Records | 3,000 users |
| Features | 25 columns |
| Time Period | January 2019 – November 2023 |
| File | `personal_finance_tracker_dataset.csv` |

**Key Columns:**
- `monthly_income`, `monthly_expense_total`, `actual_savings`, `savings_rate`
- `essential_spending`, `discretionary_spending`, `rent_or_mortgage`
- `debt_to_income_ratio`, `credit_score`, `emergency_fund`
- `financial_scenario`, `cash_flow_status`, `financial_stress_level`
- `fraud_flag`, `savings_goal_met`, `budget_goal`

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Python 3** | Core programming language |
| **Pandas** | Data loading, cleaning, manipulation |
| **NumPy** | Numerical computations |
| **Matplotlib** | Static visualizations |
| **Seaborn** | Statistical charts and heatmaps |
| **Jupyter Notebook** | Interactive analysis environment |

---

## 🔄 Project Workflow

```
Raw CSV → Data Cleaning → Feature Engineering → Exploratory Analysis 
        → Correlation Analysis → Segmentation → Scoring → Insights
```

### Step 1: Data Cleaning
- Converted `date` column from string to datetime
- Transformed `financial_advice_score` from object to numeric
- Converted `fraud_flag` and `savings_goal_met` to boolean
- Cast categorical columns to `category` dtype
- **Result:** 0 nulls, 0 duplicates, 25% memory reduction

### Step 2: Feature Engineering
Created new features:
- **Time-based:** `year`, `month`, `month_name`, `year_month`
- **Ratio-based:** `needs_ratio`, `wants_ratio`, `savings_ratio`
- **Derived metrics:** `persona`, `health_score`

### Step 3: Exploratory Data Analysis
- Income, expense, and savings distributions
- Yearly trends (2019–2023)
- Category-wise spending analysis
- 50/30/20 budget rule comparison

### Step 4: Correlation Analysis
- Measured relationships between savings rate and other factors
- Confirmed weak correlation between income and savings success

### Step 5: User Segmentation
Classified users into 5 personas based on financial behavior.

### Step 6: Financial Health Scoring
Built a custom 0–100 score combining savings rate, DTI, cash flow, goal achievement, and emergency fund.

---

## 📊 Key Findings

### Finding 1: Most Users Fail at Saving
- Only **9.2%** of users meet their savings goals
- **90.8%** miss them — a major financial literacy gap

### Finding 2: Income Isn't the Problem — Spending Is
- Correlation between income and savings rate: **+0.010** (negligible)
- Correlation between debt-to-income ratio and savings rate: **-0.037**
- Correlation between discretionary spending and savings rate: **-0.034**
- **Conclusion:** Expense control matters more than earning more

### Finding 3: Overspending on Essentials
| Category | Actual | Ideal | Gap |
|----------|--------|-------|-----|
| Needs | 59.8% | 50% | +9.8% |
| Wants | 13.5% | 30% | -16.5% |
| Savings | 25.7% | 20% | +5.7% |

Users underspend on wants because essential costs consume nearly 60% of income — indicating structural income constraints, not poor discipline.

### Finding 4: User Personas

| Persona | Count | % | Savings Rate | Profile |
|---------|-------|---|--------------|---------|
| Balanced | 1,235 | 41.2% | 0.20 | Stable, moderate |
| Debt-Burdened | 664 | 22.1% | 0.20 | High DTI ratio |
| Smart Saver | 530 | 17.7% | 0.35 | Excellent saver |
| At Risk | 400 | 13.3% | 0.24 | Negative cash flow |
| Overspender | 171 | 5.7% | 0.10 | Expense > Income |

### Finding 5: Financial Health Score

**Scoring Criteria:**
- Savings rate > 20% → +30 points
- Debt-to-income < 0.3 → +25 points
- Positive cash flow → +20 points
- Savings goal met → +15 points
- Emergency fund > $1,000 → +10 points

**Results:**
- Average score: **52.9 / 100**
- Poor health (<40): **592 users (19.7%)**
- Good health (>70): **440 users (14.7%)**

### Finding 6: High-Risk Users
- Criteria: Savings < 10% + DTI > 40% + Negative cash flow
- **37 users (1.2%)** flagged as high-risk — need urgent intervention

---

## 📁 Repository Structure

```
personal-finance-analytics/
│
├── personal_finance.ipynb              # Main analysis notebook
├── personal_finance_tracker_dataset.csv # Raw dataset
├── cleaned_personal_finance.csv        # Cleaned data (exported)
├── images/                             # Charts and visualizations
│   ├── income_expense_savings_trend.png
│   ├── correlation_heatmap.png
│   ├── persona_distribution.png
│   └── budget_rule_comparison.png
├── README.md                           # Project documentation
└── requirements.txt                    # Python dependencies
```

---

## 🚀 How to Run

### 1. Clone the repository
```bash
git clone https://github.com/your-username/personal-finance-analytics.git
cd personal-finance-analytics
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Open the notebook
```bash
jupyter notebook personal_finance.ipynb
```

### 4. Run all cells
The notebook will load the dataset, perform cleaning, generate visualizations, and export the cleaned CSV.

---

## 📦 Requirements

```
pandas
numpy
matplotlib
seaborn
jupyter
```

---

## 📈 Visualizations Included

1. **Income, Expense & Savings Distribution** — histograms with KDE
2. **Essential vs Discretionary Spending** — pie chart
3. **Category-wise Spending Analysis** — bar charts
4. **Savings Rate by Category** — horizontal bar chart
5. **50/30/20 Rule Comparison** — grouped bar chart
6. **Yearly Trends (2019–2023)** — line charts
7. **Goal-Met vs Goal-Missed Profile** — comparison bars
8. **Correlation Heatmap** — financial factors matrix
9. **User Persona Distribution** — pie chart + horizontal bars
10. **Health Score Distribution** — histogram + boxplot

---

## 💡 Key Insights Summary

1. **90.8% miss savings goals** — massive financial literacy gap
2. **Income barely correlates with savings success** (+0.01) — expense control is the real driver
3. **Users overspend on essentials** (59.8% vs 50% ideal)
4. **5.7% are overspenders** — spending more than they earn
5. **1.2% are high-risk** — 37 users need urgent financial counseling
6. **Average health score is 52.9/100** — mediocre financial well-being

---

## ⚠️ Limitations

- Dataset appears to be synthetically generated, not real user data
- 5-year time span limits long-term trend analysis
- No demographic data (age, location, family size, occupation)
- Correlation does not imply causation
- Financial health score is a custom model, not externally validated
- Persona thresholds are heuristic, not industry-standard

---

## 🔮 Future Scope

- Real-time dashboard integration
- Predictive modeling for early risk detection
- Mobile app for personal finance tracking
- Banking API integration for automatic data ingestion
- Demographic enrichment for deeper segmentation
- Machine learning models for savings prediction

---

## 🤝 Contributing

Contributions, suggestions, and feedback are welcome. Feel free to open an issue or submit a pull request.

---

## 📜 License

This project is created for academic and educational purposes. Feel free to use and adapt it with attribution.

---

## 🙏 Acknowledgments

- Dataset source: Personal Finance Tracker Dataset
- Inspired by real-world financial advisory use cases
- Built using open-source Python data science libraries

---

⭐ **If you found this project useful, please consider giving it a star!**
