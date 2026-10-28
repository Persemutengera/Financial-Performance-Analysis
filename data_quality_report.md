# Data Quality Report

## 1. Purpose
This document records the preparation steps reported during the Power BI project and provides a checklist for validation. It does not claim the dataset is fully certified until the checks below are completed.

## 2. Source and Structure
- **Source:** Microsoft's sample financial workbook.
- **Worksheet:** `Financials`.
- **Power BI table:** `FinancialData`.
- **Expected columns (16):** Segment, Country, Product, Discount Band, Units Sold, Manufacturing Price, Sale Price, Gross Sales, Discounts, Sales, COGS, Profit, Date, Month Number, Month Name, Year.

## 3. Preparation Steps Reported
1. Inspected the `Financials` worksheet.
2. Converted the source range into an Excel table named `FinancialData`.
3. Imported the table into Power BI through Power Query.
4. Reviewed column names and data types.
5. Checked for blanks/nulls during preparation. The observed values appeared as zeros rather than nulls; zeros were retained because zero discounts or other numeric values may be valid.
6. Loaded the table into the Power BI model.
7. Created DAX measures for sales, profit, COGS, discounts, profit margin, gross sales, average sales per record, profit per unit sold, sales discount rate, and units sold.
8. Created report visuals and slicers for Year, Country, and Segment.

> **Evidence note:** These steps reflect the project progress reported so far. The checklist below should be marked complete only after each check is actually performed.

## 4. Validation Checklist
- [ ] Confirm the table has the expected 16 columns.
- [ ] Confirm row count against the source workbook.
- [ ] Confirm `Date` is Date type; `Year` and `Month Number` are whole numbers.
- [ ] Confirm `Units Sold` is numeric.
- [ ] Confirm Manufacturing Price, Sale Price, Gross Sales, Discounts, Sales, COGS, and Profit are numeric.
- [ ] Check for nulls and blank strings in categorical fields.
- [ ] Check for nulls in date and numeric fields.
- [ ] Verify that zero values are legitimate rather than missing values encoded as zero.
- [ ] Check negative values and investigate them rather than automatically deleting them.
- [ ] Check for duplicate rows using appropriate business keys or an all-column comparison.
- [ ] Sort `Month Name` by `Month Number` in Power BI.
- [ ] Reconcile KPI totals against the source workbook using full-precision values.
- [ ] Test the report with Year, Country, and Segment slicers.

## 5. KPI Values Supplied for Reconciliation

| KPI | Reported value |
|---|---:|
| Total Sales | 118.73M |
| Total Profit | 16.89M |
| Total COGS | 101.83M |
| Total Discounts | 9.21M |
| Total Gross Sales | 127.93M |
| Total Units Sold | 1.13M |
| Profit Margin | 14.23% |
| Sales Discount Rate | 7.20% |
| Average Sales per Record | 169.61K |
| Profit per Unit Sold | $15.01 |

Displayed values are rounded. Reconcile using full-precision values. If gross sales minus discounts does not align with sales, investigate the source definitions, filters, and measure calculations.

## 6. DAX Definitions to Verify

```DAX
Total Sales = SUM('FinancialData'[Sales])
Total Profit = SUM('FinancialData'[Profit])
Total COGS = SUM('FinancialData'[COGS])
Total Discounts = SUM('FinancialData'[Discounts])
Total Gross Sales = SUM('FinancialData'[Gross Sales])
Total Units Sold = SUM('FinancialData'[Units Sold])
Profit Margin % = DIVIDE([Total Profit], [Total Sales], 0)
Average Sales per Record = AVERAGE('FinancialData'[Sales])
Profit per Unit Sold = DIVIDE([Total Profit], [Total Units Sold], 0)
Sales Discount Rate = DIVIDE([Total Discounts], [Total Gross Sales], 0)
```

## 7. Considerations
- **Zero vs missing:** A zero may be valid. Do not replace zeros with nulls without evidence.
- **Currency:** Confirm the intended currency and display convention.
- **Latest date:** The maximum `Date` shows the latest date represented in the dataset, not the last refresh time.
- **Average Sales per Record:** Do not call this average order value unless each row is confirmed to represent an order.
- **Sample data:** The workbook is for demonstration and is not verified audited company data.

## 8. Overall Assessment
The data has been imported and used for an initial interactive report. Describe data quality as **initially reviewed** until the checklist and source-to-report reconciliation are completed and documented.
