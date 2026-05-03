---
title: "UK Real Estate Data Warehouse & OLAP Cube"
description: "End-to-end data-engineering pipeline over ~1.3M UK property sales: from raw CSVs to a MySQL star schema, a Mondrian OLAP cube, and a PDF analytical report. Two interchangeable ETL paths (Pentaho + pure SQL), reproducible via Docker."
tech_stack:
  - "Docker"
weight: 50
---

<div>

A complete data-warehousing pipeline around the UK Government's [Price Paid Data](https://www.gov.uk/government/statistical-data-sets/price-paid-data-downloads), built for the **Data Analysis and Integration** course at IST.

## What I built

### Dimensional model

A textbook Kimball **star schema** with one fact table and three dimensions:

```
                          ┌─────────────────┐
                          │    dim_time     │
                          └────────┬────────┘
                                   │
 ┌──────────────────┐      ┌───────┴──────────┐      ┌──────────────────┐
 │   dim_location   │──────┤   fact_sales     │──────│   dim_property   │
 └──────────────────┘      └──────────────────┘      └──────────────────┘
```

- Smart key `date_key = YYYYMMDD` for `dim_time`.
- Surrogate keys (auto-increment) for `dim_location` and `dim_property`.
- `'No Data'` sentinel buckets replacing NULLs in dimension attributes.

### Two interchangeable ETL paths

| | Pentaho (`.ktr`) | Pure SQL |
|---|---|---|
| Tool | Pentaho Data Integration GUI | Plain SQL scripts |
| Editable as text | Painful (XML graph) | Trivial |
| Execution model | Streaming, row-by-row | Set-based, index-friendly |
| CI-friendly | Hard | Easy (just pipe SQL) |

Both populate the same warehouse tables; a sanity-check query proves parity between the source totals and the fact aggregate. The pure-SQL path uses `INSERT IGNORE`, a recursive CTE for the calendar dimension, and `INSERT ... ON DUPLICATE KEY UPDATE` for the fact.

### OLAP cube and analytics

I built a **Mondrian** XML cube on top of the warehouse with three hierarchies:

- **Location**: County → District → City
- **Time**: Year → Quarter → Month → Day
- **Property**: Type → New Build → Tenure → Postcode → PAON → SAON

Two measures: `Sales` (sum of price) and `Transactions` (count).

I wrote MDX analyses for Greater London breakdowns and a **PDF analytical report** in Pentaho Report Designer that lists counties above £1 bn with a top-5 pie chart driven by a Groovy JFreeChart post-processor.

### Reproducibility

The whole pipeline runs in **Docker Compose** with MySQL 8 pre-configured for `local_infile` and CTE recursion, plus cross-platform bootstrap scripts (PowerShell + Bash). End-to-end run: under a minute.

</div>
