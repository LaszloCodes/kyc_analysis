<p align="center">
  <img src="images/kyc.png" alt="Screenshot" width="600"/>
</p>

# KYC analysis and improvement

## Objective
Analyze the Know Your Customer (KYC) process to uncover key drivers behind the declining pass rate over time, and develop actionable recommendations to address root causes. A process optimization challenge within a rapidly scaling neobank.

## Problem statement
A neobank must conduct a Know Your Customer (KYC) process to verify the identity of all customers during the account opening procedure. This process consists of two main checks: a Document Verification and a Facial Similarity Check. Customers successfully pass KYC only if they clear both checks. Recently, the overall KYC pass rate has declined significantly.

The KYC pass rate is defined as the number of customers who successfully pass both checks, divided by the total number of customers who attempt the KYC process.

## Project structure 
```.
├── data/                # Raw data files
├── images/              # Project logo
├── kyc_analysis.ipynb   # Jupiter notebook with analysis
├── requirements.txt
├── README.md
```

## Dataset: 
Source: Revolut KYC case study 
  __'facial_similarity_report.csv'__: document check results
  __'doc_report.csv'__: facial similarity check results
  
176,404 KYC attempts from 142,724 users, May to October 2017.

## Methodology 
- Data cleanup 
- Exploratory Data Analysis
- Pass rate analysis (pass rate per user, by week of first attempt)
- Deep dive into failed document checks
- Analysis of users with multiple attempts 

## Results
The KYC pass rate dropped from ~97% (mid June to early July) to ~72% (early October).
  - The document check is the main driver. ~78% of failed checks fail on the document check only. The facial check improved over the same period.
  - Two separate issues in the document check:
      1. From 11 July, more and more images can't be read at all (rejected sub-result), up to ~21% of checks. 94% of these have image quality "unidentified" and no document details were extracted, so it is not fraud.
      2. From mid September to the end of October, a new document quality check flagged up to ~21% of checks as caution, mainly passports and UK documents (~34% caution vs ~3% before). It drops back suddenly at the end of October.
  - Users who get a rejected result often give up: only ~33% of them eventually pass vs ~93% of other users.
  - 5,788 checks (3.3%) were done by users who had already passed, an unnecessary cost.

## Recommendations
  1. Find out what changed around 11 July (app release, photo capture flow or vendor settings)
  2. Check image quality in the app before upload (blur, glare, document in frame) so users can retake the photo straight away
  3. Confirm with the vendor what changed in the document quality check, and monitor caution rates by document type and country to catch similar issues early
  4. Block new KYC submissions once a user has passed

## How to run
pip install -r requirements.txt
jupyter notebook kyc_analysis.ipynb
