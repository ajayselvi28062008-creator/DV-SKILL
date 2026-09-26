# Data Visualization – Week 02

## Project Overview

This project is part of **Data Visualization – Week 02** and focuses on analyzing and visualizing a **Superstore Sales Dataset** using Python.

The project demonstrates different data visualization techniques to understand **Sales, Profit, Discount, Categories, and relationships between numerical variables**.

The analysis is performed using **Pandas, NumPy, Matplotlib, and Seaborn**.

---

## Objectives

The main objectives of this project are:

* Explore and understand the Superstore dataset
* Perform basic data preprocessing
* Analyze sales and profit across categories
* Create different types of visualizations
* Understand profit distribution and variation
* Analyze the relationship between discount and profit
* Identify relationships between numerical variables using correlation
* Visualize correlations using a heatmap

---

## Technologies & Libraries

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Google Colab / Jupyter Notebook

---

## Project Structure

```text
DV-Week-02/
│
├── DV_Week_02.ipynb
├── dv_week_02.py
├── samplesuperstore - samplesuperstore(1).csv
└── README.md
```

### File Description

| File                                         | Description                                                    |
| -------------------------------------------- | -------------------------------------------------------------- |
| `DV_Week_02.ipynb`                           | Complete Google Colab/Jupyter Notebook containing the analysis |
| `dv_week_02.py`                              | Python script containing the complete analysis                 |
| `samplesuperstore - samplesuperstore(1).csv` | Superstore dataset used for the analysis                       |
| `README.md`                                  | Project documentation                                          |

---

# Analysis Performed

## 1. Data Exploration

The dataset is first loaded and explored using Pandas.

```python
df.head()
df.info()
df.describe()
```

These functions are used to understand:

* Dataset structure
* Column information
* Data types
* Statistical summary
* Initial records

---

## 2. Date Processing

The `Order Date` and `Ship Date` columns are converted into datetime format.

```python
df['Order Date'] = pd.to_datetime(df['Order Date'])
df['Ship Date'] = pd.to_datetime(df['Ship Date'])
```

### Delivery Days

Delivery duration is calculated using the order date and ship date.

```python
df['Delivery Days'] = (
    df['Ship Date'] - df['Order Date']
).dt.days
```

---

## 3. Category Analysis

The available product categories are identified using:

```python
df['Category'].unique()
```

Missing values are also checked:

```python
df.isnull().sum()
```

---

# Visualizations

## 4. Sales by Category

Total sales are grouped by category:

```python
category_sales = df.groupby('Category')['Sales'].sum()
```

A bar chart is then used to visualize the total sales for each category.

**Purpose:**
To compare sales performance across different product categories.

---

## 5. Profit by Category

A bar plot is created using Seaborn to compare profit across categories.

```python
sns.barplot(
    data=df,
    x="Category",
    y="Profit"
)

plt.title("Profit by Category")
plt.show()
```

**Question explored:**

> Which category generates maximum profit?

---

## 6. Sales Distribution by Category

Sales are visualized across different categories using a bar plot.

```python
sns.barplot(
    data=df,
    x="Category",
    y="Sales"
)

plt.title("Sales Distribution by Category")
plt.show()
```

This helps in comparing sales values across categories.

---

# 7. Box Plot Analysis

Box plots are used to understand:

* Data distribution
* Median value
* Outliers
* Variation

### Profit Distribution

```python
sns.boxplot(
    data=df,
    y="Profit"
)

plt.title("Profit Distribution")
plt.show()
```

This visualization helps understand the overall distribution and variation of profit values.

### Profit Variation Across Categories

```python
sns.boxplot(
    data=df,
    x="Category",
    y="Profit"
)

plt.title("Profit Variation Across Categories")
plt.show()
```

This allows profit variation to be compared between different categories.

---

# 8. Discount vs Profit Analysis

The relationship between discount and profit is analyzed using a scatter plot.

First, available discount values are checked:

```python
df["Discount"].unique()
```

Then a scatter plot is created:

```python
sns.scatterplot(
    data=df,
    x="Discount",
    y="Profit"
)

plt.title("Impact of Discount on Profit")
plt.show()
```

### Purpose

The analysis explores whether discounts are associated with changes in profitability.

**Question explored:**

> At what discount level does profit start decreasing?

---

# 9. Correlation Analysis

Correlation is used to understand the relationship between numerical variables.

Only numerical columns are selected:

```python
numeric_df = df.select_dtypes(
    include="number"
)
```

The correlation matrix is then calculated:

```python
corr = numeric_df.corr()
```

---

# 10. Correlation Heatmap

A heatmap is created to visually represent the correlation between numerical variables.

```python
sns.heatmap(
    corr,
    annot=True
)

plt.title("Correlation Heatmap")
plt.show()
```

### What the Heatmap Shows

The heatmap helps identify:

* Positive relationships
* Negative relationships
* Weak relationships
* Strong relationships between numerical variables

---

# Concepts Covered

This project covers the following Data Visualization concepts:

* Data Exploration
* Data Preprocessing
* Date Conversion
* Feature Creation
* GroupBy and Aggregation
* Bar Plot
* Box Plot
* Scatter Plot
* Correlation Matrix
* Heatmap
* Sales Analysis
* Profit Analysis
* Discount Analysis
* Outlier Analysis

---

# How to Run the Project

## Option 1 – Google Colab

1. Open `DV_Week_02.ipynb` in Google Colab.
2. Upload the CSV dataset.
3. Make sure the CSV filename matches the filename used in the code.
4. Run all cells from top to bottom.

---

## Option 2 – Jupyter Notebook

Install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn
```

Then open:

```text
DV_Week_02.ipynb
```

Run the notebook cells sequentially.

---

## Option 3 – Python Script

Run the Python file using:

```bash
python dv_week_02.py
```

Make sure the CSV dataset is available at the path specified in the Python script.

---

# Project Outcome

This project provides practical experience in using Python for data visualization and exploratory data analysis.

The Superstore dataset is analyzed through multiple visualization techniques including:

**Bar Plot → Box Plot → Scatter Plot → Correlation Heatmap**

These visualizations help understand sales, profit, discount, distribution, variation, and relationships between numerical variables.

---
