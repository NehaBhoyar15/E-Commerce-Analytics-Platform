# AI-Driven E-Commerce Analytics & Sales Forecasting Platform

> A full-stack data analytics project covering ingestion, ETL, EDA, customer segmentation, product recommendations, sales forecasting, and an interactive dashboard.

---

## Live Demo

| Interface | Link |
|-----------|------|
| Streamlit Dashboard | `streamlit run dashboard/app.py` |
| Jupyter Notebooks | `/notebooks/` |

---

## Project Overview

This project simulates a real-world e-commerce analytics platform built for a mid-size online retailer. It demonstrates end-to-end data pipeline skills across eight modules:

| Module | Description | Skills |
|--------|-------------|--------|
| 1. Data Collection | Synthetic data generation + CSV ingestion | Python, SQL |
| 2. ETL & Cleaning | Null handling, type coercion, deduplication | Pandas, SQL |
| 3. EDA | Distributions, trends, correlations | Matplotlib, Seaborn |
| 4. Customer Segmentation | RFM analysis + K-Means clustering | Scikit-learn |
| 5. Sales Dashboard | Interactive KPI dashboard | Streamlit, Power BI |
| 6. Recommendation System | Collaborative filtering (item-item) | Scikit-learn, NumPy |
| 7. Sales Forecasting | Time-series with Prophet / XGBoost | Prophet, XGBoost |
| 8. Business Report | Executive summary with insights | Markdown, PDF |

---

## Key Results

- Identified **4 customer segments** — Champions segment drives **62% of total revenue**
- Sales forecast achieves **MAPE < 8%** on 30-day holdout
- Recommendation engine achieves **Precision@10 of 0.41**
- Dashboard surfaces 6 KPIs with drill-down by category, region, and time

---

## Tech Stack

```
Python 3.10+    Pandas · NumPy · Scikit-learn · XGBoost · Prophet
SQL             MySQL / PostgreSQL (SQLite for local dev)
Visualization   Matplotlib · Seaborn · Plotly
Dashboard       Streamlit
BI              Power BI (.pbix included)
Version Control Git / GitHub
```

---

## Quickstart

```bash
# 1. Clone
git clone https://github.com/YOUR_USERNAME/ecommerce-analytics.git
cd ecommerce-analytics

# 2. Create virtual environment
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Generate synthetic data
python src/data/generate_data.py

# 5. Run ETL pipeline
python src/data/etl_pipeline.py

# 6. Launch dashboard
streamlit run dashboard/app.py
```

---

## Project Structure

```
ecommerce-analytics/
├── data/
│   ├── raw/                  # Original ingested data (CSV)
│   ├── processed/            # Cleaned, analysis-ready tables
│   └── external/             # Reference data (region codes, categories)
├── notebooks/
│   ├── 01_data_collection.ipynb
│   ├── 02_etl_cleaning.ipynb
│   ├── 03_eda.ipynb
│   ├── 04_customer_segmentation.ipynb
│   ├── 05_recommendation_system.ipynb
│   ├── 06_sales_forecasting.ipynb
│   └── 07_business_insights.ipynb
├── src/
│   ├── data/
│   │   ├── generate_data.py  # Synthetic data generator
│   │   └── etl_pipeline.py   # Full ETL pipeline
│   ├── features/
│   │   ├── rfm.py            # RFM feature engineering
│   │   └── time_features.py  # Lag, rolling, seasonality features
│   ├── models/
│   │   ├── segmentation.py   # K-Means clustering
│   │   ├── recommender.py    # Item-item collaborative filter
│   │   └── forecaster.py     # XGBoost + Prophet forecasting
│   ├── visualization/
│   │   └── plots.py          # Reusable chart functions
│   └── utils/
│       └── helpers.py        # Shared utilities
├── dashboard/
│   └── app.py                # Streamlit dashboard
├── reports/
│   ├── business_insights.md  # Executive summary
│   └── figures/              # Exported chart PNGs
├── tests/
│   └── test_pipeline.py      # Unit tests
├── docs/
│   └── data_dictionary.md    # Schema documentation
├── requirements.txt
├── .gitignore
└── README.md
```

---

## Notebooks Walkthrough

### 01 · Data Collection
Generates 50,000 synthetic orders across 500 products and 10,000 customers. Schema mirrors real Shopify/WooCommerce exports.

### 02 · ETL & Cleaning
- Removes duplicates and nulls
- Parses dates, normalises currency
- Creates `orders_clean.csv` and `customers_clean.csv`

### 03 · EDA
- Monthly revenue trends
- Top-10 products by revenue and volume
- Customer lifetime value distribution
- Correlation heatmap

### 04 · Customer Segmentation (RFM)
- Scores each customer on Recency, Frequency, Monetary value
- K-Means (k=4) produces: Champions, Loyal, At-Risk, Lost
- Segment profiles with actionable recommendations

### 05 · Recommendation System
- Item-item cosine similarity on purchase co-occurrence matrix
- Returns top-N product recommendations per customer
- Evaluated with Precision@10

### 06 · Sales Forecasting
- XGBoost with lag features (7d, 14d, 30d) and rolling means
- Facebook Prophet as baseline comparison
- Trained on 18 months, evaluated on 30-day holdout

### 07 · Business Insights
- Segment-level revenue attribution
- Forecast-based inventory recommendations
- Churn risk identification

---

## Dashboard Preview

The Streamlit app includes:
- **KPI cards**: Total revenue, AOV, orders, unique customers, return rate, churn risk %
- **Revenue trend**: Line chart with 30-day forecast overlay
- **Segment breakdown**: Pie + bar charts by RFM cluster
- **Product performance**: Top-20 by revenue, filterable by category
- **Regional map**: Revenue heatmap by shipping region

---

## Business Impact

| Insight | Value |
|---------|-------|
| Champions segment (12% of customers) | 62% of revenue |
| At-Risk segment requiring re-engagement | 1,847 customers |
| 30-day revenue forecast | $284,500 ± $12,000 |
| Top recommendation click-through (simulated) | 41% Precision@10 |

---

## Author

NEEHA BHOYAR
- LinkedIn: https://www.linkedin.com/in/neha-bhoyar-763b13413/
- Email: bhoyarneha815@gmail.com

---

## License

MIT License — free to use, fork, and adapt.
