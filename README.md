# 📈 Stock Market Analysis & Forecasting System (US & Vietnam)

## 📌 Overview

This project focuses on **building an end-to-end system for stock market analysis and forecasting** for both **US** and **Vietnamese** equity markets.
The system emphasizes **data engineering, financial feature extraction, performance evaluation, and decision-oriented visualization**, rather than treating forecasting as a purely black-box task.

The project is designed with an **applied finance & data science perspective**, aligning with real-world analytical workflows used in quantitative analysis and decision-support systems.

---

## 🎯 Project Objectives

* Build a **robust ETL pipeline** for stock price data
* Engineer **financially meaningful features** (returns & volatility)
* Apply **Kalman Filter** for signal smoothing and state estimation
* Evaluate forecasting performance using standard error metrics
* Design an **interactive Power BI dashboard** for market comparison and insights
* Compare behavioral characteristics of **US vs Vietnam stock markets**

---

## 🏗️ System Architecture

```
Data Sources
   ↓
ETL Pipeline
   ↓
Feature Engineering
   ↓
Kalman Smoothing (State Estimation)
   ↓
Performance Evaluation
   ↓
Power BI Dashboard
```

---

## 📊 Data Sources

* **US Market**: Yahoo Finance / Alpha Vantage
* **Vietnam Market**: Daily stock price data
* Frequency: **Daily**

Each dataset includes:

* Date
* Open
* High
* Low
* Close
* Volume

---

## 🔧 Feature Engineering

The following features are constructed to capture both **return dynamics** and **market risk**:

* **Log Return**
  [ r_t = \log(P_t) - \log(P_{t-1}) ]

* **Rolling Volatility**

  * 20-day volatility (short-term risk)
  * 60-day volatility (medium-term risk)

These features provide a balance between **stationarity**, **interpretability**, and **financial relevance**.

---

## 📉 Kalman Filter Usage

The Kalman Filter is applied using a **Local Linear Trend model** to:

* Reduce noise in price series
* Estimate latent states (trend and slope)
* Improve signal stability for downstream analysis

> ⚠️ Note: The Kalman Filter is **not used as the final forecasting model**.
> Instead, it serves as a **smoothing and analytical tool**, as linear-Gaussian assumptions may limit forecasting performance in highly volatile markets.

---

## 📐 Model Evaluation

Forecasting performance is evaluated using standard regression metrics:

* **MAE** (Mean Absolute Error)
* **RMSE** (Root Mean Squared Error)
* **MAPE** (Mean Absolute Percentage Error)

Evaluation is conducted across:

* Different markets (US vs Vietnam)
* Different volatility regimes
* Raw vs Kalman-smoothed inputs

---

## 📊 Power BI Dashboard

The Power BI dashboard provides:

* Price trends and log returns visualization
* Volatility analysis (20d vs 60d)
* Market comparison between US and Vietnam
* Performance metrics overview

The dashboard is designed for **decision support**, enabling intuitive interpretation of market risk and dynamics.

---

## 🧠 Key Insights

* US market exhibits **lower but more persistent volatility**
* Vietnam market shows **higher short-term volatility spikes**
* Kalman smoothing improves **signal interpretability**, though not always forecasting accuracy
* Volatility-based features are critical for cross-market comparison

---

## 🚀 Technologies Used

* **Python** (pandas, numpy, matplotlib)
* **Kalman Filter** (state-space modeling)
* **Power BI** (dashboard & visualization)
* **Git & GitHub** (version control)

---

## 📂 Project Structure

```
├── data/                # Raw and processed datasets
├── etl/                 # Data extraction & preprocessing scripts
├── features/            # Feature engineering modules
├── kalman/              # Kalman filter implementation
├── evaluation/          # Model evaluation metrics
├── dashboard/           # Power BI files
├── notebooks/           # Exploratory analysis
└── README.md
```

---

## 📌 Future Work

* Incorporate nonlinear models (LSTM, tree-based models)
* Extend to multi-asset portfolio analysis
* Integrate real-time data pipelines
* Add trading strategy backtesting

---

## 👤 Author

**Đăng**
Applied Data Science & Financial Analytics

---

## 📜 License

This project is for **academic and research purposes**.
Feel free to explore, fork, and adapt with proper attribution.
