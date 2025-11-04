# Input Data Options

Our platform supports multiple input types, allowing you to work with both structured and unstructured data sources.

## CSV Upload

Ideal for users with structured financial or transactional data.

### Expected Schema 1

#### Transaction_level.csv

| Field Name | Description | Required |
| :------- | :------: | :------: |
| Txndate | Date of transaction (YYYY-MM-DD) | &#9745; |
| Description | Transaction narrative or details | &#9745; |
| Txnamount | Transaction value | &#9745; |
| TransactionType | Credit or Debit | &#9745; |
| Availablebalance | Running account balance | &#9745; |
| Customer_ID | Customer Identification Number | &#9745; |
| Transaction_ID | Transaction ID (optional) | Optional |
| Account_ID | Customer Account identification Number | &#9745; |

#### Account_level.csv

| Field Name | Description | Required |
| :------- | :------: | :------: |
| Customer_ID | Customer Identification Number | &#9745; |
| AsofDate | Date the customer application came into system | Optional |
| Account_ID | Customer Account identification Number | &#9745; |


### Expected Schema 2

#### Transaction_level.csv

| Field Name | Description | Required |
| :------- | :------: | :------: |
| Txndate | Date of transaction (YYYY-MM-DD) | &#9745; |
| Description | Transaction narrative or details | &#9745; |
| Txnamount | Transaction value | &#9745; |
| TransactionType | Credit or Debit | &#9745; |
| Customer_ID | Customer Identification Number | &#9745; |
| Transaction_ID | Transaction ID (optional) | Optional |
| Account_ID | Customer Account identification Number | &#9745; |

#### Account_level.csv

| Field Name | Description | Required |
| :------- | :------: | :------: |
| Customer_ID | Customer Identification Number | &#9745; |
| AsofDate | Date the customer application came into system | Optional |
| Account_ID | Customer Account identification Number | &#9745; |
| Balance | Account Balance | &#9745; |
| Balance_date | Date on which Account Balance is reported | &#9745; |

Note: AsofDate is optional, in case it is not provided, today will be considered as AsofDate


## Steps to Upload

1.	Navigate to Data Upload → CSV/JSON Upload.
2.	Choose your file, click Validate, then Submit.
3.	Processing typically completes within 1–2 minutes.

Tip: Download a sample CSV file [Account_level.csv](sample_files/Account_level.csv) and [Transaction_level.csv](sample_files/Transaction_level.csv) for reference.

