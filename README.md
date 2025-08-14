# Bank Loan Analysis Project

## Description

This project offers an in-depth analysis of bank loan datasets to derive critical insights into lending dynamics, risk assessment, and customer financial profiles. Utilizing Python's powerful data analysis and visualization capabilities, it aims to uncover actionable trends in loan performance, interest rate structures, and various borrower demographics. The analysis supports a data-driven approach to understanding the financial landscape and informs strategic decision-making in the banking sector.

## Features

This analysis covers several key areas, presenting findings through various visualizations and tabular data:

* **Total Funded Amount by Home Ownership:** A treemap illustrating loan distribution based on borrower home ownership.

* **Average Interest Rate by Loan Grade:** Bar charts detailing interest rates across different loan grades, reflecting risk-based pricing.

* **Bad Loan Percentage Analysis:** Visualizations showing the percentage of charged-off loans by grade, employment length, and loan purpose.

* **Correlation of Financial Variables:** A heatmap displaying relationships between `annual_income`, `loan_amount`, `int_rate`, and `dti`.

* **Distribution of Annual Income:** A histogram providing insights into borrower income levels.

* **Average Loan Amount by Home Ownership:** Bar charts showcasing average loan sizes across various home ownership categories.

## Technologies Used

* Python

* Pandas (for data manipulation)

* Matplotlib (for static visualizations)

* Seaborn (for statistical data visualization)

* Plotly Express (for interactive visualizations)

* Tabulate (for formatted table output)

## Getting Started

To set up and run this project locally, follow these steps:

1.  **Clone the repository:**

    ```bash
    git clone [https://github.com/YourGitHubUsername/bank-loan-analysis.git](https://github.com/YourGitHubUsername/bank-loan-analysis.git)
    cd bank-loan-analysis
    ```

2.  **Install the required Python packages:**

    ```bash
    pip install pandas matplotlib seaborn plotly tabulate openpyxl
    ```

    *(Note: `openpyxl` is required by Pandas to read .xlsx files.)*

3.  **Obtain the dataset:**
    Ensure you have the `financial_loan.xlsx` file in your project directory. This project assumes the data is present for the scripts to run correctly.

## Usage

After setting up the environment and placing the dataset, you can run the Python scripts to perform the analysis and generate the visualizations. Each metric is typically represented by a distinct code chunk in the provided project files.

To execute the entire analysis, you would typically run a main Python script that contains all the code snippets, or run each snippet individually in a Jupyter Notebook/IPython environment.

```python
# Example of how to run a specific analysis from your Python environment
# (assuming df is loaded from financial_loan.xlsx)

import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import plotly.express as px
from tabulate import tabulate

# Load your data (ensure financial_loan.xlsx is in the same directory)
df = pd.read_excel("financial_loan.xlsx")

# Example: Run the "Bad Loan Percentage by Loan Grade" analysis
total_loans_by_grade = df.groupby('grade')['id'].count()
bad_loans = df[df['loan_status'].isin(['Charged Off'])]
bad_loans_by_grade = bad_loans.groupby('grade')['id'].count()
bad_loan_percentage_by_grade = (bad_loans_by_grade / total_loans_by_grade) * 100

plt.figure(figsize=(10, 6))
bad_loan_percentage_by_grade.plot(kind='bar', color='#e9b7d8')
plt.title('Bad Loan Percentage by Loan Grade')
plt.xlabel('Loan Grade')
plt.ylabel('Bad Loan Percentage (%)')
plt.xticks(rotation=0)
plt.grid(axis='y', linestyle='--', alpha=0.6)
plt.tight_layout()
plt.show()

print("Bad Loan Percentage by Loan Grade:")
print(tabulate(bad_loan_percentage_by_grade.to_frame(), headers='keys', tablefmt='psql'))
