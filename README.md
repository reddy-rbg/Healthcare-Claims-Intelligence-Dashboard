# Healthcare Claims Intelligence Dashboard

![Power BI](https://img.shields.io/badge/Power%20BI-Healthcare%20Analytics-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Dataset](https://img.shields.io/badge/Synthetic%20Dataset-1M%2B%20Claims-1F7A8C?style=for-the-badge)
![Focus](https://img.shields.io/badge/Focus-Cost%20%7C%20Denials%20%7C%20SLA%20%7C%20Risk-2F3C7E?style=for-the-badge)

A portfolio-grade Power BI analytics solution for healthcare payer claims operations. This dashboard turns a large synthetic claims dataset into an executive-ready intelligence layer for monitoring cost, denial trends, SLA performance, payment delays, provider risk, member utilization, and data quality exposure.

---

## Executive Snapshot

This project simulates the kind of reporting environment a payer leadership, claims operations, provider network, or analytics team would use to answer high-impact questions:

- Where are claim costs rising, and which claim types are driving them?
- Which providers show elevated denial rates, quality risk, or out-of-network cost leakage?
- Which regions, plans, or claim categories are missing SLA targets?
- How much payment delay exists after approval?
- Which records need data quality remediation before leadership reporting?
- Which member groups and risk segments are contributing most to utilization?

The result is a six-page Power BI dashboard built around operational visibility, financial control, and drill-through investigation.

## Dashboard Preview

| Executive Summary | Claims Operations |
| --- | --- |
| ![Executive Summary](screenshots/Executive%20Summary.png) | ![Claims Operations](screenshots/Claims%20Operations.png) |

| Provider Performance | Member and Plan Analysis |
| --- | --- |
| ![Provider Performance](screenshots/Provider%20Performance.png) | ![Member and Plan Analysis](screenshots/Member%20%26%20Plan%20Analysis.png) |

| SLA and Data Quality | Claim Detail |
| --- | --- |
| ![SLA and Data Quality](screenshots/SLA%20%26%20Data%20Quality.png) | ![Claim Detail](screenshots/Claim%20Detail.png) |

## What This Dashboard Delivers

| Area | Business Value |
| --- | --- |
| Cost Intelligence | Track total claim amount, approved amount, paid amount, high-cost outliers, and claim type cost drivers. |
| Denial Analytics | Monitor denial rate, denial reason patterns, provider-level denial behavior, and operational bottlenecks. |
| SLA Compliance | Compare processing days against SLA targets by claim type, region, and operational segment. |
| Provider Risk | Evaluate provider cost, denial rate, network status, quality score, and risk indicators. |
| Member and Plan Insights | Analyze utilization by plan type, age group, risk score, state, and region. |
| Payment Operations | Track paid amount, payment method, payment delay, and late-payment exposure. |
| Data Quality Monitoring | Surface duplicate claims, missing providers, invalid claim amounts, blank denial reasons, and reporting reliability risk. |

## Project Assets

```text
.
|-- Healthcare_Claims_Intelligence_Dashboard.pbix
|-- DAX_Measures_Reference.xlsx
|-- healthcare_dataset/
|   |-- Claims.csv
|   |-- Members.csv
|   |-- Providers.csv
|   |-- Diagnosis.csv
|   |-- Payments.csv
|   |-- SLA_Targets.csv
|   |-- Date.csv
|   `-- Data_Dictionary.csv
|-- screenshots/
|   |-- Executive Summary.png
|   |-- Claims Operations.png
|   |-- Provider Performance.png
|   |-- Member & Plan Analysis.png
|   |-- SLA & Data Quality.png
|   `-- Claim Detail.png
`-- documentation/
    `-- Healthcare_Claims_Dataset_Documentation.txt
```

## Data Model

The model follows a healthcare payer analytics pattern with claim and payment fact tables connected to conformed dimensions.

| Table | Type | Purpose |
| --- | --- | --- |
| Claims | Fact | Claim-level transactions, status, cost, denial, SLA, and processing metrics. |
| Payments | Fact | Payment records for approved and partially approved claims. |
| Members | Dimension | Synthetic member demographics, plan type, geography, enrollment, and risk score. |
| Providers | Dimension | Provider specialty, region, network status, and quality score. |
| Diagnosis | Dimension | Diagnosis code, category, and severity level. |
| SLA_Targets | Dimension | Target processing days and business priority by claim type. |
| Date | Dimension | Calendar table for time intelligence and trend analysis. |

Recommended relationship pattern:

```text
Members      -> Claims <- Diagnosis
Providers    -> Claims <- SLA_Targets
Date         -> Claims -> Payments
```

## Dashboard Pages

1. **Executive Summary** - Leadership-level view of claim volume, cost, approvals, paid amount, denial rate, SLA compliance, and data quality score.
2. **Claims Operations** - Operational tracking for claim status, SLA misses, processing time, backlog, and denial trends.
3. **Provider Performance** - Provider-level visibility into claim amount, denial behavior, network impact, quality score, and risk.
4. **Member and Plan Analysis** - Utilization and cost patterns by age group, plan type, risk score, state, and region.
5. **SLA and Data Quality** - Monitoring layer for SLA misses, duplicates, missing provider IDs, invalid amounts, and blank denial reasons.
6. **Claim Detail** - Drill-through page for investigating individual claim records and operational exceptions.

## Analytics Features Showcased

- Power Query cleaning and transformation workflow
- Star schema modeling with fact and dimension tables
- DAX measures for KPIs, rates, delays, scores, and trend analysis
- Time intelligence using a dedicated date dimension
- Drill-through investigation pages
- Slicers and cross-filtered visuals
- Provider performance and network leakage analysis
- SLA compliance monitoring
- Data quality exception reporting
- Large synthetic dataset handling for 1M+ claim records

## Dataset Notes

This project uses a fully synthetic healthcare payer dataset created for portfolio and practice use. It is inspired by public synthetic healthcare data concepts such as CMS DE-SynPUF and Synthea-style healthcare utilization modeling, but it is not copied from a real hospital, payer, provider, employer, or patient database.

No real patient information, protected health information, company-confidential data, or production claim records are included.

The dataset intentionally includes realistic quality issues:

- duplicate claim IDs
- missing provider IDs
- zero and negative claim amounts
- blank denial reasons on denied claims
- SLA missed claims
- late payments
- high-cost outliers
- higher-risk out-of-network provider patterns

These issues are included so the dashboard can demonstrate practical claims data validation, exception monitoring, and operational risk analysis.

## How To Use

1. Clone the repository with Git LFS enabled.
2. Open `Healthcare_Claims_Intelligence_Dashboard.pbix` in Power BI Desktop.
3. If Power BI prompts for source paths, update the CSV source location to the local `healthcare_dataset` folder.
4. Refresh the model.
5. Review the `DAX_Measures_Reference.xlsx` workbook for measure documentation and KPI definitions.

```powershell
git lfs install
git clone https://github.com/reddy-rbg/Healthcare-Claims-Intelligence-Dashboard.git
```

## Business Impact Story

This dashboard is designed to show how healthcare claims data can move beyond static reporting into an operational control center. It helps leaders spot cost leakage, claims teams identify processing delays, provider network teams monitor denial and quality risk, and analysts validate the reliability of the underlying data before decisions are made.

## Suggested Portfolio Positioning

**Power BI Healthcare Claims Intelligence Dashboard**  
Built a large-scale Power BI dashboard using a 1M+ row synthetic payer claims dataset, Power Query transformations, star schema modeling, DAX KPIs, drill-through pages, SLA tracking, provider performance analysis, payment delay metrics, and data quality monitoring to analyze claim cost, denials, operational bottlenecks, and provider risk.

---

Designed for healthcare analytics, payer operations, provider network performance, and business intelligence portfolio demonstration.
