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

## Json Upload

Ideal for users with structured financial or transactional data.

### Expected Schema 1 - [Download here](sample_files/Input_Format_1.json)
```
{
    "Transaction level":
    [
        {
            "Transaction_ID": 1,
            "Customer_ID": "C1",
            "Account_ID": "A1C1",
            "TransactionType": "CREDIT",
            "Description": "REMOTE ONLINE DEPOSIT 1",
            "Txnamount": 300.0,
            "Txndate": "2024-09-09",
            "Availablebalance": 286631.73
        }
    ]
}
```

### Expected Schema 2 - [Download here](sample_files/Input_Format_2.json)

```
{
    "Transaction level":
    [
        {
            "Transaction_ID": 1,
            "Customer_ID": "C1",
            "Account_ID": "A1C1",
            "TransactionType": "CREDIT",
            "Description": "REMOTE ONLINE DEPOSIT 1",
            "Txnamount": 300.0,
            "Txndate": "2024-09-09"
        }
    ],
    "Account level":
    [
        {
            "Customer_ID": "C1",
            "Account_ID": "A1C1",
            "Balance_date": "2024-09-09",
            "Balance": 100
        }
    ]
}
```

### Plaid Asset Report

In addition to above formats we also support plaid asset report. You can see the sample [here](sample_files/btiApiPlaidAssetReportSample.json)

### Finicity VOA Report

In addition to above formats we also support plaid asset report. You can see the sample [here](sample_files/btiApiFinicityVoaHistorySample.json)

## Steps to Upload

1.	Navigate to Data Upload → CSV/JSON Upload.
2.	Choose your file, click Validate, then Submit.
3.	Processing typically completes within 1–2 minutes.

## Plaid Bank Connection  

Connect your bank account directly using Plaid Link, and our platform will automatically retrieve your recent transactions and generate insights — no file upload needed.

### How It Works
1.	Go to Data Upload → Connect Bank Account.
2.	Click Connect with Plaid.
3.	A secure Plaid Link window will appear.
4.	Choose your bank (e.g., Chase, Wells Fargo, Bank of America).
5.	Log in with your online banking credentials via Plaid’s secure interface.
6.	Once authenticated, the connection will close automatically.
7.	Your recent bank transactions will be fetched and processed.

### Supported Banks

Plaid supports over 12,000+ financial institutions across:
- U.S. Retail and Business Banks
- Credit Unions
- Digital and Neobank Accounts

Security & Compliance
- Authentication happens directly within Plaid (we never see or store your credentials).
- Data transfer is encrypted end-to-end using TLS 1.2+.
- Only read-access is used — we cannot move or modify money.
- You can revoke access at any time from your Plaid dashboard.

## API Integration
For enterprise or developer users looking to integrate the platform programmatically.

### API Documentation

Available under API Access → Docs.

### Key Endpoints

| Method | Endpoint | Description | Formats Supported | 
| :------- | :------: | :------: | :------: |
| POST | /processData | Process data (JSON/CSV) | BTI, Plaid Asset Report and Finicity VOA Report |
| GET | /getScore | Retrieve the generated score | Get the risk score for the customer |
| GET | /getReport | Fetch detailed analytics report | Get all the metrics for the customer |

You can access the complete documentation [here](https://belhc7lbhe.apidog.io/bti-api-2886719f0) for more information.

### Authentication

Generate your API key under My Profile → API Keys, then include it in your request headers:
Authorization: Bearer <your_api_key>
Sample cURL Command
curl -X POST https://api.yourdomain.com/uploadData \
  -H "Authorization: Bearer <your_api_key>" \
  -F "file=@sample.csv"

