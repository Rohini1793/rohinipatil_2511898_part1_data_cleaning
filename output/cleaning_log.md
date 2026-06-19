# Data Cleaning Log

## Project

Business Data Cleaning, Validation and Excel Reporting

Repository:
rohinipatil_2511898_part1_data_cleaning

---

## Issues Found

### Text Formatting Issues

The following fields contained inconsistent formatting:

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

Issues identified:

* Leading spaces
* Trailing spaces
* Multiple spaces
* Inconsistent capitalization
* Inconsistent category naming

---

## Text Cleaning Actions

Applied:

* TRIM()
* PROPER()
* SUBSTITUTE()
* Find and Replace

Actions performed:

* Removed extra spaces
* Standardized capitalization
* Corrected inconsistent values
* Filled missing Region values with "Unknown"
* Filled missing Ship Mode values with "Unknown"

---

## Date Cleaning and Validation

Fields cleaned:

* order_date
* ship_date

Actions performed:

* Standardized dates into a consistent format
* Identified missing dates
* Identified invalid dates
* Identified ship dates earlier than order dates

New column created:

shipping_delay_days

Formula:

ship_date - order_date

Validation Rules:

* Missing dates flagged
* Invalid dates flagged
* Ship date before order date flagged as Invalid

---

## Duplicate Handling

Exact Duplicate Rows Found: 20

Duplicate Order IDs Found: 32

Actions Performed:

* Exact duplicate records removed
* Duplicate Order IDs retained
* Duplicate Order IDs flagged for review
* Conflicting records not deleted

---

## Missing Values

| Field     | Action                   |
| --------- | ------------------------ |
| Region    | Filled with Unknown      |
| Ship Mode | Filled with Unknown      |
| Discount  | Filled with 0 when valid |

---

## Discount Validation

Issues Found:

* Negative Discounts: 16
* Discounts Above 50%: 7

Actions Performed:

* Negative discounts flagged as Invalid
* Discounts above threshold flagged as Invalid

---

## Business Rules Applied

1. Missing Region → Unknown
2. Missing Ship Mode → Unknown
3. Missing Discount → 0 when valid
4. Negative Discount → Invalid
5. Discount Above 50% → Invalid
6. Cancelled Orders Excluded From Sales Summary
7. Failed Payments Excluded From Sales Summary
8. Refunded Orders Summarized Separately
9. Ship Date Earlier Than Order Date → Invalid

---

## Calculated Columns Created

* cleaned_discount
* shipping_delay_days
* order_month
* order_year
* data_quality_flag

---

## Records Removed

20 exact duplicate records removed.

---

## Records Flagged

* 32 duplicate order IDs
* 16 negative discount records
* 7 excessive discount records
* 2 invalid shipping records

---

## Assumptions

* Maximum allowed discount = 50%
* Unknown values retained for reporting transparency
* Duplicate Order IDs require manual review

---

## Limitations

* Duplicate order conflicts require manual investigation.
* Source-system errors cannot be fully verified.
* Some business rules depend on external validation.

---

## Final Status

Dataset cleaned, validated, documented, and prepared for business reporting and pivot analysis.
