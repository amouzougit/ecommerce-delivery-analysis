# 📦 Olist E-commerce Delivery Analysis

[![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Library-Pandas-green?logo=pandas)](https://pandas.pydata.org/)
[![Plotly](https://img.shields.io/badge/Viz-Plotly-orange?logo=plotly)](https://plotly.com/)
[![License](https://img.shields.io/badge/License-MIT-lightgrey.svg)](LICENSE)

> **End-to-end data analysis project** using the [Olist Brazilian E-commerce Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce).  
> Objective: explore delivery performance, identify factors influencing delays, and prepare a predictive modeling pipeline.

---

## 🧭 Project Overview

This project replicates a real-world **data analytics workflow** applied to e-commerce logistics.

It covers:
1. 🧹 **Data loading and cleaning** — merge 9 raw Olist CSV datasets and create a unified view.  
2. 📊 **Exploratory Data Analysis (EDA)** — compute delivery KPIs, visualize trends, and measure correlations.  
3. 🔍 **Statistical insights** — test differences between on-time vs late deliveries.  
4. 🤖 *(Next step)* Model training to predict late deliveries.  
5. 🖥️ *(Future)* Streamlit dashboard for interactive visualization.

---

## 🧱 Repository Structure

olist-delivery-risk/
│
├── data/ # raw datasets (ignored in .gitignore)
├── artifacts/ # saved parquet & models (ignored)
├── notebooks/
│ ├── 00_setup_data_load.ipynb # Load & merge all Olist datasets
│ ├── 01_cleaning_EDA.ipynb # Cleaning, EDA & correlations ✅
│ ├── 02_model_evaluation.ipynb # (Next) Predictive model
│
├── requirements.txt # Python dependencies
├── .gitignore # excludes data, artifacts, venv
└── README.md # this file


---

## ⚙️ Tech Stack

| Category | Tools |
|-----------|-------|
| **Language** | Python 3.11 |
| **Data Manipulation** | Pandas, NumPy |
| **Statistics** | SciPy |
| **Visualization** | Plotly Express, Plotly FigureFactory |
| **IDE / Notebook** | VS Code, JupyterLab |
| **Version Control** | Git + GitHub |

---

## 🧩 Data Source

> Dataset: [Olist Brazilian E-Commerce Public Dataset — Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

It contains 9 CSV files describing:
- Orders, Items, Products, Customers, Sellers
- Payments, Reviews, and Geolocation data

Total size: ~500,000 lines (2016–2018 transactions)

---

## 📊 Main KPIs Computed

| Metric | Description |
|---------|--------------|
| **Late delivery rate** | % of orders delivered after estimated date |
| **Average delivery time** | Mean days between purchase and delivery |
| **Seller handling time** | Time between order approval and shipping |
| **Transport time** | Time between carrier pickup and customer delivery |
| **Average freight value** | Average logistics cost per order |

---

## 📈 Sample Visualizations

### 🔥 Correlation heatmap
<img src="https://raw.githubusercontent.com/amouzougit/ecommerce-delivery-analysis/main/docs/corr_heatmap.png" width="600"/>

### 📆 Delivery delay trend by month
<img src="https://raw.githubusercontent.com/amouzougit/ecommerce-delivery-analysis/main/docs/delay_trend.png" width="600"/>

---

## 🧠 Key Insights (from EDA)

- The **average delay rate** is around **11–13%** of orders.  
- Longer **seller handling time** is the most correlated factor with delays (+0.58).  
- Some states (AM, RR, AC) show higher delay rates due to distance/logistics.  
- Deliveries made on **weekends or holidays** tend to have higher risk.  

---

## 🚀 Quick Start (Local Setup)

### 1️⃣ Clone the repo
```bash
git clone https://github.com/amouzougit/ecommerce-delivery-analysis.git
cd ecommerce-delivery-analysis

2️⃣ Create a virtual environment
python3 -m venv venv
source venv/bin/activate   # or venv\Scripts\activate on Windows

3️⃣ Install dependencies
pip install -r requirements.txt

4️⃣ Run the notebooks
jupyter lab

Then open:

00_setup_data_load.ipynb

01_cleaning_EDA.ipynb
