# SaaS Metrics Dashboard – Power BI

A production Power BI report built to demonstrate executive-level SaaS analytics — MRR trends, customer health, churn analysis, and revenue breakdowns across three report pages.

![Power BI](https://img.shields.io/badge/Tool-Power%20BI-F2C811) ![DAX](https://img.shields.io/badge/Language-DAX-yellow) ![No Real Data](https://img.shields.io/badge/Data-Fictional-green)

## 📥 Download

[**→ SaaS_Metrics_Dashboard.pbix**](SaaS_Metrics_Dashboard.pbix)

Open in Power BI Desktop (free). No gateway, no workspace, no login required.

---

## 🌐 Live Browser Demo

Don't have Power BI Desktop? The dashboard also runs as an interactive HTML demo:

[**→ Open Live Demo**](https://gmaglasang.github.io/App_Build/saas-metrics/demo.html)

---

## Report Pages

**Executive Overview**
- MRR trend with monthly breakdowns
- Active customer count and churn rate KPIs
- Revenue split by plan type and industry

**Revenue Breakdown**
- Year-over-year MRR vs. target
- Growth rate trend and country-level distribution
- Dynamic filtering by year, country, and plan

**Customer Health**
- Active customer trends over time
- Churn analysis by plan
- Top customers by MRR
- At-risk account identification

---

## Data Model

Built on a star schema with fictional sample data:

| Table | Type | Description |
|---|---|---|
| `Fact_Subscriptions` | Fact | Monthly snapshot of customer MRR and status |
| `Dim_Customers` | Dimension | Customer attributes — industry, country, acquisition channel |
| `Dim_Plans` | Dimension | Subscription plan tiers |
| `Dim_Date` | Date | Standard calendar table |

---

## Key DAX Patterns

| Measure | Pattern |
|---|---|
| `Churned MRR` | `CALCULATETABLE` + `ADDCOLUMNS` for first-churn detection |
| `Churn Rate` | Point-in-time with `SELECTEDVALUE` + `MAX` fallback |
| `Net Revenue Retention` | Period-over-period MRR ratio via `EDATE` |
| `Cohort Retention %` | Cross-context cohort membership with `ALL(Dim_Date)` |
| `MRR Target` | Compound growth projection using `POWER` |

Full annotations for these measures: [**→ DAX Showcase**](https://github.com/gmaglasang/powerbi-dax-showcase)

---

## Privacy

All data is entirely fictional. No real company, customer, or financial information is included.

---

*Built by [Guilbert Maglasang](https://github.com/gmaglasang) · [Portfolio](https://gmaglasang.github.io) · [DAX Showcase](https://github.com/gmaglasang/powerbi-dax-showcase)*
