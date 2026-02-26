# Telecom Network Usage Analysis

## Project Overview

Telecom operators generate massive volumes of data every day through calls, SMS, and internet usage. However, without proper analysis, it is difficult to identify peak traffic hours, congestion-prone cell towers, and overall usage patterns.

This project analyzes telecom network activity data to understand traffic distribution, detect peak usage periods, and identify high-load cell towers. The goal is to generate actionable insights that can help telecom companies optimize network performance and improve user experience.

---

##  Problem Statement

Telecom networks handle millions of activity records daily. Identifying peak traffic hours and overloaded cell towers is critical for:

- Preventing network congestion  
- Improving service quality  
- Optimizing infrastructure investment  
- Enhancing customer experience  

This project performs exploratory and time-series analysis on telecom usage data to uncover meaningful patterns.

---

## Dataset Information

- Source: Telecom Italia Big Data Challenge Dataset  
- Location: Milan, Italy  
- Time Period: 1 Week  
- Total Records: ~15 million  
- Data Includes:
  - Call activity
  - SMS activity
  - Internet traffic
  - Cell tower ID
  - Timestamp information

---

## Tools & Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

---

## Data Cleaning & Preparation

- Handled missing values  
- Converted timestamps to proper datetime format  
- Extracted date and hour for time-series analysis  
- Aggregated traffic by hour and cell tower  
- Removed inconsistencies and validated data integrity  

---

## Analysis Performed

### Hourly Traffic Analysis
- Identified peak network usage hours  
- Compared call, SMS, and internet activity trends  

### Cell Tower Load Analysis
- Calculated total traffic per CellID  
- Identified high-load towers  
- Detected potential congestion points  

### Correlation Analysis
- Analyzed relationship between calls, SMS, and internet usage  
- Observed simultaneous demand trends across services  

---

## Key Insights

- Evening hours show peak telecom traffic usage  
- A small number of cell towers handle disproportionately high traffic  
- Strong correlation exists between call, SMS, and internet usage  
- Network congestion risk is concentrated in specific high-load towers  

---

## Business Impact

This analysis can help telecom companies:

- Identify congestion-prone towers  
- Optimize network capacity  
- Improve infrastructure planning  
- Enhance overall service quality  

---

## Skills Demonstrated

- Large dataset handling (~15 million records)  
- Data cleaning and preprocessing  
- Time-series analysis  
- Aggregation and traffic pattern detection  
- Data visualization  
- Business insight generation  

---

## 📂 Project Structure
Telecom_Network_Usage_Analysis/
│
├── .gitignore
├── README.md
└── Telecom_Network_Usage_Analysis.ipynb


