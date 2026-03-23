# 📊 Exploratory Data Analysis with DuckDB (Google Colab)

## 📌 Project Overview

This project demonstrates how to perform **Exploratory Data Analysis (EDA)** using **DuckDB** within a **Google Colab** environment. The workflow includes connecting to a DuckDB database, querying tables, exporting data to CSV, and visualizing insights using Python libraries.

---

## ⚙️ Technologies Used

* Python
* DuckDB
* Pandas
* Matplotlib
* Seaborn
* Google Colab
* Google Drive

---

## 📂 Project Workflow

### 1. Environment Setup

* Install required DuckDB version:

  ```bash
  pip install duckdb==0.8.1
  ```
* Mount Google Drive to access datasets.

---

### 2. Database Connection

* Connect to a DuckDB database file stored locally or in Google Drive.
* Example:

  ```python
  con = duckdb.connect(database="/content/eda_sample_data.db", read_only=True)
  ```

⚠️ **Note:** Ensure the database file exists at the specified path before connecting.

---

### 3. Data Exploration

* Query tables using SQL:

  ```sql
  SELECT * FROM eda_sample_data.store_data;
  ```
* Retrieve results and inspect data.

---

### 4. Export Data to CSV

* Extract table data and save it as CSV files in Google Drive.
* Automatically writes column headers and rows.

---

### 5. Data Analysis with Pandas

* Load query results into a Pandas DataFrame:

  ```python
  df = con.execute("SELECT * FROM eda_sample_data.order_data").fetchdf()
  ```
* Perform:

  * Data inspection (`info()`)
  * Summary statistics (`describe()`)

---

### 6. Data Visualization

* Distribution Analysis:

  * Histogram of `total_price`
* Relationship Analysis:

  * Scatter plot of `order_time` vs `total_price`

---

## 📊 Sample Insights

* Distribution of order values
* Relationship between order time and total price
* Basic statistical summaries of dataset

---

## 🚨 Common Issue

**Error: Database does not exist**

```
Catalog Error: Cannot open database "...db" in read-only mode
```

### ✅ Solution:

* Verify the correct file path:

  * Example for Google Drive:

    ```
    /content/drive/My Drive/your_folder/eda_sample_data.db
    ```
* Ensure the file is uploaded and accessible.

---

## 📁 Output

* Exported CSV files stored in:

  ```
  /content/drive/My Drive/exported_csv/
  ```

---

## 🚀 How to Run

1. Open the notebook in Google Colab
2. Mount Google Drive
3. Update the database file path if needed
4. Run all cells step-by-step

---

## 👤 Author

**[Kaung Si Thu]**
Master’s Student & Researcher

---

## 📄 License

This project is for educational and research purposes.

