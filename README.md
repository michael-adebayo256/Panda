
# 🐍 Python & Pandas | Retail Sales Data Analysis

### 🎓 Level 3 Data Technician Bootcamp | Leep Talent

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Data%20Visualisation-blue?style=for-the-badge)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

## 📌 Project Overview

This project was completed during my **Level 3 Data Technician Bootcamp with Leep Talent**.

I used Python and the Pandas library to explore, clean, manipulate and analyse retail and sales data.

The project focused on developing practical skills in data preparation, filtering, indexing, aggregation and visualisation.

I also used Python plotting tools to present findings and identify patterns in sales performance.

---

## 🎯 Project Objectives

- 📂 Import and explore datasets using Pandas.
- 🔍 Filter and select relevant records.
- 🧹 Identify and handle missing values.
- 🔄 Sort and manipulate data.
- 📊 Group and aggregate sales information.
- 📈 Create charts to visualise sales trends.
- 💡 Extract insights to support business decisions.

---

## 🛠️ Skills & Techniques

| Python / Pandas Method | Application |
|------------------------|-------------|
| `pd.read_csv()` | Import CSV datasets |
| `head()` | Preview dataset records |
| `info()` | Inspect data types and missing values |
| `describe()` | Generate descriptive statistics |
| `.loc[]` | Select data using row and column labels |
| `.iloc[]` | Select data using integer positions |
| `groupby()` | Aggregate sales by category |
| `sort_values()` | Sort records by sales performance |
| `dropna()` | Remove missing values |
| `fillna()` | Replace missing values |
| `isnull().sum()` | Identify missing values |
| `value_counts()` | Count category frequencies |
| `plot()` | Create charts directly from Pandas |
| `matplotlib` | Customise data visualisations |

---

## 📂 Dataset Exploration

### 1️⃣ Importing and Inspecting Data

The first stage involved importing the retail sales dataset and examining its structure.

```python
import pandas as pd

df = pd.read_csv("retail_sales.csv")

print(df.head())
print(df.info())
print(df.describe())
```

**What I learned:**

- How to load a CSV file into a DataFrame.
- How to inspect rows, columns and data types.
- How to generate descriptive statistics.

📸 **Notebook Screenshot**

![Dataset Exploration](screenshots/01_dataset_exploration.png)

*Figure 1: Importing the retail sales dataset and inspecting its structure.*

---

## 🔍 Data Filtering & Slicing

### 2️⃣ Filtering Sales Records

Used conditional filtering to retrieve transactions that met specific criteria.

```python
high_sales = df[df["Total Amount"] > 500]

print(high_sales.head())
```

**What I learned:**

- How to apply conditions to a DataFrame.
- How to identify transactions above a sales threshold.
- How to extract relevant records for further analysis.

📸 **Notebook Screenshot**

![Filtering Data](screenshots/02_filtering.png)

*Figure 2: Filtering retail transactions based on sales values.*

---

### 3️⃣ Selecting Data with .loc[] and .iloc[]

Practised two methods of selecting data from a Pandas DataFrame.

```python
# Select rows and columns using labels
print(df.loc[0:5, ["Product Category", "Total Amount"]])

# Select rows and columns using positions
print(df.iloc[0:5, 0:4])
```

**What I learned:**

- `.loc[]` selects data using labels.
- `.iloc[]` selects data using integer positions.
- These methods allow specific rows and columns to be extracted.

📸 **Notebook Screenshot**

![Loc and Iloc](screenshots/03_loc_iloc.png)

*Figure 3: Selecting DataFrame records using label-based and position-based indexing.*

---

## 🧹 Data Cleaning & Preparation

### 4️⃣ Handling Missing Values

Used Pandas methods to identify and manage missing information.

```python
# Check missing values
print(df.isnull().sum())

# Remove rows with missing values
clean_df = df.dropna()

# Replace missing sales values
df["Total Amount"] = df["Total Amount"].fillna(0)
```

**What I learned:**

- How to identify incomplete records.
- How to remove missing observations.
- How to replace missing values where appropriate.
- Why data quality matters before analysis.

📸 **Notebook Screenshot**

![Data Cleaning](screenshots/04_data_cleaning.png)

*Figure 4: Identifying and handling missing values in the dataset.*

---

## 📊 Data Manipulation & Aggregation

### 5️⃣ Grouping Sales by Product Category

Used `groupby()` to summarise total sales across product categories.

```python
category_sales = (
    df.groupby("Product Category")["Total Amount"]
    .sum()
    .sort_values(ascending=False)
)

print(category_sales)
```

**What I learned:**

- How to group records by category.
- How to calculate total sales.
- How to sort results from highest to lowest.
- How to compare product performance.

📸 **Notebook Screenshot**

![GroupBy Analysis](screenshots/05_groupby.png)

*Figure 5: Aggregating and sorting sales performance by product category.*

---

