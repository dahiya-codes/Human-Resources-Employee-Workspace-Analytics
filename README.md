# Human-Resources-Employee-Workspace-Analytics
Project Overview:- 

A production-grade HR analytics pipeline that transforms raw IBM HR attrition data into board-ready workforce intelligence. This project demonstrates the full data analyst toolkit: data governance in Excel → advanced SQL segmentation → interactive executive dashboard.

Headline finding: 26.5% attrition rate — nearly double the industry benchmark. 120 employees at high burnout risk. Sales department leads at 28.8%. The dashboard tells you exactly who, why, and what to do about it.
hr-analytics-employee-attrition/

PIPELINE ARCHITECTURE:- 

│[Raw IBM HR CSV]
      │
      ▼
[STAGE 1 — Excel Workbook]
  • 01_RAW_DATA         ← Source data (1,470 rows, 34 columns)
  • 02_ANONYMIZED_PREP  ← EmpHash masking, IFS tenure/distance buckets
  • 03_ANOMALY_AUDIT    ← Conditional formatting flags & governance checks
  • 04_SUMMARY_STATS    ← KPI cards & department breakdown
  • 05_CLEAN_EXPORT_CSV ← SQL-upload-ready governance file
      │
      ▼
[STAGE 2 — SQL (PostgreSQL / BigQuery)]
  • CTE              → High performers with low environment satisfaction
  • Window Function  → AVG() OVER (PARTITION BY JobRole) pay gap
  • CASE WHEN        → 7-factor Burnout Index Score (0–18 pts)
  • Subquery         → Department attrition vs company average
      │
      ▼
[STAGE 3 — Power BI Dashboard]
  • Diverging bar chart    → Dept attrition vs company average
  • Scatter plot matrix    → Tenure × Income × Burnout Profile
  • Interactive cross-filter → High Burnout card → role drill-down
  • Narrative story arc    → What? Why? Who?
