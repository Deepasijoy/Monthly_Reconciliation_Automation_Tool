# Monthly_Reconciliation_Automation_Tool
Project Overview

The Monthly Reconciliation Automation Tool is designed to automate the reconciliation process between ERP transaction records and bank statement data. The project reduces manual effort, improves accuracy, and provides actionable exception reporting for finance teams.

Business Problem

Finance teams often spend significant time manually comparing ERP transactions with bank credits to identify:

Missing bank entries
Amount mismatches
Successfully reconciled transactions

Manual reconciliation is time-consuming, prone to errors, and difficult to scale for large transaction volumes.

Solution
This project automates the reconciliation process using Python and Excel, generating:

Reconciled Transactions Report
Exception vs Action Required Report

The solution compares ERP transaction amounts against bank credits using a common transaction reference number.
Dataset:
The dataset used in this project is a mock dataset created to simulate a real-world ERP-to-Bank reconciliation process.

The sample data includes:
- ERP transaction records
- Bank credit transactions
- Matching transaction reference numbers
- Intentional exceptions such as missing entries and amount mismatches

The dataset was designed for educational and portfolio purposes and does not contain any confidential financial information.

The project uses two worksheets from an Excel Macro-Enabled Workbook (.xlsm):

ERP_Data

Contains:

Reference_No
Transaction Amount
ERP transaction details
Bank_Data

Bank_Data

Contains:

Reference_No
Credit Amount
Bank transaction details
Workflow
Step 1: Load Data
Read ERP data from Excel
Read Bank data from Excel
Step 2: Merge Records
Perform a left join using Reference_No
Retain all ERP transactions
Step 3: Reconciliation Logic

The tool evaluates each transaction and assigns remarks:

Scenario	Result
Matching Amount	Transaction Reconciled Successfully
No Bank Entry Found	No Matching Entry Found in Bank
Amount Difference	Amount Difference Identified
Step 4: Generate Exception Report

For unmatched transactions, the system recommends corrective actions.

Examples:

Exception	Action Required
Missing Bank Entry	Check bank statement and settlement status
Amount Difference	Compare ERP amount and bank credited amount
Step 5: Export Reports

The tool automatically writes results back to the Excel workbook:

Reconciled_Report
Exception_vs_Action_Req
Key Features
Automated ERP vs Bank reconciliation
Exception identification
Actionable exception reporting
Reconciliation status tracking
Reduced manual effort and reconciliation time
Project Structure
Monthly_Reconciliation_Project.ipynb
Monthly_Reconciliation_Tool.xlsm
│
├── ERP_Data
├── Bank_Data
├── Reconciled_Report
└── Exception_vs_Action_Req
Exception Report

Contains:

Missing bank transactions
Amount discrepancies
Suggested corrective actions
