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

```

### **2️⃣ K-Means Clustering**

In this step, we use **K-Means** to group the assets by their return and variance values to identify similar-performing stocks.

#### 🧩 Process:
1. Loop through multiple `k` values to determine the best cluster count.
2. Use the **Elbow Method** to find the optimal `k`.
3. Visualize clusters in a scatter plot.
4. Detect and remove outliers to refine results.
5. Re-run clustering for the clean dataset.

📈 **K-Means Clustering Output:**

![K-Means Clusters](images/kmeans_clusters.png)

#### 💡 Observations:
- The portfolio is divided into **5 clusters**.
- Clusters interpretation:
  - 🔴 & 🔵 — Maximum returns at similar risk
  - 🟣 — High Sharpe ratio group
  - 🟡 & 🔴 — Minimum volatility clusters

📊 **Cluster Assignments Example:**

| Stock | Cluster |
|--------|----------|
| AMAT | 2 |
| AMZN | 2 |
| BABA | 0 |
| BIDU | 0 |
| META | 0 |
| TSLA | 0 |
| GM | 3 |
| SNAP | 1 |
| SHOP | 1 |

---

### **3️⃣ Portfolio Optimization**

After identifying clusters, we construct and optimize portfolios using different optimization strategies.

#### ⚖️ Methods Used:
1. **Maximum Sharpe Ratio** – maximize return-to-risk ratio  
2. **Minimum Volatility** – minimize overall risk  
3. **Efficient Return** – maximize return for given risk tolerance  
4. **Maximum Quadratic Utility** – balance between return and investor risk aversion  

📊 **Optimization Result Table:**

| Optimization Type | Risk (Variance) | Return | Sharpe Ratio |
|--------------------|----------------|---------|---------------|
| Max Sharpe Ratio | 62% | 6% | 0.70 |
| Min Volatility | 50% | -2.3% | -0.32 |
| Efficient Return | 72% | -25% | — |
| Max Utility | 72% | -27.76% | — |

#### 📈 Efficient Frontier Visualization:
The **Efficient Frontier** shows optimal portfolios at varying risk levels, displaying how expected return increases with risk.

![Efficient Frontier](images/efficient_frontier.png)

---

### **4️⃣ Analysis & Findings**

#### 🔹 Key Observations:
- **Baidu Inc. (BIDU)** dominates in all optimization results, indicating the best trade-off between **risk and profit**.
- **Aggressive investors** can focus on:  
  `SHOP`, `BIDU`, `BZUN`
- **Conservative investors** should prefer:  
  `GM`, `RACE`, `EA`, `SNAP`, `EBAY`, `UBER`
- **Balanced investors** seeking both return and safety can rely on:  
  `Baidu Inc.` primarily.

📊 **Cluster Risk-Return Summary:**
![Cluster Summary](images/cluster_summary.png)

---

### **5️⃣ Mathematical Formulas**

**Expected Portfolio Return:**
\[
R_p = \sum (w_i * R_i)
\]

**Portfolio Variance:**
\[
\sigma_p^2 = w^T \Sigma w
\]

**Sharpe Ratio:**
\[
S = \frac{R_p - R_f}{\sigma_p}
\]

**Quadratic Utility Function:**
\[
U = R_p - \frac{A}{2}\sigma_p^2
\]

Where:
- \( R_f \) → Risk-free rate  
- \( A \) → Risk aversion coefficient  
- \( \Sigma \) → Covariance matrix  
- \( w_i \) → Weight of each stock  

---

### **6️⃣ Conclusion**

- Each optimization method produces distinct portfolios depending on risk preference.  
- The **Efficient Frontier** provides a clear visualization of optimal investment combinations.  
- **Baidu Inc. (BIDU)** shows consistent performance across all optimization methods.
- **Diverse portfolios** still require periodic adjustments due to market volatility.  
- The project emphasizes:
  - Understanding investor goals  
  - Adapting strategies based on market data  
  - Avoiding underutilization by exploring more advanced optimization metrics  

> “Despite a well-diversified portfolio, underutilization was observed — suggesting potential improvements via deeper data features or hybrid clustering models.”

---



