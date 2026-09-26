# Data Visualization – Week 01

## Project Overview

This project is part of **Data Visualization – Week 01** and focuses on exploring and analyzing a **Superstore Sales Dataset** using Python.

The project demonstrates basic data analysis, data preprocessing, and visualization techniques using popular Python libraries such as **Pandas, NumPy, Matplotlib, and Seaborn**.

---

## Objectives

The main objectives of this project are:

* Load and explore the Superstore dataset
* Understand the structure and summary statistics of the data
* Convert date columns into proper datetime format
* Calculate delivery days
* Identify available product categories
* Check for missing values
* Calculate total sales by category
* Visualize sales by category
* Analyze the distribution of sales values

---

## Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **Google Colab / Jupyter Notebook**

---

## Project Structure

```text
DV-Week-01/
│
├── DV_Week_01.ipynb
├── dv_week_01.py
├── samplesuperstore - samplesuperstore.csv
└── README.md
```

### Files Description

| File                                      | Description                                                    |
| ----------------------------------------- | -------------------------------------------------------------- |
| `DV_Week_01.ipynb`                        | Jupyter/Google Colab notebook containing the complete analysis |
| `dv_week_01.py`                           | Python script version of the analysis                          |
| `samplesuperstore - samplesuperstore.csv` | Dataset used for the analysis                                  |
| `README.md`                               | Project documentation                                          |

---

## Dataset

The project uses a **Superstore Sales Dataset** containing **10,194 records and 21 columns**.

Some important columns include:

* `Order ID`
* `Order Date`
* `Ship Date`
* `Ship Mode`
* `Customer Name`
* `Segment`
* `City`
* `State/Province`
* `Region`
* `Category`
* `Sub-Category`
* `Product Name`
* `Sales`
* `Quantity`
* `Discount`
* `Profit`

---

## Data Analysis Process

### 1. Import Libraries

The project uses the following libraries:

```python
import pandas as pd
import numpy as np

import matplotlib.pyplot as plt
import seaborn as sns
```

### 2. Load the Dataset

```python
df = pd.read_csv("samplesuperstore - samplesuperstore.csv")
```

### 3. Explore the Dataset

The following functions are used to understand the dataset:

```python
df.head()
df.info()
df.describe()
```

These functions help to view the first few records, understand column data types, and obtain statistical information.

### 4. Date Conversion

The `Order Date` and `Ship Date` columns are converted into datetime format:

```python
df['Order Date'] = pd.to_datetime(df['Order Date'])
df['Ship Date'] = pd.to_datetime(df['Ship Date'])
```

### 5. Calculate Delivery Days

Delivery duration is calculated using the order date and ship date:

```python
df['Delivery Days'] = (
    df['Ship Date'] - df['Order Date']
).dt.days
```

### 6. Category Analysis

The unique product categories are identified using:

```python
df['Category'].unique()
```

### 7. Missing Value Check

Missing values are checked using:

```python
df.isnull().sum()
```

### 8. Sales by Category

Total sales for each category are calculated using:

```python
category_sales = df.groupby('Category')['Sales'].sum()
```

---

## Visualizations

### Sales by Category

A bar chart is created to compare total sales between product categories.

```python
category_sales.plot(
    kind='bar',
    figsize=(8,5)
)

plt.title("Sales by Category")
plt.ylabel("Total Sales")
plt.show()
```

### Sales Distribution

A histogram is used to visualize the distribution of sales values.

```python
plt.figure(figsize=(8,5))

sns.histplot(
    df['Sales'],
    bins=30
)

plt.title("Sales Distribution")
plt.show()
```

---

## Key Analysis Areas

This project covers the following Data Visualization concepts:

* Data loading
* Data inspection
* Data cleaning
* Date and time conversion
* Feature creation
* Group-by analysis
* Aggregation
* Bar charts
* Histograms
* Basic statistical analysis

---

## How to Run

### Option 1 – Google Colab

1. Open `DV_Week_01.ipynb` in Google Colab.
2. Upload the CSV dataset.
3. Make sure the CSV filename matches the filename used in the code.
4. Run the notebook cells from top to bottom.

### Option 2 – Jupyter Notebook

Install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn
```

Then open:

```text
DV_Week_01.ipynb
```

and run the cells.

### Option 3 – Python Script

Run the Python file using:

```bash
python dv_week_01.py
```

Make sure the CSV dataset is available in the same project folder or update the CSV file path in the code.

---

## Project Outcome

Through this project, the Superstore dataset is explored and analyzed using Python. The analysis includes data inspection, date processing, delivery-day calculation, missing-value checking, category-wise sales aggregation, and basic sales visualizations.

---

