# rohinipatil_2511898_part1_data_cleaning
# Business Data Cleaning, Validation & Excel Reporting

## Repository Information

**Repository Name:** rohinipatil_2511898_part1_data_cleaning

**Student Name:** Rohini Patil

**Student ID:** 2511898



# Problem Summary

A retail company exported order-level sales data from multiple internal systems. The dataset contained inconsistencies such as duplicate records, missing values, invalid discounts, inconsistent text formatting, and date-related issues.

The objective was to clean, validate, and transform the dataset into an analysis-ready format while documenting all quality issues and generating business summary reports.


# Dataset Description

The dataset contains retail order information including:

* Order ID
* Order Date
* Ship Date
* Customer Information
* Segment
* Region
* State
* City
* Category
* Sub-Category
* Product Name
* Ship Mode
* Quantity
* Unit Price
* Discount
* Sales
* Cost
* Profit
* Payment Status
* Order Status


# Tools Used

* Microsoft Excel
* Pivot Tables
* Excel Functions

  * TRIM()
  * PROPER()
  * SUBSTITUTE()
  * IF()
  * YEAR()
  * TEXT()
  * DATEDIF()
* GitHub



# Cleaning Steps Performed

## Text Cleaning

The following fields were standardized:

* customer_name
* segment
* region
* state
* city
* category
* sub_category
* ship_mode
* payment_status
* order_status

Actions performed:

* Removed leading spaces
* Removed trailing spaces
* Removed extra spaces
* Standardized capitalization
* Corrected inconsistent values


## Date Cleaning

The following fields were validated:

* order_date
* ship_date

Actions performed:

* Standardized date formats
* Identified missing dates
* Identified invalid dates
* Flagged ship dates earlier than order dates


## Duplicate Handling

* Exact duplicate rows identified and removed.
* Duplicate Order IDs identified.
* Conflicting duplicate records retained and flagged for review.

---

## Missing Value Handling

* Missing Region values replaced with "Unknown".
* Missing Ship Mode values replaced with "Unknown".
* Missing Discount values treated as 0 where applicable.


# Business Rules Applied

1. Missing Region → Unknown
2. Missing Ship Mode → Unknown
3. Missing Discount → 0 when valid
4. Negative Discount → Invalid
5. Discount Above 50% → Invalid
6. Cancelled Orders excluded from completed sales reporting
7. Failed Payments excluded from completed sales reporting
8. Refunded Orders summarized separately
9. Ship Date earlier than Order Date flagged as Invalid



# Calculated Columns Created

* cleaned_discount
* calculated_sales
* calculated_profit
* profit_margin
* shipping_delay_days
* order_month
* order_year
* data_quality_flag


# Summary of Data Quality Issues Found

| Issue                    | Status                   |
| ------------------------ | ------------------------ |
| Missing Values           | Identified and handled   |
| Duplicate Records        | Identified and processed |
| Invalid Discounts        | Flagged                  |
| Date Issues              | Flagged                  |
| Invalid Shipping Records | Flagged                  |
| Data Quality Flags       | Applied                  |


# Pivot Reports Created

1. Sales and Profit by Region
2. Sales and Profit by Category and Sub-Category
3. Order Count by Ship Mode
4. Profit Margin by Customer Segment
5. Refunded, Cancelled and Failed Orders by Region
6. Monthly Sales Trend

# Key Business Insights

* South region generated the highest sales.
* Office Supplies contributed significantly to total revenue.
* Standard and Second Class shipping modes were used most frequently.
* Some records contained invalid discounts requiring business review.
* Refunded and cancelled orders impacted overall profitability.
* Missing region and ship mode values were successfully identified and tracked.


# Assumptions

* Maximum valid discount allowed = 50%.
* Unknown values were retained for reporting transparency.
* Duplicate Order IDs require manual business review.
* Missing discounts were treated as zero only when other sales fields were valid.


# Limitations

* Source system errors cannot be independently verified.
* Conflicting duplicate records require manual investigation.
* Business decisions based on flagged records may require additional validation.


# Repository Structure

```text
part1_data_cleaning/
├── data/
│   ├── raw_orders.xlsx
│   └── cleaned_orders.xlsx
├── outputs/
│   ├── data_quality_report.xlsx
│   ├── pivot_summary.xlsx
│   └── cleaning_log.md
├── screenshots/
│   ├── raw_data_preview.png
│   ├── cleaned_data_preview.png
│   ├── pivot_summary_1.png
│   └── pivot_summary_2.png
└── README.md
```

# Screenshots Included

* raw_data_preview.png
* cleaned_data_preview.png
* pivot_summary_1.png
* pivot_summary_2.png


# Final Outcome

The dataset was successfully cleaned, validated, documented, and transformed into an analysis-ready format. Data quality issues were identified and reported, business rules were applied, and summary reports were generated to support business decision-making.
