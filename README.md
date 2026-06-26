# Royal Trump Enterprises — Sales Intelligence Dashboard

A Business Intelligence system built in Excel that turns daily cyber café sales transactions into a live, auto-updating dashboard — covering revenue tracking, service performance, and category analysis for a small business in Nairobi, Kenya.

**Prepared by:** Doreen Wathimu

---

## Overview

Royal Trump Enterprises is a cyber café offering printing, photocopying, lamination, government document services (e-Citizen, DL renewal, passport applications), and related services. Daily sales were originally logged by hand into a spreadsheet with inconsistent naming, mixed-in expenses, and no way to see trends or top performers at a glance.

This project rebuilds that raw log into a structured BI system with:

- A clean, repeatable **data entry workflow**
- A **lookup-based categorization engine** so every transaction is automatically classified
- **Pivot tables** summarizing revenue by category, service, month, week, and day
- A live **Dashboard** with KPI cards and four charts that update automatically as new sales are entered
- A documented **data quality process** showing what was cleaned and why

## Business Objective

> Design a Business Intelligence system that transforms daily sales transactions into meaningful insights for decision-making — enabling monitoring of revenue trends, identification of high-performing services, evaluation of category performance, and a foundation for future financial and credit management modules.

## Dashboard Preview

The Dashboard sheet includes:

- **KPI row** — Total Revenue, Total Transactions, Average Sale Value, Highest Single Sale
- **Revenue by Category** — pie chart showing each category's share of total revenue
- **Revenue by Service** — top services ranked by income
- **Monthly Revenue Trend** — line chart tracking revenue over time
- **Sales by Day of Week** — bar chart identifying the busiest trading days

## Workbook Structure

| Sheet | Purpose |
|---|---|
| `README` | Project overview, objective, and scope (in-workbook version of this file) |
| `DATA_INPUT` | Daily entry point — type Date, Service, and Amount; Category fills in automatically |
| `RAW_DATA` | Full historical transaction log, cleaned and structured for analysis |
| `LOOKUPS` | Service-to-category mapping table used to auto-classify every transaction |
| `PIVOT_TABLES` | Revenue summarized by Category, Service, Month, Week, and Day |
| `DASHBOARD` | The live visual summary — KPIs and charts, built on top of the pivot tables |
| `DATA_QUALITY` | Documents the cleaning steps applied to the original raw data |
| `EDA` | Exploratory summary metrics (revenue, transaction count, averages) |
| `SETTINGS` | Workbook configuration (reserved for future automation) |

## How It Works

1. **Enter a transaction** in `DATA_INPUT` — Date, Service, Amount.
2. A `VLOOKUP` against the `LOOKUPS` table automatically assigns a Category.
3. The entry flows into `RAW_DATA` via formula, joining the historical dataset.
4. `PIVOT_TABLES` recalculates totals by category, service, and time period.
5. `DASHBOARD` reflects the updated figures immediately — no manual refresh of formulas required.

## Data Quality Notes

The original raw export contained 670 rows, including 70 entirely blank separator rows that were identified and removed. Entries that weren't genuine sales — rent payments, owner cash withdrawals, and a small number of personal/non-business expenses — were re-tagged into dedicated categories (`Rent / Fixed Expense`, `Owner Withdrawal`, `Personal / Non-Business`) so they no longer distort revenue and "top service" metrics. This process and its findings are logged in the `DATA_QUALITY` sheet.

## Current Status

**Module 1 — Sales Intelligence Dashboard:** in progress. Core data pipeline (input → categorization → pivot tables → dashboard) is functional; visual styling and a few category edge cases are still being refined.

## Roadmap

- [ ] Finish dashboard visual styling (color theme, card layout)
- [ ] Resolve remaining "Other Services" catch-all entries for cleaner category reporting
- **Financial Dashboard** — expenses, profit margins, budget tracking
- **Credit Management Dashboard** — customer credit/debt tracking
- **Automation & Reporting** — scheduled summaries, reduced manual upkeep

## Tools

- Microsoft Excel (formulas, PivotTables, PivotCharts)
- `VLOOKUP`, `SUMIFS`/`COUNTIFS`, array formulas
- Manual data cleaning and validation
