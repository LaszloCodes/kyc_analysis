<p align="center">
  <img src="images/kyc.png" alt="Screenshot" width="600"/>
</p>

# KYC analysis and improvement

## TL;DR 
The KYC pass rate decline is a document check problem, not a facial check problem. About 78% of failed checks fail on the document step alone, and most of those failures are documents the system could not read at all. A new "rejected" failure mode appears during the period and becomes the dominant driver by October. Separately, roughly 15% of repeat checks are run on customers who had already passed, which is avoidable cost.

## The Business Problem
A fast-scaling neobank verifies every new customer through two checks during account opening:

  __Document verification__: is the ID document genuine, readable and valid?
  __Facial similarity__: does the selfie match the photo on the document?

A customer passes KYC only if both checks are clear. The pass rate has been falling, which means more good customers dropping out of onboarding, more manual review and higher verification spend. The goal was to find the root cause and recommend fixes.

KYC pass rate = customers who clear both checks / customers who attempt KYC.

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
