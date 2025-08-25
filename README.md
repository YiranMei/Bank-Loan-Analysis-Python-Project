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

## Usage

To set up and run this project locally, follow these steps:

1.  **Install the required Python packages:**

    ```bash
    pip install pandas matplotlib seaborn plotly tabulate openpyxl
    ```

    *(Note: `openpyxl` is required by Pandas to read .xlsx files.)*

2.  **Obtain the dataset:**
    Ensure you have the `financial_loan.xlsx` file in your project directory. This project assumes the data is present for the scripts to run correctly.