## 📈 Data Visualisation

### 6️⃣ Bar Chart – Sales by Product Category

Created a bar chart to compare sales across different product categories.

```python
import matplotlib.pyplot as plt

category_sales.plot(kind="bar")

plt.title("Total Sales by Product Category")
plt.xlabel("Product Category")
plt.ylabel("Total Sales")
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()
```

**What I learned:**

- How to create bar charts using Pandas.
- How to customise charts using Matplotlib.
- How to communicate category performance visually.

📸 **Notebook Screenshot**

![Sales Bar Chart](screenshots/06_bar_chart.png)

*Figure 6: Comparing total sales across product categories.*

---

### 7️⃣ Line Chart – Monthly Sales Trends

Used a line chart to explore changes in sales over time.

```python
df["Date"] = pd.to_datetime(df["Date"])

monthly_sales = (
    df.groupby(df["Date"].dt.to_period("M"))["Total Amount"]
    .sum()
)

monthly_sales.index = monthly_sales.index.to_timestamp()

monthly_sales.plot(kind="line", marker="o")

plt.title("Monthly Retail Sales Trend")
plt.xlabel("Month")
plt.ylabel("Total Sales")
plt.tight_layout()
plt.show()
```

**What I learned:**

- How to work with date columns.
- How to group transactions by month.
- How to visualise sales trends over time.

📸 **Notebook Screenshot**

![Monthly Sales Trend](screenshots/07_line_chart.png)

*Figure 7: Visualising monthly sales performance.*

---

## 💡 Data Storytelling & Business Insights

The project demonstrated how Python and Pandas can be used to transform raw sales records into meaningful information.

My analysis followed five stages:

1. **Explore:** Understand the structure and quality of the dataset.
2. **Clean:** Identify missing values and prepare records.
3. **Manipulate:** Filter, sort and select relevant information.
4. **Analyse:** Aggregate data and calculate performance metrics.
5. **Visualise:** Present findings using charts and summaries.

These techniques provide a foundation for identifying high-performing products, comparing sales categories and examining changes in customer purchasing activity.

---

## 🎯 Learning Outcomes

Through this project, I developed practical experience in:

- ✅ Python data analysis
- ✅ Pandas DataFrames
- ✅ Data filtering and slicing
- ✅ Label-based and position-based indexing
- ✅ Data cleaning and missing-value handling
- ✅ Data aggregation using `groupby()`
- ✅ Sorting and summarising datasets
- ✅ Creating charts using Matplotlib
- ✅ Interpreting retail and sales data
- ✅ Communicating findings through visualisations

---

## 📁 Repository Structure

```text
python-pandas-retail-analysis/
│
├── README.md
│
├── data/
│   └── retail_sales.csv
│
├── notebooks/
│   └── retail_sales_analysis.ipynb
│
├── screenshots/
│   ├── 01_dataset_exploration.png
│   ├── 02_filtering.png
│   ├── 03_loc_iloc.png
│   ├── 04_data_cleaning.png
│   ├── 05_groupby.png
│   ├── 06_bar_chart.png
│   └── 07_line_chart.png
│
└── requirements.txt
```

---

## 🚀 Tools & Technologies

**Python 3** • **Pandas** • **Matplotlib** • **Jupyter Notebook** • **Data Cleaning** • **Exploratory Data Analysis**

---

## 👨‍💻 Project Information

| Detail | Information |
|--------|-------------|
| 🎓 Programme | Level 3 Data Technician Bootcamp |
| 🏫 Provider | Leep Talent |
| 🐍 Project | Python & Pandas Retail Sales Analysis |
| 💻 Language | Python |
| 📚 Libraries | Pandas, Matplotlib |
| 📊 Focus | Data Cleaning, Analysis & Visualisation |
| ✅ Status | Completed |

---

## 📝 Final Reflection

This project strengthened my understanding of how Python and Pandas can be used to explore and analyse business datasets.

I gained experience in selecting records, managing missing values, aggregating sales information and producing visualisations.

These skills provide a foundation for further development in data analytics, data engineering and machine learning.

---

⭐ *Turning raw data into meaningful business insights through Python and Pandas.*

[Link to My Panda Task 1](https://colab.research.google.com/drive/18blJsfPaHWc7usIBUpzHYM7dsh6yoZ4k#scrollTo=0e5976e6)

[Link to My Panda Task 2](https://colab.research.google.com/drive/1mOxfStfrxSanQ_O0kbAY_mbdy6SBje_8#scrollTo=UDyBu9ADwuGo)

[Link to my Panda Task 3](https://colab.research.google.com/drive/1mOxfStfrxSanQ_O0kbAY_mbdy6SBje_8#scrollTo=UDyBu9ADwuGo)

[Link to my Panda Task 4](https://colab.research.google.com/drive/1L-URXjch6rU0UKHleG1G9Cl8hMv5Ptoq)
