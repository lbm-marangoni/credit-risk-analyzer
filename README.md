# 🔷 Credit Risk Analyzer

> Credit scoring model that estimates probability of default and classifies customers into risk ratings

A Python-based credit risk model that collects customer financial data, normalizes each variable, applies a weighted scoring system, and outputs a probability of default with a structured risk rating — replicating the core logic used in real credit analysis workflows.

---

## 📌 What It Does

1. **Data Collection** — Gathers key customer inputs: credit score, monthly income, total debt, payment delays, relationship length with the bank, and recent loan requests
2. **Normalization** — Converts all raw variables to a 0–1 scale for comparability
3. **Weighted Scoring** — Applies calibrated weights to each variable to produce a final composite score
4. **Default Probability** — Derives probability of default (PD) directly from the final score
5. **Rating & Action** — Classifies the customer into a credit rating (AAA → D) with a recommended course of action
6. **Report** — Generates a structured report with both raw values and normalized metrics
7. **Input Validation** — rejects invalid entries before processing: score out of range, negative income or debt, and other inconsistent inputs
8. **CSV Export** — automatically saves each result to `results.csv`, appending new entries and building a cumulative client history

---

## 💡 Why I Built This

Credit risk is one of the most fundamental problems in finance — every bank, fund, and lender needs to assess the likelihood that a borrower won't repay. This project translates that logic into code: from raw customer data to a structured rating decision, using the same principles behind institutional credit scoring models.

---

## 📊 Rating System

| Rating | P(Default) | Action |
|--------|-----------|--------|
| AAA | < 5% | Automatic approval |
| A | 5% – 15% | Simplified review |
| B | 15% – 30% | Managerial review |
| C | 30% – 50% | Conditional approval |
| D | > 50% | Recommended refusal |

---

## ⚙️ How It Works

```python
# Run the full analyzer
run_analyzer()

# Output example:
# Costumer...................... Lucas
# Final Score................... 0.7367
# P(Default).................... 26.33%
# Rating........................ B
# Action........................ Managerial review
```

**Variable weights:**

| Variable | Weight |
|---|---|
| Credit Score | 30% |
| Monthly Income | 25% |
| Debt Ratio | 20% |
| Payment Delays | 10% |
| Time with Bank | 10% |
| Recent Requests | 5% |

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

---

## 📁 Project Structure

```
📁 credit-risk-analyzer
├── README.md
├── requirements.txt
├── credit_risk_analyzer.ipynb    ← main notebook
└── results.csv                   ← auto-generated after first run
```

---

## 🚀 How to Run

1. Clone the repository
```bash
git clone https://github.com/lbm-marangoni/credit-risk-analyzer
cd credit-risk-analyzer
```

2. Install dependencies
```bash
pip install -r requirements.txt
```

3. Run the notebook `credit_risk_analyzer.ipynb` and input the customer data when prompted

---

## 🚧 Next Steps

- **Visualization** — bar chart of normalized variables per customer using Matplotlib, making the scoring breakdown visual
- **Logistic Regression** — replace the weighted score with a trained `sklearn` model, moving from rule-based to data-driven credit classification

---


*Built by [Lucas Marangoni](https://www.linkedin.com/in/lbm-marangoni) — Economics student at FAAP | Quant Finance & Portfolio Management*


