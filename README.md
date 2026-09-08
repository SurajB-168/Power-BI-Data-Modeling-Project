# 🧩 Power BI Data Modeling - Star Schema

This project takes messy, real-world-style retail data (orders, invoices, shipments, campaigns, inventory) and turns it into a clean, well-organized data model in Power BI, ready for reporting.

## 🔄 Before → After

**Initial model — auto-detected by Power BI on raw import**
![Initial Data Model](docs/Initial%20Data%20Model%20Created%20By%20Power%20BI.jpg)

**Final model — after cleaning and star-schema design**
![Final Data Model](docs/Final%20Data%20Model.jpg)

## 🚀 What This Project Is About

Real-world data is often messy, inconsistent, and spread across multiple sources. This project transforms that raw data into a clean **star schema**, connecting central **fact tables** (e.g., sales) with **dimension tables** (e.g., customers, products, dates).

This structure makes data **consistent, reliable, and easy to analyze**, enabling faster and more accurate reporting and dashboards.

## 💼 The Business Behind the Data

The data represents a retail business, covering:
- 🛒 **Sales & Orders** — from order placement through shipping, invoicing, and payment
- 👤 **Customers** — segments, account managers, contact info, credit terms
- 📦 **Products & Inventory** — product catalog and monthly stock levels
- 📣 **Marketing** — campaign spend, impressions/clicks, and which products each campaign promoted
- 🎯 **Targets** — revenue targets by period, to compare actual sales against goals

## 📂 Repo Structure

```
├── README.md
├── Data Modelling Project.pbix         # Power BI file with the full model and relationships
├── data/
│   ├── Raw Dataset.xlsx                # Original, messy multi-sheet source data
│   └── Final Datasets.xlsx             # Cleaned dimension and fact tables
└── docs/
    ├── Initial Data Model Created By Power BI.jpg   # Auto-detected model on raw import
    └── Final Data Model.jpg                          # Final star schema diagram
```

## 🛠️ What Was Wrong With the Raw Data, and How It Was Fixed

The raw data came with realistic problems. Here's what was found and how each one was handled:

| Raw Data Problem                                              | How It Was Fixed                                              |
| ------------------------------------------------------------- | ------------------------------------------------------------- |
| Orders were split across yearly tables with different columns | Combined into one consistent order table                      |
| Several columns had unclear names (`Column1`, `Column2`)      | Renamed columns based on their actual meaning                 |
| Inventory months were stored as separate columns              | Restructured into one row per product, month, and stock value |
| Customer and location data was duplicated across tables       | Centralized into dedicated customer and location tables       |
| Duplicate tracking fields (`hash_key`, `source_id`) existed   | Used to identify and remove duplicate records                 |
| Customer details were scattered across multiple tables        | Merged into a single customer dimension                       |
| Tables relied on names/codes for relationships                | Added surrogate keys for reliable table relationships         |

**✅ Result:** The raw data was transformed into a **clean, consistent, and analysis-ready structure** suitable for reporting and dashboards.

## 🧱 The Data Model

**Dimension tables** (the "who, what, where, when"): `dim_customers`, `dim_products`, `dim_geo`, `dim_date`, `dim_campaign`, `dim_order_flags`

**Fact tables** (the "what happened"): `fact_sales`, `fact_order_process`, `fact_inventory`, `fact_campaign_spend`, `fact_promotion_coverage`, `fact_sales_target`

Each fact table connects to the relevant dimension tables through ID columns, so you can slice any metric (like sales or spend) by customer, product, location, time, or campaign without complicated joins.

## 🛠️ Tech Stack

- **Power BI Desktop** — Power Query for cleaning and reshaping the data, the Data Model view for building relationships
- **Excel** — used to stage and inspect the original source data

## 📚 What I Learned

- 🔑 How to design ID-based relationships (surrogate keys) to connect data that originally had no reliable way to link together
- 📅 How to handle data that's split inconsistently across time periods (year-over-year column changes)
- 🔄 How to reshape "wide" data (months as columns) into the "long" format needed for proper analysis
- ⭐ How to apply star schema principles — one clear grain per fact table, and shared dimension tables — to keep a data model simple and fast

---

## 👨‍💻 About the Author

**Surajkumar Bevnale**
Data Analyst | SQL • Excel • Power BI • Python
B.Tech, Engineering Physics, IIT Ropar (2023–2027)

- 📫 Reach me at: surajk.b168@gmail.com
- 🔗 LinkedIn: [Surajkumar B](https://www.linkedin.com/in/skb168/)
