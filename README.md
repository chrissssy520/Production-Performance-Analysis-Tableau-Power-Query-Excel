
## Live Dashboard

[View on Tableau Public](https://public.tableau.com/app/profile/christian.aler3008/viz/ProductionAnalysis_17766512791150/MainDashboard)

---

## Author

Christian Aler  
Aspiring Data Analyst | Manila, Philippines  
[Portfolio](https://ckaportfolio.vercel.app)

# Production Performance Analysis

A manufacturing operations analytics project built to identify 
the primary sources of downtime and defects across a multi-machine 
factory environment.

---

## Objective

Identify which machines, shift types, downtime reasons, and operators 
contribute most to production inefficiency — specifically targeting 
downtime rate and defect rate as the two core KPIs.

---

## Tools Used

- **Power Query / Excel** — Data cleaning and transformation
- **Tableau Public** — Dashboard design and visualization

---

## Data Preparation (Power Query)

- Cleaned and transformed raw factory operations data
- Structured into a **fact/dimension table model**
  - `fact_table` — production metrics per machine per shift per day
  - `dim_table` — machine attributes, operator info, shift type
- Joined fact and dimension tables for dashboard consumption

---

## Dashboard Structure

**Main Dashboard**
- OEE (Overall Equipment Effectiveness) with Availability, 
  Performance, and Quality breakdown
- Downtime Rate % and Defect Rate % as primary KPIs
- Yield Rate % and Cycle Time Rate %
- Machine-level performance table sorted by defect share
- OEE comparison by shift (Morning / Afternoon / Night)
- Dynamic Top Priority Actions panel — auto-updates based on 
  current filter state to surface the highest downtime category 
  and highest defect source

**DTR Main (Downtime Drill Down)**
- Average downtime minutes per machine sorted by machine age
- Downtime distribution by reason category with average 
  duration per incident
- Downtime rate comparison across all three shifts

**Def Main (Defect Drill Down)**
- Total defective units by machine grouped by machine type
- Operator defect rate vs units produced scatter plot 
  filtered to highest defect machine
- Total defects broken down by product type and machine type

---

## Key Design Decisions

- **No time series added** — month-over-month trend was flat 
  across the dataset, adding a trend line would have added 
  noise without analytical value
- **No hard-coded recommendations in dashboard** — dashboard 
  is a live monitoring tool; recommendations belong in a 
  separate reporting layer
- **No entity names or specific values in insight text** — 
  all descriptive text is chart-level and filter-safe, 
  ensuring accuracy regardless of data updates or filter state
- **Drill-down via dashboard actions** — DTR Main and Def Main 
  are accessible via double-click on the primary KPI cards

---

## Data Limitations

- No product pricing or maintenance cost data available — 
  financial impact of downtime and defects cannot be quantified
- Operator performance cannot be fully isolated from machine 
  condition without assignment history data
- Dataset is static — findings reflect the period covered 
  by the raw data only

---
