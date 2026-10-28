
This dictionary describes the fields in the `Financials` worksheet of Microsoft's sample financial workbook. Confirm source definitions and types before using the values for business decisions.

| Column | Suggested type | Definition |
|---|---|---|
| `Segment` | Text | Segment category used to group financial performance. |
| `Country` | Text | Country associated with the financial record. |
| `Product` | Text | Product category/name used for product comparisons. |
| `Discount Band` | Text | Categorical band describing the discount level. |
| `Units Sold` | Whole number or decimal | Quantity of units sold in the record. |
| `Manufacturing Price` | Decimal/currency | Manufacturing price or cost per unit as defined by the source. Confirm its business meaning before interpreting it as unit cost. |
| `Sale Price` | Decimal/currency | Sale price per unit as defined by the source workbook. |
| `Gross Sales` | Decimal/currency | Sales amount before discounts, according to the source. |
| `Discounts` | Decimal/currency | Discount amount applied to the record. Zero may be a valid value. |
| `Sales` | Decimal/currency | Sales amount after discounts, according to the source. |
| `COGS` | Decimal/currency | Cost of goods sold associated with the record. |
| `Profit` | Decimal/currency | Profit value provided in the dataset; validate the source definition before accounting interpretation. |
| `Date` | Date | Date associated with the financial record. |
| `Month Number` | Whole number | Numeric month, usually 1–12; use it to sort month names chronologically. |
| `Month Name` | Text | Month label for visuals; sort by `Month Number` in Power BI. |
| `Year` | Whole number | Year associated with the record, used for filtering and comparisons. |

## Notes
- The workbook may not explicitly establish a currency symbol in every context. 
- `Profit Margin %`, `Profit per Unit Sold`, and `Sales Discount Rate` are calculated measures, not source columns.
- `Average Sales per Record` averages `Sales` over rows; it is not necessarily average order value or average customer spend.
- The dataset is for sample/reporting demonstration and is not audited company data.
