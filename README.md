# Loan Data Preprocessing with NumPy

# Overview

This project provides a Python-based preprocessing pipeline for loan data using NumPy, implemented in a Jupyter Notebook (loan_data_preprocessing.ipynb).
It takes loan-data.csv as input and outputs loan-data-preprocessed.csv as a clean, structured dataset ready for analysis or modeling.
The preprocessing pipeline treats string and numeric values separately, as well as handling data and headers independently. Throughout the process, checkpoints are created to track progress.

# Key Features
- Separate handling of:
- String data preprocessing
- Numeric data preprocessing
- Data content vs. header rows
- Checkpoint creation to monitor progress during preprocessing
- Filling missing values with worst possible outcome
 
# Text data manipulation steps:
- Issue Date - Converting Dates into Months number and 
- Loan Status - Subsituting 0 for '','Charged Off','Default','Late(31-120 days)' and 1 for 'Current', 'Fully Paid', 'In Grace Period', 'Issued'
- Term - Stripping 'months' from the data and substituting '' with 60.
- Grade and Sub Grade - As Grade is included in the subgrade column making the Grade column redundant. While in Subgrade substituing the numbers in place for variables. for example - 'A1' = 1 to 'H1' = 36. 
- Verification Status - Substituting '', 'Not Verified' - 0 and 'Source Verified', 'Verified' - 1
- URL - has same id as the loan_id column in dataset, hence deleting the URL column
- State Address - breaking the states into for region 'west', 'south', 'midwest' and 'east' and substituing corresponding 1-4 values in it.
- Converting strings and creating checkpoints

# Numeric data manipulation steps:
- Substituting temporary filler values which was placed in the beginning in the dataset to mean, minimum or maximum values of the particular column based on the values which the column contains
- Currency conversion using exchange rates files EUR-USD.csv
- Adding both converted amount and conversion rate into the dataset and header
- Rearranging the header to make the relevant fields together
- Creating CHECKPOINT

# Finalization:
- Completing the dataset
- Exporting as loan-data-preprocessed.csv

# STEPS TO RUN THE FILE
- Download loan-data.csv, loan_data_preprocessing.ipynb file and EUR-USD.csv file 
- Store them into the same folder 
- Now run the code in jupyter notebook file 
- Output and checkpoint files will be created in the same folder
