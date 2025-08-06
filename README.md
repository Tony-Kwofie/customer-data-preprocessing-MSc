# 🧹 Customer Data Preprocessing Project

This project demonstrates practical data preprocessing techniques applied to a synthetic customer dataset in `.csv` format. It involves restructuring flat data into nested formats, cleaning inconsistencies, engineering new features, and preparing the data for downstream analysis and visualization.

---

## 📚 Programme Details

- **Programme of Study:** MSc Artificial Intelligence and Data Science  
- **University:** University of Hull, London Campus  
- **Course:** Introduction to Programming for Artificial Intelligence and Data Science (Course Code: 771768)  
- **Student ID:** 202502578  
- **Prepared By:** Anthony Eddei Kwofie  

---

## 📌 Project Overview

Working with data is one of the most important stages in any data science pipeline. This project focuses on:

- Cleaning inconsistent or missing data  
- Restructuring flat `.csv` files into logically nested JSON  
- Flagging suspicious credit card records  
- Creating derived metrics like **Salary-to-Commute Ratio**  
- Splitting data based on employment status  
- Visualizing relationships between features using Pandas and Seaborn  

This is a practical example of the data wrangling tasks commonly encountered in industry. The objective is to prepare raw customer data into a clean, structured format suitable for analysis and model building.

---

## 🗃️ Dataset Description

- **Source:** Synthetic data provided by course instructors  
- **Format:** CSV (`acw_user_data.csv`)  
- **Contents:**  
  - Personal details (name, age, marital status, dependents)  
  - Financial data (balance, salary)  
  - Commute details (distance to work)  
  - Credit card information (issue and expiry dates)  
  - Vehicle data (type, brand, ownership)

---

## ⚙️ Key Processing Steps

### ✅ Reading and Validating Data
- Converts `age` and `balance` columns into correct data types
- Handles missing or invalid entries gracefully

### ✅ Feature Engineering
- **Salary-Commute Metric**: Measures income per kilometer of daily commute  
  `salary_commute_ratio = salary / commute_distance`

### ✅ Error Detection
- Flags credit card entries with invalid or suspicious date ranges

### ✅ Splitting and Grouping
- Segregates customers based on employment status (`employed`, `retired`, etc.)

### ✅ Output Format
- Transforms flat CSV into nested JSON for easier querying and structure

---

## 📊 Visualizations

Using `Pandas` and `Seaborn`, the notebook generates:

- Distribution plots of **Age vs Salary**  
- Heatmaps and scatterplots of **Commute Distance vs Earnings**  
- Box plots comparing **Salary by Employment Group**

These visuals help uncover trends and patterns that may not be obvious from raw data.

---

## 🧰 Libraries & Tools Used

| Functionality         | Tools/Libraries          |
|------------------------|--------------------------|
| File Processing        | `csv`, `os`, `json`       |
| Data Handling          | `pandas`, `numpy`         |
| Date Parsing           | `datetime`                |
| Visualization          | `seaborn`, `matplotlib`   |
| Notebook Environment   | `Jupyter Notebook`        |

---

## 🏁 How to Run the Project

1. Ensure you have Python 3.8+ installed.
2. Clone the repository or download the notebook.
3. Place the CSV file (`acw_user_data.csv`) in the same folder as the notebook.
4. Open the notebook and run all cells in order.

```bash
jupyter notebook customer_data_preprocessing.ipynb
📂 Project Structure
bash
Copy
Edit
.
├── customer_data_preprocessing.ipynb   # Jupyter notebook with all processing steps
├── acw_user_data.csv                   # Raw data file (input)
├── output/
│   └── cleaned_data.json               # Nested JSON output
├── README.md                           # Project documentation
🧪 Sample Code Snippet
python
Copy
Edit
def read_csv_file(file_path):
    data = []
    try:
        with open(file_path, mode='r', encoding='utf-8') as file:
            reader = csv.DictReader(file)
            for row in reader:
                try:
                    row["age"] = int(row["age"])
                except (ValueError, KeyError):
                    row["age"] = None

                try:
                    row["balance"] = float(row["balance"])
                except (ValueError, KeyError):
                    row["balance"] = None

                data.append(row)
    except FileNotFoundError:
        print(f"Error: File '{file_path}' not found.")
    except Exception as e:
        print(f"Unexpected error while reading CSV: {e}")
    return data
📄 License
This project is submitted as part of academic coursework and is intended for educational purposes only. Redistribution for commercial use is not permitted without written permission.

✉️ Contact
Author: Anthony Eddei Kwofie
📧 202502578@hull.ac.uk
🎓 MSc Artificial Intelligence and Data Science
🏫 University of Hull – London Campus

yaml
Copy
Edit

---

### 📦 Want this as a file?

Let me know if you'd like me to export it as a downloadable `README.md` file so you can upload it directly to your GitHub repository.
