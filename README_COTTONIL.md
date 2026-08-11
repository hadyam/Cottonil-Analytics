# COTTONIL Egypt --- Business & Data Analysis

> **From Data to Decisions**\
> An end-to-end Business & Data Analytics project built to transform raw
> operational data into actionable business intelligence using Power BI.

## Project Overview

**COTTONIL Business & Data Analysis** is a Power BI analytics solution
designed to provide a multi-dimensional view of commercial, product,
supplier, pricing, discount, and profitability performance.

The project goes beyond traditional reporting. Instead of presenting
sales figures only, it focuses on identifying **performance deviations,
profitability drivers, product behavior, supplier performance, discount
patterns, product associations, and potential business scenarios**.

**Analytical flow:**

`Raw Data → Data Preparation → Data Modeling → KPI Layer → Business Analysis → Insights → Decision Support`

## Business Objectives

The report is designed to answer questions such as:

-   How is overall commercial performance changing?
-   Which products contribute most to revenue and gross profit?
-   Where are selling prices deviating from standard retail prices?
-   Which products show inventory/sales gaps?
-   What products are being returned or remaining unsold?
-   How do suppliers contribute to purchasing activity and supplier
    balances?
-   How large are discounts and how dispersed are they?
-   Which products may have cross-selling or basket relationships?
-   What happens to revenue and gross profit under different business
    scenarios?

## Dashboard Structure

### 1. Executive Dashboard

Management-level overview of:

-   Total Revenue
-   Total Quantity
-   Average Price
-   Total Discount
-   Total Invoices
-   COGS
-   Gross Profit
-   Purchases
-   Sales
-   Balance Value
-   Sales Returns
-   Revenue and COGS trends
-   Revenue-to-profit bridge

**Purpose:** Provide a fast overview of business performance.

### 2. Product Analysis

Product-level commercial and profitability analysis covering:

-   Total Revenue
-   Total Quantity
-   Total Discount
-   Total Invoices
-   COGS
-   Gross Profit
-   Gross Profit %
-   Balance Value
-   Balance Quantity
-   Average Selling Price
-   Average Buy Price
-   Discount %
-   COGS %

**Purpose:** Identify high-performing, low-performing, profitable, and
problematic products.

### 3. Deviations Analysis

Exception-focused analysis covering:

-   Selling Price Deviation
-   Standard Retail Price
-   Actual Selling Price
-   Inventory Sales Quantity vs. Actual Sales Quantity
-   Unsold Products
-   Returned Products
-   Revenue trends
-   Product-level deviation analysis

**Purpose:** Detect commercial and operational exceptions that require
investigation.

### 4. Suppliers Analysis

Supplier-oriented analysis covering:

-   Purchases Value
-   Recorded Payments
-   Returns
-   Discounts
-   Supplier Balance
-   Standard Retail Price
-   Actual Selling Price
-   Selling Price Deviation
-   Purchases over time
-   Revenues over time
-   Supplier invoice values

The report respects the selected filter context. If no payment
transactions are recorded in a selected period, the payment KPI
correctly returns zero.

**Purpose:** Support supplier performance monitoring and purchasing
analysis.

### 5. Discount Analysis

Discount analytics using descriptive and statistical measures:

-   Sales Value
-   Discount Value
-   Mean
-   Median
-   Q1
-   Q3
-   Standard Deviation
-   Discount distribution
-   Discount over time
-   Revenue over time
-   Product/section-level discount relationships
-   Dispersion analysis

**Purpose:** Understand discount behavior and identify unusual patterns.

### 6. Market Basket Analysis

Explores product relationships and potential cross-selling opportunities
through:

-   Product sales ranking
-   Product quantity
-   Related/other product sales
-   Product relationship exploration

**Purpose:** Identify product relationships that can support
merchandising and cross-selling decisions.

> **Note:** The current presentation focuses on product association
> exploration. Formal association-rule metrics such as Support,
> Confidence, and Lift should only be interpreted if they are explicitly
> calculated in the underlying model.

### 7. What-If Analysis

Scenario analysis for:

-   Average Price
-   Quantity
-   Discount
-   COGS

Outputs include:

-   Sales If
-   Gross Profit If

**Purpose:** Move from historical reporting toward scenario-based
decision support.

## Time Intelligence

A major component of the report is dynamic time intelligence.

The growth logic changes according to the active filter context rather
than blindly displaying the same comparison everywhere.

The implementation uses concepts such as:

-   `IF`
-   `HASONEVALUE`
-   Month-over-Month (MoM)
-   Year-over-Year (YoY)

Conceptually:

-   **Single month context → MoM**
-   **Year-level context → YoY**

This helps avoid misleading comparisons caused by applying monthly
calculations to an annual filter context.

## Data Preparation & Quality

The project started from raw operational files that required preparation
before analysis.

Key challenges included:

-   Unstructured HTML source files
-   Different product naming conventions
-   Product-name standardization
-   Duplicate records
-   Cross-source reconciliation
-   Inconsistent source structures
-   Missing business dimensions in the available data

Workflow:

`Extraction → Cleaning → Standardization → Reconciliation → Modeling → Analysis`

