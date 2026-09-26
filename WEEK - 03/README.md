# Data Visualization – Week 03

## Project Overview

This project is part of **Data Visualization – Week 03** and focuses on exploring and preprocessing **Apple Inc. (AAPL) historical stock market data** using Python.

The project demonstrates fundamental data analysis and data preprocessing techniques using **Pandas, NumPy, and Matplotlib**.

The dataset contains historical stock information including **Open, High, Low, Close prices and Trading Volume**.

---

## Objectives

The main objectives of this project are:

* Load the Apple historical stock dataset
* Explore the structure of the dataset
* Display the first few records
* Understand the dataset information and data types
* Identify and handle missing values
* Remove duplicate records
* Prepare the dataset for further analysis and visualization

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
DV-Week-03/
│
├── DV_Week_03.ipynb
├── dv_week_03.py
├── Apple_historical_data.csv
└── README.md
```

### File Description

| File                        | Description                                                    |
| --------------------------- | -------------------------------------------------------------- |
| `DV_Week_03.ipynb`          | Google Colab/Jupyter Notebook containing the complete analysis |
| `dv_week_03.py`             | Python script version of the analysis                          |
| `Apple_historical_data.csv` | Apple Inc. historical stock market dataset                     |
| `README.md`                 | Project documentation                                          |

---

# Dataset

The project uses historical stock data for **Apple Inc. (AAPL)**.

The dataset contains **11,355 records** and the following columns:

| Column   | Description                                   |
| -------- | --------------------------------------------- |
| `Date`   | Historical trading date                       |
| `Open`   | Opening stock price                           |
| `High`   | Highest stock price during the trading period |
| `Low`    | Lowest stock price during the trading period  |
| `Close`  | Closing stock price                           |
| `Volume` | Number of shares traded                       |
| `ticker` | Stock ticker symbol                           |
| `name`   | Company name                                  |

---

# Data Analysis & Preprocessing

## 1. Import Required Libraries

The project uses Pandas, NumPy, and Matplotlib.

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```

---

## 2. Load the Dataset

The Apple historical stock data is loaded using Pandas:

```python
df = pd.read_csv("Apple_historical_data.csv")
```

The complete dataset is then displayed for initial inspection.

---

## 3. View the First Records

The first few rows of the dataset are displayed using:

```python
print(df.head())
```

This helps to understand the structure and values contained in the dataset.

---

## 4. Dataset Information

The structure and data types of the dataset are checked using:

```python
print(df.info())
```

This provides information about:

* Number of records
* Column names
* Data types
* Non-null values
* Memory usage

---

## 5. Handle Missing Values

Missing values are removed from the dataset using:

```python
df = df.dropna()
```

This step helps prepare the data for further analysis.

---

## 6. Remove Duplicate Records

Duplicate rows are removed using:

```python
df = df.drop_duplicates()
```

This ensures that duplicate records do not affect future analysis.

---

# Data Preprocessing Workflow

The overall preprocessing workflow can be summarized as:

```text
Load Dataset
     ↓
Explore Dataset
     ↓
View First Records
     ↓
Check Dataset Information
     ↓
Remove Missing Values
     ↓
Remove Duplicate Records
     ↓
Clean Dataset
     ↓
Ready for Further Analysis
```

---

# Key Concepts Covered

This project demonstrates the following Data Visualization and Data Analysis concepts:

* Data Loading
* Data Exploration
* Dataset Inspection
* Missing Value Handling
* Duplicate Removal
* Data Cleaning
* Pandas DataFrame Operations
* Basic Stock Market Dataset Exploration

---

# How to Run the Project

## Option 1 – Google Colab

1. Open `DV_Week_03.ipynb` in Google Colab.
2. Upload `Apple_historical_data.csv`.
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
DV_Week_03.ipynb
```

Run each cell sequentially.

---

## Option 3 – Python Script

Run the Python script using:

```bash
python dv_week_03.py
```

Make sure the CSV dataset is available in the expected location.

---

# Project Outcome

This project provides practical experience in working with **historical stock market data** using Python.

The dataset is explored and cleaned by:

* Loading the historical Apple stock data
* Inspecting the dataset
* Checking its structure and information
* Removing missing values
* Removing duplicate records

The cleaned dataset can be used as a foundation for further **stock price analysis and data visualization**.

---
