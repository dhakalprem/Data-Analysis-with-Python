🔎 About Data Analysis with Python

Python for Data Analysis is one of the most influential for learning practical data analysis using Python.

It focuses on:

pandas for data manipulation

NumPy for numerical computing

matplotlib for visualization

Real-world datasets and workflows

It is widely used by data analysts, data scientists, and ML engineers.

📚 What You’ll Learn

1️⃣ NumPy Fundamentals

Arrays

Vectorized operations

Broadcasting

Linear algebra basics

import numpy as np

arr = np.array([1, 2, 3])
print(arr * 2)

2️⃣ Pandas for Data Wrangling

DataFrame creation

Indexing and filtering

GroupBy operations

Merging and joining datasets

Handling missing data

import pandas as pd

df = pd.read_csv("data.csv")
df.groupby("category")["sales"].mean()

3️⃣ Data Cleaning

Handling null values

Removing duplicates

Type conversion

String operations

4️⃣ Data Visualization

Line plots

Bar charts

Histograms

Basic statistical summaries

import matplotlib.pyplot as plt

df["sales"].plot(kind="hist")

plt.show()

5️⃣ Time Series Analysis

Datetime indexing

Resampling

Rolling windows

Time-based grouping

🧠 Why This Book Is Important

Almost every ML/AI workflow begins with:

Data loading

Cleaning

Transformation

Exploration

Feature engineering

This book builds that foundation.

Without strong data analysis skills, advanced ML becomes difficult.

💻 Required Setup

python -m venv data_env

source data_env/bin/activate   # Mac/Linux

# data_env\Scripts\activate    # Windows

pip install numpy pandas matplotlib seaborn jupyter


Then run:

jupyter notebook

🎯 Who Should Read It?

Beginners entering Data Science

Analysts transitioning from Excel

ML engineers needing stronger data skills

Students in statistics or CS

📊 Data Analysis vs Machine Learning

Data Analysis	Machine Learning

Understand data	Predict outcomes

Summaries & trends	Model building

Visualization	Optimization
    
Small to medium data	Often large data





🎯 Practical Data Cleaning guide in Python (Pandas) covering:

✅ Handling null values

✅ Removing duplicates

✅ Type conversion

✅ String operations

🔹 1️⃣ Setup

import pandas as pd
import numpy as np

# Sample dataset

data = {
    "Name": ["Alice", "Bob", "Charlie", "Alice", None],
    "Age": [25, 30, None, 25, 40],
    "Salary": ["50000", "60000", "70000", "50000", "80000"],
    "City": ["New York", "Los Angeles", "Chicago", "New York", "  miami  "]
}

df = pd.DataFrame(data)

print(df)

🔹 2️⃣ Handling Null Values

🔍 Check for nulls

print(df.isnull().sum())

➤ Drop rows with null values

df_drop = df.dropna()

➤ Fill null values

Fill with mean (numeric)

df["Age"] = df["Age"].fillna(df["Age"].mean())

Fill with constant

df["Name"] = df["Name"].fillna("Unknown")

Forward fill

df["Age"] = df["Age"].fillna(method="ffill")

🔹 3️⃣ Removing Duplicates

🔍 Check duplicates

print(df.duplicated())

➤ Remove duplicates

df = df.drop_duplicates()

➤ Remove duplicates based on specific columns

df = df.drop_duplicates(subset=["Name", "Age"])

🔹 4️⃣ Type Conversion

🔍 Check data types

print(df.dtypes)

➤ Convert Salary from string to integer

df["Salary"] = df["Salary"].astype(int)

➤ Convert Age to integer

df["Age"] = df["Age"].astype(int)

➤ Convert to datetime

df["Date"] = pd.to_datetime("2024-01-01")

🔹 5️⃣ String Operations

➤ Convert to lowercase

df["City"] = df["City"].str.lower()

➤ Remove extra spaces

df["City"] = df["City"].str.strip()

➤ Replace values

df["City"] = df["City"].str.replace("miami", "Miami")

➤ Extract substring

df["First_Letter"] = df["Name"].str[0]

➤ Check if string contains word

df[df["City"].str.contains("new")]

🔹 6️⃣ Final Cleaned Data

print(df)

🚀 Real-World Cleaning Workflow

df = (
    df
    .drop_duplicates()
    .fillna({"Name": "Unknown"})
)

df["Age"] = df["Age"].fillna(df["Age"].mean())

df["Salary"] = df["Salary"].astype(int)

df["City"] = df["City"].str.strip().str.lower()


🎯 Professional Tips

✔ Always check .info()

✔ Always check .describe()

✔ Handle nulls before type conversion

✔ Clean strings before grouping

✔ Validate results after cleaning