Data quality validation was treated as an analytical step rather than
assuming that source data was automatically reliable.

## Analytical Layer

The Power BI solution uses business-oriented measures rather than
relying only on raw columns.

Examples include:

-   Revenue
-   COGS
-   Gross Profit
-   Gross Profit %
-   Revenue Growth
-   Quantity Growth
-   Sales Target
-   Selling Price Deviation
-   Discount Value
-   Discount %
-   Returns
-   Balance Value
-   Supplier Balance

## Business Analysis Framework

``` text
Business Problem
       ↓
Data Preparation
       ↓
Data Modeling
       ↓
KPI & Measure Development
       ↓
Exploratory Analysis
       ↓
Deviation Detection
       ↓
Scenario Analysis
       ↓
Business Insight
       ↓
Decision Support
```

## Technology Stack

  Technology                Role
  ------------------------- -------------------------------------------------------
  **Power BI**              Data modeling, DAX, analytics & dashboard development
  **DAX**                   Measures, KPIs & time intelligence
  **Power Query**           Data transformation and preparation
  **Python**                Data extraction, cleaning and reconciliation
  **HTML / Source Files**   Raw operational data sources

## Key Analytical Concepts

-   Business Intelligence
-   Business Analysis
-   Data Cleaning
-   Data Reconciliation
-   Data Modeling
-   KPI Design
-   DAX
-   Time Intelligence
-   MoM Analysis
-   YoY Analysis
-   Variance & Deviation Analysis
-   Profitability Analysis
-   Supplier Analysis
-   Product Analysis
-   Discount Analytics
-   Statistical Descriptive Analysis
-   Market Basket / Product Association Analysis
-   What-If Scenario Analysis
-   Decision Intelligence
-   Data Storytelling

## Navigation

``` text
Home
 ├── Executive Dashboard
 ├── Deviations Analysis
 ├── Suppliers Analysis
 ├── Products Analysis
 ├── Discount Analysis
 ├── Market Basket Analysis
 └── What-If Analysis
```

The Home page acts as the central navigation layer for the analytical
experience.

## Design Philosophy

The report follows a clean corporate visual language:

-   White background
-   Consistent blue primary identity
-   Clear KPI hierarchy
-   Consistent navigation
-   Interactive filters
-   Tooltip-based contextual details
-   Executive-first presentation

The goal is to make complex analysis accessible to business users and
decision-makers.

## Data Validation Philosophy

A dashboard should not be considered reliable simply because it looks
correct.

The project emphasizes:

1.  Source-data inspection
2.  Duplicate detection
3.  Cross-source reconciliation
4.  Product-name standardization
5.  Measure validation
6.  Filter-context validation
7.  Business-logic validation

> **A correct-looking dashboard is not necessarily a correct
> dashboard.**

## Limitations

The analysis is constrained by the information available in the source
data.

Examples include:

-   Limited customer-level information
-   Limited branch-level information
-   Limited payment transaction detail
-   Product naming inconsistencies in source files
-   Missing business dimensions that were not present in the original
    data

The dashboard should therefore be interpreted according to the available
data scope and should not be used to infer information that is not
represented in the underlying dataset.

## Project Value

This project demonstrates an end-to-end analytical mindset.

Not only:

> **How can I build a Power BI dashboard?**

But:

> **What business problem am I solving, what does the data tell me, and
> what decision can be made from it?**

The project combines **Business Analysis + Data Analysis + Financial
Thinking + Decision Intelligence** into one analytical solution.

## Recommended Repository Structure

``` text
COTTONIL-Business-Data-Analysis/
│
├── README.md
├── PowerBI/
│   └── COTTONIL_Business_Data_Analysis.pbix
├── Data/
│   ├── Raw/
│   ├── Processed/
│   └── Reconciliation/
├── Python/
│   └── Data_Preparation/
├── Screenshots/
│   ├── Home.png
│   ├── Executive_Dashboard.png
│   ├── Products.png
│   ├── Deviations.png
│   ├── Suppliers.png
│   ├── Discount.png
│   ├── Market_Basket.png
│   └── What_If.png
└── Documentation/
    └── Data_Dictionary.md
```

## Screenshots

Add report screenshots to the `Screenshots/` folder and reference them
in this README.

Example:

``` markdown
![Executive Dashboard](Screenshots/Executive_Dashboard.png)
```

Recommended screenshots:

-   Home Page
-   Executive Dashboard
-   Product Analysis
-   Deviations Analysis
-   Suppliers Analysis
-   Discount Analysis
-   Market Basket Analysis
-   What-If Analysis

## Author

**Hady Amr**\
**Business & Data Analyst**

> **Turning Business Data into Decisions**

Focus areas:

-   Business Analysis
-   Data Analysis
-   Financial Analysis
-   Business Intelligence
-   Decision Intelligence
-   Strategic Analysis

## Disclaimer

This repository is a portfolio/analytical project. The dashboard and
analysis are intended to demonstrate data analytics, business
intelligence, modeling, and decision-support capabilities.

The conclusions and calculations should be interpreted within the scope,
quality, completeness, and business definitions of the underlying
dataset.
