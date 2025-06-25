# 📊 Customer Churn Analysis

This project focuses on analyzing customer churn trends using structured data. The goal is to understand patterns and behaviors that lead customers to discontinue a service, and present those insights through clear visualizations and data summaries.

## 🔍 Project Overview

- **Objective**: To explore the factors that influence customer churn using historical data.
- **Dataset**: Telco Customer Churn dataset.
- **Tool Used**: Jupyter Notebook
- **Language**: Python

## 🧰 Tools & Libraries Used

- **Pandas** – Data handling and manipulation
- **NumPy** – Basic array operations
- **Matplotlib / Seaborn** – Data visualization and charts

## 📌 Key Features

- Data loading and cleaning
- Exploratory data analysis (EDA)
- Feature encoding and data scaling
- Tabular and graphical representation of customer behavior
- Identification of key influencing factors like tenure, contract type, internet usage, etc.

## 📁 Project Structure
**
 import pandas as pd
 import numpy as np
 import matplotlib.pyplot as plt
 import seaborn as sns
 df = pd.read_csv('Customer Churn.csv')
 df.head(3)
**
**
  df.shape   #checking the shape of the dataset
**

**
 df.isnull().sum()    #checking the null values in the dataset
**

## Replacing Blank Values with 0
**
 df["TotalCharges"]=df["TotalCharges"].replace(" ","0")
 df["TotalCharges"]=df["TotalCharges"].astype ("float")      
**

** df.describe() **

** df.duplicated().sum()   # checking duplicate values present in data sets
** 
--

## 🚀 How to Use

1. Clone this repository:

   [git clone https://github.com/your-username/Customer-Churn-Analysis.git](https://github.com/SurajSingh-Cse/Customer-Churn-Analysis-seaborn-)
   cd Customer-Churn-Analysis

## Install required libraries:

pip install -r requirements.txt
Launch the notebook:

jupyter notebook Customer_Churn_Analysis.ipynb
##  Insights
Higher churn rates are observed among customers with month-to-month contracts.

Tenure and payment method have visible impact on customer retention.

Visual charts reveal how different service features relate to churn behavior.

## Author
**Suraj Singh**
**Data Analysis Enthusiast**
📍 Dehradun, Uttarakhand
📧 surajsinghnegi654@gmail.com


Thank you for visiting this repository! Feel free to explore and share your feedback.
