# Data Visualization – Week 04

## Project Overview

This project is part of **Data Visualization – Week 04** and focuses on analyzing **Shopify historical stock market data** using Python.

The project explores stock price movements through **Closing Price Visualization** and **Daily Return Analysis**.

Python libraries such as **Pandas, NumPy, and Matplotlib** are used for data loading, analysis, and visualization.

---

## Objectives

The main objectives of this project are:

* Load and explore Shopify stock market data
* Understand historical stock price movements
* Visualize the closing price over time
* Calculate daily stock returns
* Analyze the distribution of daily returns
* Understand basic financial data visualization techniques

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Google Colab / Jupyter Notebook

---

## Project Structure

```text
DV-Week-04/
│
├── DV_Week_04.ipynb
├── dv_week_04.py
├── shopify_stock.csv
└── README.md
```

### File Description

| File                | Description                                                    |
| ------------------- | -------------------------------------------------------------- |
| `DV_Week_04.ipynb`  | Google Colab/Jupyter Notebook containing the complete analysis |
| `dv_week_04.py`     | Python script containing the analysis and visualizations       |
| `shopify_stock.csv` | Historical Shopify stock market dataset                        |
| `README.md`         | Project documentation                                          |

---

# Dataset

The project uses historical **Shopify stock market data**.

The dataset contains **2,469 records** and **7 columns**.

| Column      | Description                             |
| ----------- | --------------------------------------- |
| `date`      | Stock trading date                      |
| `open`      | Opening stock price                     |
| `high`      | Highest price during the trading period |
| `low`       | Lowest price during the trading period  |
| `close`     | Closing stock price                     |
| `adj_close` | Adjusted closing stock price            |
| `volume`    | Number of shares traded                 |

### Dataset Information

* **Rows:** 2,469
* **Columns:** 7
* **Missing Values:** None
* **Data Type:** Numerical stock price and volume data with date information

---

# Data Analysis

## 1. Import Libraries

The project uses Pandas, NumPy, and Matplotlib.

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```

---

## 2. Load the Dataset

The Shopify stock dataset is loaded using Pandas:

```python
df = pd.read_csv("shopify_stock.csv")
```

The dataset is then displayed for initial inspection.

---

## 3. Explore the Dataset

The first few records are displayed using:

```python
print(df.head())
```

This helps to understand the structure and values of the stock dataset.

---

# Visualizations

## 4. Closing Price Visualization

The closing price is plotted against the date to visualize the historical movement of Shopify's stock price.

```python
plt.plot(df["date"], df["close"])

plt.xlabel("Date")
plt.ylabel("Closing Price")
plt.title("Closing Price")

plt.show()
```

### Purpose

The line chart helps visualize how the stock's closing price changes over time.

It provides a simple view of historical price movements and trends.

---

# 5. Daily Return Analysis

Daily return is calculated using the percentage change in the closing price.

```python
df["Daily_Return"] = df["close"].pct_change()
```

The daily return represents the percentage change in the closing price from one trading period to the next.

---

## Daily Return Distribution

A histogram is used to visualize the distribution of daily returns.

```python
plt.hist(
    df["Daily_Return"].dropna(),
    bins=30
)

plt.xlabel("Daily Return")
plt.ylabel("Frequency")
plt.show()
```

### Purpose

The histogram helps understand:

* Distribution of daily returns
* Frequency of different return values
* General variation in daily stock returns

---

# Analysis Workflow

```text
Load Shopify Stock Dataset
          ↓
Explore Dataset
          ↓
Analyze Stock Prices
          ↓
Visualize Closing Price
          ↓
Calculate Daily Returns
          ↓
Visualize Daily Return Distribution
          ↓
Interpret Stock Data
```

---

# Concepts Covered

This project demonstrates the following Data Visualization and Data Analysis concepts:

* Data Loading
* Data Exploration
* Time-Series Data
* Stock Price Analysis
* Line Plot
* Percentage Change
* Daily Return Calculation
* Histogram
* Distribution Analysis
* Financial Data Visualization

---

# How to Run the Project

## Option 1 – Google Colab

1. Open `DV_Week_04.ipynb` in Google Colab.
2. Upload `shopify_stock.csv`.
3. Make sure the CSV filename matches the filename used in the notebook.
4. Run the notebook cells from top to bottom.

---

## Option 2 – Jupyter Notebook

Install the required libraries:

```bash
pip install pandas numpy matplotlib
```

Then open:

```text
DV_Week_04.ipynb
```

Run the cells sequentially.

---

## Option 3 – Python Script

Run the Python script using:

```bash
python dv_week_04.py
```

Make sure `shopify_stock.csv` is available in the same project directory.

---

# Project Outcome

This project provides practical experience in analyzing **time-series stock market data** using Python.

The analysis focuses on:

* Historical Shopify closing prices
* Stock price visualization
* Daily return calculation
* Daily return distribution

The project demonstrates how basic visualization techniques can be used to understand financial datasets.

---
