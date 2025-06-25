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
```
 import pandas as pd
 import numpy as np
 import matplotlib.pyplot as plt
 import seaborn as sns
 df = pd.read_csv('Customer Churn.csv')
 df.head(3)

  df.shape   #checking the shape of the dataset



 df.isnull().sum()    #checking the null values in the dataset


## Replacing Blank Values with 0

 df["TotalCharges"]=df["TotalCharges"].replace(" ","0")
 df["TotalCharges"]=df["TotalCharges"].astype ("float")      


 df.describe() **

 df.duplicated().sum()   # checking duplicate values present in data sets

 def conv(value):
 if value == 1:
 return "Yes"
 else:
 return "No"
 df["SeniorCitizen"]=df["SeniorCitizen"].apply(conv)

 plt.figure(figsize=(4, 4))
 ax=sns.countplot(x='Churn', data=df,hue='Churn', palette=["#b20cff","#fc0707"])
 ax.bar_label(ax.containers[0])
 plt.title('Churn Distribution')
 plt.show()
```
![image](https://github.com/user-attachments/assets/efa28054-9db6-43f4-9fd1-91fc1d0e147a)

```
 plt.figure(figsize=(4, 4))
 gb=df.groupby('Churn').agg({"Churn":"count"})
 plt.pie(gb["Churn"],labels=gb.index,autopct='%1.1f%%', startangle=180,␣
 ↪colors=["#2be437","#f71212"])
 plt.title('Churn Distribution Percentage In Pie Chart')
 plt.axis('equal') # Equal aspect ratio ensures that pie chart is a circle.
 plt.show()
```

![image](https://github.com/user-attachments/assets/a5e53b3e-02de-457a-9d59-a9909ba65721)

```
 plt.figure(figsize=(5,4))
 sns. countplot(x="gender", data=df, hue="Churn", palette=["#b20cff","#fc5c00"])
 plt.title("Churn By Gender")
 plt.show()
```
![image](https://github.com/user-attachments/assets/e1f8bf4b-a068-41a3-bf20-47be7891615f)

```
plt.figure(figsize=(5,4))
 sns. countplot(x="SeniorCitizen", data=df, hue="Churn",␣
 ↪palette=["#02e5fe","#fc5c00"])
 plt.title("Churn By SeniorCitizen")
 plt.show()

```
![image](https://github.com/user-attachments/assets/647bb92f-f37b-42e8-8570-53c429f4ec6c)

```
 plt.figure(figsize=(5,4))
 sns. countplot(x="Contract", data=df, hue="Churn",␣
 ↪palette=["#02fe2c","#fc0061"])
 plt.title("Churn By Contract")
 plt.show()

```

![image](https://github.com/user-attachments/assets/0d424841-b0af-4abb-a149-56d86443a947)

```
 plt.figure(figsize = (9,4))
 sns.histplot(x = "tenure", data = df, bins = 72, hue = "Churn")
 plt.show()
```
![image](https://github.com/user-attachments/assets/88184c51-2ed1-49e6-b000-aefa7cc62942)


```
 columns = ['PhoneService', 'MultipleLines', 'InternetService', 'OnlineSecurity',
 'OnlineBackup', 'DeviceProtection', 'TechSupport', 'StreamingTV',␣
 ↪'StreamingMovies']
 # Number of columns for the subplot grid (you can change this)
 n_cols = 3
 n_rows = (len(columns) + n_cols- 1) // n_cols # Calculate number of rows␣
 ↪needed
 # Create subplots
 fig, axes = plt.subplots(n_rows, n_cols, figsize=(12, n_rows * 3)) # Adjust␣
 ↪figsize as needed
 # Flatten the axes array for easy iteration (handles both 1D and 2D arrays)
 axes = axes.flatten()
 # Iterate over columns and plot count plots
 for i, col in enumerate(columns):
 sns.countplot(x=col, data=df, ax=axes[i], hue = df["Churn"])
 axes[i].set_title(f'Count Plot of {col}')
 axes[i].set_xlabel(col)
 axes[i].set_ylabel('Count')
 # Remove empty subplots (if any)
 for j in range(i + 1, len(axes)):
 fig.delaxes(axes[j])
 plt.tight_layout()
 plt.show()
```

![image](https://github.com/user-attachments/assets/72b5d602-4bce-4f83-8c4c-48deb94439f9)

**The majority of customers who do not churn tend to have services like PhoneService, InternetSer
vice (particularly DSL), and OnlineSecurity enabled. For services like OnlineBackup, TechSupport,
 and StreamingTV, churn rates are noticeably higher when these services are not used or are un
available.**
 
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
