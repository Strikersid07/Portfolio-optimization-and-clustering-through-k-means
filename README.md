# 📊 Portfolio Optimization & Clustering using K-Means

## 📘 Project Overview
This project focuses on analyzing and optimizing stock portfolios using **K-Means Clustering** and **Portfolio Optimization** techniques.  
It aims to identify clusters of assets with similar risk-return characteristics and construct efficient portfolios through:

- Maximum **Sharpe Ratio**
- Minimum **Volatility**
- Maximum **Quadratic Utility**
- Maximum **Return**

The approach provides a framework for investors to make **data-driven portfolio allocation** decisions.

---

## 👥 Team Members
**Group 4 — Class 4**  
- Siddharth Sharma (20230076)  
- Xavier  
- Titouan  
- Erik  

> *Group project for “Coding and Data Science for Finance (FI505E)” — Rennes School of Business, 2023–24.*

---

## 🧠 Core Concepts
- **Portfolio Clustering** → Grouping portfolios based on performance and asset allocation similarity.  
- **Portfolio Optimization** → Selecting assets and weights to maximize return for a given risk.  
- **Efficient Frontier** → Curve showing the optimal trade-off between risk and expected return.

---

## ⚙️ Workflow

### **1️⃣ Data Preprocessing**
- Imported libraries and historical stock data.  
- Calculated:
  - Returns
  - Variance  
- Combined them into a single dataset `Ret_var` for unsupervised clustering.

```python
# Example
returns = data.pct_change().mean()
variance = data.var()
ret_var = pd.concat([returns, variance], axis=1)
