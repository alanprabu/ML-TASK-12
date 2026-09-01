# Customer Churn Data Preprocessing

## 📌 Project Overview

This project focuses on **data preprocessing for customer churn analysis** using Python and popular data science libraries such as **Pandas, NumPy, Matplotlib, Seaborn, and Scikit-learn**.

The project uses the **Churn Modelling dataset**, which contains customer information such as credit score, geography, age, tenure, balance, number of products, estimated salary, and churn status.

The preprocessing work is divided into two main tasks:

1. **Data Cleaning**
2. **Feature Scaling**

---

## 📂 Dataset

The dataset used in this project is:

`Churn_Modelling1.csv`

### Dataset Information

| Attribute             | Details  |
| --------------------- | -------- |
| **Number of Records** | 10,000   |
| **Number of Columns** | 14       |
| **Target Variable**   | `Exited` |

### Features

| Column            | Description                                         |
| ----------------- | --------------------------------------------------- |
| `RowNumber`       | Row number of the customer                          |
| `CustomerId`      | Unique customer ID                                  |
| `Surname`         | Customer surname                                    |
| `CreditScore`     | Customer's credit score                             |
| `Geography`       | Customer's country                                  |
| `Gender`          | Customer gender                                     |
| `Age`             | Customer age                                        |
| `Tenure`          | Number of years the customer has been with the bank |
| `Balance`         | Customer account balance                            |
| `NumOfProducts`   | Number of bank products used                        |
| `HasCrCard`       | Indicates whether the customer has a credit card    |
| `IsActiveMember`  | Indicates whether the customer is an active member  |
| `EstimatedSalary` | Estimated customer salary                           |
| `Exited`          | Indicates whether the customer left the bank        |

---

# 🧹 1. Data Cleaning

The `Data Cleaning.ipynb` notebook performs basic data inspection and missing-value handling.

## Libraries Used

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```

## Operations Performed

### Load the Dataset

```python
df = pd.read_csv('Churn_modelling.csv')
```

The dataset is loaded using Pandas.

### Inspect the Dataset

```python
df.info()
```

This function is used to examine:

* Column names
* Data types
* Number of non-null values
* Memory usage

### Check Missing Values

```python
df.isnull().sum()
```

The dataset contains missing values in:

* `Gender` – 37 missing values
* `Age` – 34 missing values

### Remove Columns Containing Missing Values

The notebook also demonstrates:

```python
update_df = df.dropna(axis=1)
```

This removes columns that contain missing values.

### Calculate Age Statistics

The mean and median of the `Age` column are calculated:

```python
df['Age'].mean()
df['Age'].median()
```

### Fill Missing Age Values

The missing values in `Age` are replaced with the mean age:

```python
updated_df = df
updated_df['Age'] = updated_df['Age'].fillna(df['Age'].mean())
```

This ensures that the `Age` column does not contain missing values.

---

# ⚖️ 2. Feature Scaling

The `Feature_Scaling.ipynb` notebook prepares the dataset for feature scaling using Scikit-learn.

## Libraries Used

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

Scikit-learn preprocessing classes are imported:

```python
from sklearn.preprocessing import StandardScaler
from sklearn.preprocessing import MinMaxScaler
```

## Dataset Inspection

The notebook uses:

```python
df.info()
df.describe().round(2)
df.head()
```

These functions are used to:

* Inspect the dataset
* View descriptive statistics
* Display the first few records

## Selecting Features

A new DataFrame is created containing the `Age` and `Tenure` columns:

```python
new_df = pd.DataFrame(df, columns=['Age', 'Tenure'])
```

Therefore, **Age** and **Tenure** are selected as the numerical features for the scaling exercise.

> **Note:** The current notebook imports `StandardScaler` and `MinMaxScaler` and selects `Age` and `Tenure`, but the actual scaling transformation has not yet been applied.

---

# 🛠️ Technologies Used

| Technology           | Purpose                                |
| -------------------- | -------------------------------------- |
| **Python**           | Programming language                   |
| **Pandas**           | Data loading and manipulation          |
| **NumPy**            | Numerical operations                   |
| **Matplotlib**       | Data visualization                     |
| **Seaborn**          | Statistical visualization              |
| **Scikit-learn**     | Data preprocessing and feature scaling |
| **Jupyter Notebook** | Development environment                |

---

# 📁 Project Structure

```text
Customer-Churn-Preprocessing/
│
├── Churn_Modelling1.csv
├── Data Cleaning.ipynb
├── Feature_Scaling.ipynb
└── README.md
```

---

# 🔄 Data Preprocessing Workflow

```text
Churn Modelling Dataset
          ↓
     Load Dataset
          ↓
      Inspect Data
          ↓
   Check Missing Values
          ↓
      Data Cleaning
          ↓
    Select Age & Tenure
          ↓
     Feature Scaling
          ↓
   Preprocessed Data
```

---

# 🎯 Project Objectives

* Load and inspect a customer churn dataset.
* Identify missing values.
* Understand the structure and data types of the dataset.
* Handle missing values in the `Age` column.
* Explore basic statistical information.
* Select relevant numerical features.
* Understand feature scaling techniques.
* Prepare customer data for further machine-learning tasks.

---

# 📊 Dataset Quality

The provided dataset contains:

* **10,000 customer records**
* **14 columns**
* **No duplicate rows**
* **34 missing values in `Age`**
* **37 missing values in `Gender`**

The cleaning notebook specifically handles missing `Age` values by replacing them with the **mean age**.

---

# 🚀 Future Improvements

The project can be extended with the following steps:

1. Handle missing values in the `Gender` column.
2. Apply `StandardScaler` to numerical features.
3. Apply `MinMaxScaler` and compare the results.
4. Encode categorical variables such as `Geography` and `Gender`.
5. Split the dataset into training and testing sets.
6. Train a machine-learning model to predict customer churn.
7. Evaluate the model using:

   * Accuracy
   * Precision
   * Recall
   * F1-score
   * Confusion Matrix

---

# 👩‍💻 Author

**Jenos**

This project was created as a **Python and Machine Learning data preprocessing practice project**.
