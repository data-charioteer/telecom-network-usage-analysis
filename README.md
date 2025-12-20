# Telecom Network Usage Analysis (Milan CDR)

## Overview
Analysis of one week of telecom usage data (calls, SMS, and internet traffic) across cell towers in Milan to identify peak usage patterns, high-load towers, and insights for network optimization.

## Problem Statement
To analyze temporal telecom usage patterns and detect congestion-prone cell towers using aggregated Call Detail Records (CDR) data.

## Tools & Skills
Python, Pandas, NumPy, Matplotlib, Seaborn, Exploratory Data Analysis, Time-Series Analysis

## Dataset
Source: Telecom Italia Big Data Challenge (Milan CDR)  
Period: 1–7 November 2013  
Size: ~15 million rows  
Note: Raw data is not included due to dataset size and licensing constraints.

## Key Analysis
- Daily and hourly traffic trend analysis  
- Peak usage hour identification  
- High-load cell tower (CellID) analysis  
- Correlation analysis between calls, SMS, and internet traffic  

## Key Insights
- Evening hours show peak network usage  
- A small number of cell towers handle disproportionately high traffic  
- Strong correlation across services indicates simultaneous demand  

## Repository Structure
Telecom_Network_Usage_Analysis.ipynb  
README.md  
.gitignore  

## Conclusion
A real-world telecom analytics case study demonstrating Python-based EDA, time-series analysis, and business-oriented insights.
