# predictive-maintenance-powerbi
Industrial Predictive Maintenance &amp; Reliability Analytics Dashboard built using Power BI and DAX.
# Predictive Maintenance & Machine Reliability Analytics

## Executive Summary
An interactive 2-page Power BI dashboard built using the industrial **AI4I 2020 Predictive Maintenance Dataset** (10,000 operational records). The project analyzes equipment reliability metrics, machine variant performance, thermal condition monitoring trends, and specific failure mechanisms to enable data-driven preventive maintenance strategies.

---

## Key Performance Indicators (KPIs)
* **Overall Equipment Effectiveness (OEE):** **88.67%** — Evaluates mechanical availability and performance efficiency.
* **Mean Time Between Failures (MTBF):** **166.7 Hours** — Tracks average operational runtime between breakdown events.
* **Mean Time To Repair (MTTR):** **0.8 Hours** — Measures average turnaround time to restore failed equipment.
* **Total Machine Failures:** **339 Units** — Represents breakdown instances out of 10,000 cycles.

---

## DAX Measures Used
```dax
// OEE Percentage
OEE_Pct = DIVIDE([Total_Operating_Hours] - [Downtime_Hours], [Total_Operating_Hours], 0)

// Mean Time Between Failures (MTBF)
MTBF_Hours = DIVIDE([Total_Operating_Hours], [Total Failures], 0)

// Mean Time To Repair (MTTR)
MTTR_Hours = DIVIDE([Total_Downtime_Hours], [Total Failures], 0)

// Total Machine Failures
Total Failures = SUM(ai4i2020[Machine failure])
