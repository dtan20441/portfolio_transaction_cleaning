# Cleaning dirty financial transaction data using Python
## Overview
This portfolio the cleaning of dirty financial transaction data from a dummy company where each row represents a transaction made by the company using Python.     
The original dataset can be downloaded [here](https://github.com/dtan20441/portfolio_transaction_cleaning/blob/main/dirty_financial_transactions.csv).    
The cleaned dataset can be downloaded [here](https://github.com/dtan20441/portfolio_transaction_cleaning/blob/main/cleaned_financial_transactions.csv).    
The jupyter notebook containing all the code can be viewed [here](https://github.com/dtan20441/portfolio_transaction_cleaning/blob/main/Financial%20cleaning.ipynb).    

Here is a snapshot of the original dataset: ![dirty dataset snapshot](https://github.com/dtan20441/portfolio_transaction_cleaning/blob/main/Screenshots/dirty_financial_transaction_snapshot.png).  
Here is a snapshot after it has been cleaned: ![cleaned dataset snapshot](https://github.com/dtan20441/portfolio_transaction_cleaning/blob/main/Screenshots/clean_financial_data.png).  

## Data structure and issues
The dataset consists of 1 table with 100,000 rows.
![Image of dataset](https://github.com/dtan20441/portfolio_transaction_cleaning/blob/main/Screenshots/dirty_financial_transactions_data.png).

The data quality issues present in the dataset:
1. Transaction_ID has values missing.
2. Transaction_Date has invalid dates and missing values.
3. Product_Name have misspelt names, extra spaces and missing values.
4. Quantity contain negative values, missing values and outlier quantities.
5. Price contain negative values, missing values and symbols.
6. Payment_Method has misspelt values.
7. Transaction_Status has missing and misspelt values.

## Reasoning behind cleaning decisions
1. Transaction_ID in the original dataset is in ascending order. Thus, the missing values was filled based on that order.
2. Transaction_Date had invalid dates like 30th of February that have now been replaced with NaT.
3. Standardised Product_Name.
4. Assumed that negative values in Quantity were meant to be positive. Some Quantity values were extremely high, therefore, those above the third quartile were removed.
5. Assumed negative Price values were meant to be positive, rounded to 2 decimal places because its currency, and since the column is named Price, symbols such as '$' were deemed unnecessary.
6. Standardised Payment_Method.
7. Standardised Transaction_Status.

## Limitations
- Difficult to determine what to do with missing values without context from other departments, e.g. price for products at the time of purchase.
- Outliers in Quantity were removed based on statistics but they could have been rare and valid.
- Negative values were assumed to be positive because of data entry errors and, Price and Quantity are presumably positive. However, without business context, these negatives could have represented valid scenarios.
