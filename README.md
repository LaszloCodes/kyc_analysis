<p align="center">
  <img src="images/kyc.png" alt="Screenshot" width="600"/>
</p>

# KYC analysis and improvement

## Objective: 
Analyze the Know your Customer (KYC) process to uncover key drivers behind the declining pass rate over time, and develop actionable recommendations to address root causes. A process optimization challenge within a rapidly scaling neobank.

## Problem statement 
A neobank must conduct a Know Your Customer (KYC) process to verify the identity of all customers during the account opening procedure. This process consists of two main checks: a Document Verification and a Facial Similarity Check. Customers successfully pass KYC only if they clear both checks. Recently, the overall KYC pass rate has declined significantly.

The KYC pass rate is defined as the number of customers who successfully pass both checks, divided by the total number of customers who attempt the KYC process.

## Project structure 
```.
├── data/                # Raw data files
├── images/              # Project logo
├── notebook/            # Jupiter notebook with analysis
├── README.md
```

## Dataset: 
Source: Revolut KYC case study 
  'facial_similarity_report.csv': 
  'doc_report.csv':

## Methodology 
- Data cleanup 
- Exploratory Data Analysis
- Pass rate analysis
- Analysis of users with multiple attempts 

## Results
