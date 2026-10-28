# Key Findings

## Scope
The following findings use the aggregate KPI values provided from the current Power BI report. Figures are rounded as displayed. Product-, country-, segment-, and month-specific findings should be added only after checking the corresponding visuals and filters.

## Evidence-Based Findings
1. **Total Sales are 118.73M.** This is the reported sales baseline for the current filter state.
2. **Total Gross Sales are 127.93M and Total Discounts are 9.21M.** The reported Sales Discount Rate is 7.20%, calculated as discounts divided by gross sales.
3. **Total Profit is 16.89M and Profit Margin is 14.23%.** These measures summarise reported profitability using the current DAX definitions.
4. **Total COGS are 101.83M.** Costs should be monitored alongside sales and profit rather than assessed in isolation.
5. **Total Units Sold are 1.13M.** Volume is useful context but does not, by itself, show which products are most profitable.
6. **Profit per Unit Sold is $15.01.** This is total profit divided by total units sold; confirm currency before external presentation.
7. **Average Sales per Record are 169.61K.** This is the average of the `Sales` field across rows, not necessarily average order value.

## Interpretation and Caveats
- The aggregate 7.20% discount rate may conceal differences across products, countries, segments, and periods.
- The 14.23% overall profit margin may conceal stronger and weaker individual categories.
- Use full-precision values when reconciling gross sales, discounts, and sales. Rounded KPI values may not reconcile exactly.
- A chart showing discounts and profit can indicate an association but cannot prove discounts caused a change in profit.
- The source is a Microsoft sample workbook, not audited financial statements.

## Complete After Checking the Charts
- Highest-profit product: **Paseo**
- Highest-sales country: **United States and Canada**
- Highest-sales segment: **Government**
- Strongest/weakest month by sales or profit: **September 2013 is weakest month by sales and November 2014 is the waekest month by Profit**
- Notable discount/profit pattern: **Germany had the lowest rate of sales discont 5.68%**
