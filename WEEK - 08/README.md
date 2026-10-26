# Student Performance Data Analysis Using Python

## About the Project

This project focuses on exploring and analyzing student performance data using Python. It examines students' mathematics, reading, and writing scores to understand score patterns and compare academic performance across different demographic and educational factors.

The project uses data analysis and visualization techniques to explore the relationships between subject scores and factors such as parental education level, lunch type, and test preparation course.

## Objectives

- Understand the structure and characteristics of the dataset.
- Perform basic data exploration using Pandas.
- Analyze mathematics, reading, and writing scores.
- Compare average scores across parental education levels.
- Examine score differences based on lunch type.
- Analyze the relationship between test preparation and academic scores.
- Visualize relationships and correlations between subject scores.

## Dataset

The project uses the Students Performance dataset, which contains 1,000 student records and 8 columns.

### Dataset Features

| Column Name | Description |
|---|---|
| gender | Gender of the student |
| race/ethnicity | Race or ethnicity group |
| parental level of education | Parent's education level |
| lunch | Type of lunch received |
| test preparation course | Test preparation course status |
| math score | Mathematics examination score |
| reading score | Reading examination score |
| writing score | Writing examination score |

## Technologies and Libraries

- **Python** – Core programming language
- **Pandas** – Data loading, manipulation, and analysis
- **NumPy** – Numerical computing
- **Matplotlib** – Creating charts and graphs
- **Seaborn** – Statistical data visualization
- **Jupyter Notebook** – Interactive data analysis

## Project Workflow

### 1. Data Loading

Load the CSV dataset into a Pandas DataFrame for analysis.

### 2. Data Exploration

- Display the first and last records.
- Inspect dataset information and dimensions.
- Identify column names.
- Examine descriptive statistics.
- Explore unique values in categorical columns.

### 3. Feature Selection

Separate the subject score columns from the demographic and educational columns for easier analysis.

### 4. Data Visualization

**Grouped Bar Chart:** Compare average mathematics, reading, and writing scores by parental education level.

**Pair Plot:** Explore the distributions and relationships between mathematics, reading, and writing scores.

**Correlation Heatmap:** Examine correlations among the three subject scores.

### 5. Group-Based Analysis

Calculate average subject scores by:

- Parental level of education
- Lunch type
- Test preparation course status

## Key Analysis Areas

- Academic performance across three subjects.
- Differences in average scores across parental education categories.
- Score comparisons between lunch groups.
- Score comparisons based on test preparation course status.
- Correlations among mathematics, reading, and writing scores.

## Project Structure

```text
Student-Performance-Data-Analysis/
|
|-- student_performance_data_dv_week_08.py
|-- Student_Performance_Data_DV_Week_08.ipynb
|-- StudentsPerformance(1).csv
|-- README.md
```

## Installation and Execution

### Prerequisites

Install Python and the required libraries before running the project.

### Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### Clone the Repository

```bash
git clone <your-repository-url>
cd Student-Performance-Data-Analysis
```

### Run Using Jupyter Notebook

```bash
jupyter notebook
```

Open `Student_Performance_Data_DV_Week_08.ipynb` and execute the cells sequentially.

### Run the Python Script

Ensure the CSV file path in the script points to the dataset in your project directory.

For local execution, use:

```python
df = pd.read_csv("StudentsPerformance(1).csv")
```

Then execute:

```bash
python student_performance_data_dv_week_08.py
```

## Results and Learning Outcomes

This project demonstrates how Python can be used to explore educational datasets, summarize student scores, compare groups, and visualize relationships between numerical variables.

It also provides practical experience with Pandas DataFrames, grouped averages, correlation analysis, Matplotlib charts, and Seaborn visualizations.

## Future Enhancements

- Build an interactive dashboard using Plotly or Tableau.
- Add more detailed comparisons across student groups.
- Explore additional statistical techniques.
- Develop further insights into factors associated with academic performance.

