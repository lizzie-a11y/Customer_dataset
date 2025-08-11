
# Customer Dataset (Cleaned, Analyzed & Visualized)

## 📌 Overview
This repository contains a **cleaned, analyzed, and visualized customer dataset**.  
The dataset includes demographic details, purchasing patterns, and behavioral attributes, making it suitable for exploratory data analysis (EDA), visualization, and predictive modeling.

**Dataset Shape:** 2005 rows × 11 columns  
**File Format:** CSV (`customer.csv`)  

## 📂 Columns Description
| Column Name           | Description |
|-----------------------|-------------|
| **CustomerID**        | Unique identifier for each customer |
| **Gender**            | Customer gender (Male/Female) |
| **Age**               | Customer age in years |
| **Items Purchased**   | Items bought by the customer |
| **Category**          | Product category of purchased items |
| **Purchase Amount**   | Total purchase value |
| **Shipping Type**     | Shipping method chosen (e.g., Standard, Express) |
| **Profession**        | Customer profession |
| **Subscription Status** | Whether the customer is subscribed to a service (Yes/No) |
| **Season**            | Season during which the purchase was made |
| **Country**           | Customer's country |

---

## 🛠 Data Cleaning Process (Jupyter Lab)
The dataset was cleaned in **Python** using **Pandas** inside **Jupyter Lab**.

### Steps Taken:
1. **Loaded Dataset**
   ```python
   import pandas as pd
   df = pd.read_csv("customer.csv")
````

2. **Checked for Missing Values**

   ```python
   df.isnull().sum()
   ```

   * `Profession` and `Season` had missing values.

3. **Handled Missing Values**

   * Filled missing `Profession` values with `"Unknown"`.
   * Filled missing `Season` values with `"Not Specified"`.

   ```python
   df['Profession'].fillna('Unknown', inplace=True)
   df['Season'].fillna('Not Specified', inplace=True)
   ```

4. **Removed Duplicates**

   ```python
   df.drop_duplicates(inplace=True)
   ```

5. **Data Type Verification**

   * Ensured numerical columns (`Age`, `Purchase Amount`) were integers.
   * Confirmed categorical columns were stored as `object`.

---

## 📊 Data Analysis Performed

Analysis was done using **Pandas**, **NumPy**, and **Matplotlib/Seaborn**.

1. **Basic Statistics**

   ```python
   df.describe()
   ```

   * Summary of numerical features (mean, median, etc.).

2. **Gender Distribution**

   * Counted number of male vs. female customers.

3. **Age Group Analysis**

   * Grouped customers into age brackets for insights.

4. **Top Purchased Categories**

   * Identified most popular product categories.

5. **Average Purchase Amount by Profession**

   * Compared spending behavior across professions.

6. **Shipping Type Preference**

   * Checked customer preferences for shipping methods.

---

## 📈 Data Visualization

Visualizations were created using **Matplotlib** and **Seaborn** to make insights clearer.

### Examples:

* **Gender Distribution**

  ```python
  import seaborn as sns
  sns.countplot(x='Gender', data=df)
  ```
* **Top Categories Purchased**

  ```python
  df['Category'].value_counts().head(10).plot(kind='bar')
  ```
* **Purchase Amount by Age Group**

  ```python
  sns.boxplot(x='Age', y='Purchase Amount', data=df)
  ```

---

## 📌 Key Insights

* **Majority of purchases** came from \[insert finding after analysis, e.g., "customers aged 25–34"].
* **Most popular category** was \[insert category name].
* **Average purchase amount** was higher among \[insert profession or group].
* **Preferred shipping method** was \[insert shipping type].

---

## 🚀 Tools & Libraries Used

* **Python**: Data manipulation & analysis
* **Pandas**: Data cleaning & EDA
* **NumPy**: Numerical computations
* **Matplotlib** & **Seaborn**: Data visualization
* **Jupyter Lab**: Interactive development

---

## 📄 License

This dataset is shared for educational and research purposes. Please cite this repository if used in publications.

