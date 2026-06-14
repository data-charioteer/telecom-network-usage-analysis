# Telecom Network Usage Analysis (Milan CDR Dataset)

Analysis of ~15 million telecom activity records across Milan's cell tower network to uncover traffic patterns, detect congestion-prone towers, and generate actionable insights for network optimization.

**Tools & Technologies:** Python · Pandas · NumPy · Matplotlib · Seaborn · Jupyter Notebook

---

## Visualizations
<img width="712" height="393" alt="image" src="https://github.com/user-attachments/assets/1a25a67a-b58d-4c2f-8da6-cc844c02e9cd" />
<img width="1001" height="547" alt="image" src="https://github.com/user-attachments/assets/3be0545c-ac2c-4686-9746-7d99dda444e2" />
<img width="1001" height="568" alt="image" src="https://github.com/user-attachments/assets/706c7704-ae09-4776-80aa-45e4e86109f1" />
<img width="640" height="529" alt="image" src="https://github.com/user-attachments/assets/8fec8b4d-b0df-4914-9006-29ec53bd09c7" />
<img width="643" height="690" alt="image" src="https://github.com/user-attachments/assets/65aca161-1e4b-4dde-9894-0af38438fa07" />

---

## Problem Statement

Telecom networks experience fluctuating demand across time and location, leading to congestion and degraded service quality. Without proper analysis, it is difficult to identify when and where the network is under stress.

This project addresses:
- When does peak usage occur, and how does it vary by hour and day?
- Which cell towers carry disproportionately high load?
- How do calls, SMS, and internet usage relate to each other?
- What can these patterns tell us about capacity planning?

---

## Dataset

| Field | Detail |
|---|---|
| **Source** | [Telecom Italia Big Data Challenge](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/EGZHFV) |
| **Location** | Milan, Italy |
| **Time Period** | 1–7 November 2013 |
| **Total Records** | ~15 million |
| **Columns** | CellID, datetime, smsin, smsout, callin, callout, internet |

The dataset captures call, SMS, and internet activity per cell tower per hour across 7 daily CSV files, merged into a single DataFrame for analysis.

---

## Project Structure

```
telecom-network-usage-analysis/
│
├── README.md
├── .gitignore
├── Telecom_Network_Usage_Analysis.ipynb
└── images/                         ← add chart screenshots here
    ├── hourly_traffic.png
    ├── daily_usage.png
    ├── top10_towers.png
    ├── correlation_heatmap.png
    └── hour_day_heatmap.png
```

---

## Methodology

**1. Data Loading & Merging** — Used `glob` to read 7 daily CSV files and concatenated them into one DataFrame with a `date` column.

**2. Data Cleaning** — Converted timestamps to `datetime`, extracted `hour`, validated column types, and confirmed no critical missing values.

**3. Exploratory Analysis** — Computed summary statistics revealing internet traffic (avg: 102.32 units) is ~15× higher than calls and SMS on average, but with a median near 0 — indicating heavy concentration in hotspot areas.

**4. Time-Series Analysis** — Aggregated traffic by hour and date to identify daily and hourly demand cycles.

**5. Cell Tower Load Analysis** — Ranked all towers by total internet usage to identify congestion risk zones.

**6. Correlation Analysis** — Built a correlation matrix across all five usage metrics.

---

## Key Findings

### Daily Traffic Patterns
- Internet traffic rose ~**30%** from the first three days to the second half of the week — from ~82–83M units on 1–3 Nov to over **108M units** from 4 Nov onward.
- Peak daily usage hit **111 million units** on 5 November.
- Weekends (2–3 Nov) showed noticeably lower call and SMS activity, while internet usage remained relatively stable.

### Hourly Network Activity

| Period | Hours | Activity Level |
|---|---|---|
| Off-peak | 2 AM – 6 AM | Lowest (~14–15M units/hour) |
| Ramp-up | 7 AM – 10 AM | Sharp rise to ~30M units |
| **Peak** | **11 AM – 5 PM** | **Highest: 35–38M units/hour** |
| Evening cool-down | 8 PM – 11 PM | Gradual decline |

The peak window (11 AM – 5 PM) is consistent across all 7 days, indicating a structural usage pattern rather than random spikes.

### High-Load Cell Towers

| Rank | CellID | Total Internet Usage |
|---|---|---|
| 1 | 5161 | ~1.51 million units |
| 2 | 5059 | ~1.1 million units |
| 3 | 5259 | ~1.1 million units |
| 4 | 5061 | ~1.1 million units |

High-load towers appear in numerical clusters (5059–5061, 5258–5259), suggesting geographically adjacent zones with concentrated demand. The top towers carry a disproportionate share of overall network load.

### Service Correlations

| Metric Pair | Correlation |
|---|---|
| Call-in ↔ Call-out | **0.982** (near-perfect) |
| SMS-in ↔ SMS-out | **0.861** (very strong) |
| Internet ↔ Calls/SMS | **0.85 – 0.90** (strong) |

Strong correlation between internet and voice/SMS confirms that certain geographic zones are high-demand hotspots across all services simultaneously.

---

## Recommendations

- **Capacity Upgrades** — Towers 5161, 5059, and 5259 require bandwidth expansion or small cell deployment given sustained million-unit weekly loads.
- **Maintenance Scheduling** — Schedule network maintenance outside the 11 AM – 5 PM peak window to minimize customer impact.
- **Dynamic Resource Allocation** — Allocate additional spectrum and backhaul resources during mid-day peaks.
- **Weekend Optimization** — Reduced weekend demand creates a safe window for planned upgrades or load testing without affecting peak users.

---

## Skills Demonstrated

- Large-scale dataset handling (~15M records across multiple files)
- Multi-file data loading and merging with `glob`
- Time-series aggregation and pattern detection
- Cell-level network load analysis
- Correlation analysis across multiple metrics
- Data visualization (line charts, bar charts, heatmaps)
- Business insight generation and actionable recommendations
