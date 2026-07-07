# Swiggy Customer Funnel, Retention & A/B Test Analysis

**Product Analyst Portfolio Project** — End-to-end analysis of customer conversion funnel, retention behavior, RFM segmentation, and statistical A/B testing using real transactional data.

---

## 📌 Project Overview

This project analyzes **1,50,281 real Swiggy orders** from **1,00,000 users** (India, 2017-2020) to understand customer conversion and retention patterns, and applies rigorous **statistical hypothesis testing** on a real mobile game A/B test dataset (Cookie Cats, 90,189 players) to derive a data-driven product recommendation.

**Why this project?** Product Analysts are expected to go beyond descriptive stats — this project demonstrates the full analytical workflow a PA uses in industry: funnel diagnosis, retention/cohort analysis, customer segmentation, and experiment analysis with statistical rigor.

---

## 🎯 Key Business Questions Answered

1. Where do users drop off in the customer journey, and how many convert into paying customers?
2. How well does Swiggy retain customers over time (cohort-based)?
3. Which customers drive the most revenue, and how should they be segmented for targeted marketing?
4. Does a mobile game's gate-placement change (A/B test) actually improve player retention?

---

## 🛠️ Tech Stack

- **Python** (Pandas, NumPy, Matplotlib, SciPy) — data cleaning, analysis, statistical testing
- **Jupyter Notebook** — exploratory analysis & documentation
- **Power BI** — interactive dashboard
- **Statistics** — Chi-Square hypothesis testing, RFM modeling, cohort analysis

---

## 📊 Datasets

| Dataset | Source | Size | Description |
|---|---|---|---|
| Swiggy Orders | [Real transactional dataset](https://github.com/kamaljangir1/Swiggy_Data_analysis_Project) | 1,50,281 rows | order_date, user_id, sales_amount, sales_qty |
| Swiggy Users | Same source | 1,00,000 rows | Demographics: age, gender, occupation, marital status |
| Cookie Cats A/B Test | [Kaggle - Mobile Games A/B Testing](https://www.kaggle.com/datasets/yufengsui/mobile-games-ab-testing) | 90,189 rows | Real A/B test data from Tactile Entertainment |

---

## 🔍 Methodology & Key Findings

### 1. Customer Conversion Funnel
Built a 4-stage customer lifecycle funnel since raw clickstream data wasn't available:

```
Total Registered Users (1,00,000)
   → Ordered ≥1 Time (77,929 | 77.9%)
      → Repeat Customers, 2+ Orders (44,472 | 44.5%)
         → Loyal Customers, Top 10% Spend (7,793 | 7.8%)
```

**Finding:** 22.1% of registered users never place a single order — the single largest drop-off point. Of those who do order, only 57.1% return for a second purchase.

### 2. Cohort Retention Analysis
Tracked monthly acquisition cohorts (Oct 2017 – 2020) to measure repeat engagement over time.

**Finding:** Average Month-1 retention across all cohorts is only ~4.4%, indicating most customers are one-time or highly infrequent purchasers — a major opportunity for re-engagement campaigns.

### 3. RFM Segmentation
Segmented customers using Recency, Frequency, and Monetary scoring into 6 actionable groups.

| Segment | % of Customers | % of Revenue |
|---|---|---|
| Champions | 22.0% | 35.2% |
| Loyal Customers | 21.3% | 25.4% |
| At Risk | 9.3% | 12.2% |
| Lost | 23.2% | 11.6% |
| Need Attention | 14.3% | 10.6% |
| New/Promising | 10.0% | 5.0% |

**Finding:** Champions + Loyal Customers (43.3% of users) generate 60.6% of total revenue — classic Pareto distribution. At-Risk customers represent the highest-value win-back opportunity.

### 4. Demographic Analysis
Cross-checked conversion and spend against age, gender, occupation, and marital status.

**Finding:** No statistically meaningful variation across any demographic cut (~77-79% conversion uniformly) — engagement is driven by behavior, not demographic profile.

### 5. A/B Test — Cookie Cats Gate Placement
Tested whether moving a game's progression gate from level 30 to level 40 affects player retention, using Chi-Square hypothesis testing.

| Metric | Gate 30 | Gate 40 | p-value | Significant? |
|---|---|---|---|---|
| Day-1 Retention | 44.82% | 44.23% | 0.076 | No |
| Day-7 Retention | 19.02% | 18.20% | **0.002** | **Yes** |

**Recommendation:** Keep the gate at level 30. Day-7 retention is significantly higher with the original gate placement (p=0.002) — moving it to level 40 measurably hurts long-term player retention, even though the short-term (Day-1) effect is statistically inconclusive.

---

## 📈 Dashboard

An interactive Power BI dashboard was built covering:
- Customer funnel visualization
- Cohort retention heatmap
- RFM segment breakdown with demographic filters
- A/B test results comparison

*(See `/Dashboards` folder for screenshots and `/Power BI` folder for the `.pbix` file)*

---

## 📁 Repository Structure

```
Swiggy-Product-Analytics/
│
├── Data/
│   ├── swiggy_orders.xlsx
│   ├── swiggy_users.xlsx
│   └── cookie_cats.csv
│
├── Notebook/
│   └── swiggy_product_analytics.ipynb
│
├── Power BI/
│   ├── Swiggy_Customer_Analysis.pbix
│   └── Power BI Data/
│       ├── powerbi_master_orders.csv
│       ├── powerbi_funnel.csv
│       ├── powerbi_cohort_retention.csv
│       ├── powerbi_rfm.csv
│       ├── powerbi_ab_test_summary.csv
│       └── powerbi_ab_test_raw.csv
│
├── Dashboards/
│   ├── overview_page.png
│   ├── retention_page.png
│   ├── rfm_segments_page.png
│   └── ab_test_page.png
│
├── Charts/
│   ├── funnel_chart.png
│   ├── cohort_heatmap.png
│   ├── rfm_segments_chart.png
│   ├── ab_test_chart.png
│   └── demographic_chart.png
│
├── README.md
├── requirements.txt
└── .gitignore
```

---

## 🚀 How to Run

```bash
git clone https://github.com/shekhu24-bit/Swiggy-Product-Analytics.git
cd Swiggy-Product-Analytics
pip install -r requirements.txt
jupyter notebook "Notebook/swiggy_product_analytics.ipynb"
```

For the Power BI dashboard, open `Power BI/Swiggy_Customer_Analysis.pbix` in Power BI Desktop.

---

## 👤 Author

**Shekhar** — MBA (Finance & Business Analytics), Maharshi Dayanand University
Product Analyst Intern @ Swasth Aahar Pvt. Ltd. (Patanjali Group) | Financial Analyst Intern @ Ziion Technology

[GitHub](https://github.com/shekhu24-bit) • [LinkedIn](#)
