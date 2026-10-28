# Financial Performance Analysis

## Project Overview
This portfolio project uses Microsoft's sample financial workbook to explore sales, profitability, costs, discounts, and performance across products, countries, segments, and time. The report was built in Power BI with Power Query preparation, DAX measures, KPI cards, charts, and slicers for Year, Country, and Segment.

> **Dataset note:** This is a Microsoft sample dataset for demonstration. It is not a company's audited financial statements and should not be presented as verified real-business performance.

## Tools
- **Microsoft Excel:** inspected the workbook and structured the `FinancialData` table.
- **Power Query:** imported data and reviewed column types and blanks.
- **Power BI Desktop:** model, KPI cards, visuals, slicers, and report pages.
- **DAX:** calculated financial measures.
- **GitHub / Markdown:** project documentation.

## Dashboard Pages
1. **Financial Performance Overview** — overall KPIs, monthly sales and profit trend, profit by product, and sales by country.
2. **Profitability and Segment Analysis** — gross sales, average sales per record, profit per unit sold, discount rate, units sold, and comparisons across country, segment, and product.

## Dashboard Screenshots
Export screenshots from Power BI and save them using these filenames in a `screenshots/` folder in this repository.

### Financial Performance Overview
<img width="1427" height="806" alt="financial-performance-overview" src="https://github.com/user-attachments/assets/ee19c5f4-7e63-48b3-b533-c9845bd7fb77" />


### Profitability and Segment Analysis
<img width="1427" height="807" alt="profitability-segment-analysis" src="https://github.com/user-attachments/assets/58b03393-dc2e-4b7d-91c1-19aa225bfe6a" />



## Key Results
Figures are rounded as displayed in the current Power BI report.

| KPI | Reported value |
|---|---:|
| Total Sales | 118.73M |
| Total Profit | 16.89M |
| Total COGS | 101.83M |
| Total Discounts | 9.21M |
| Profit Margin | 14.23% |
| Total Gross Sales | 127.93M |
| Average Sales per Record | 169.61K |
| Profit per Unit Sold | $15.01 |
| Sales Discount Rate | 7.20% |
| Total Units Sold | 1.13M |

Values depend on the current filter state. Use full-precision values when reconciling measures; rounded figures may not reconcile exactly.

## Main DAX Measures
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

## How to Use
1. Open the `.pbix` file in Power BI Desktop.
2. Use the Year, Country, and Segment slicers to filter results.
3. Compare the KPI cards with the monthly trend and category breakdown charts.
4. See `key_findings.md` and `recommendations.md` for interpretation and suggested follow-up analysis.

## Limitations
- The dataset is a sample, not audited financial data.
- `Average Sales per Record` is not necessarily average order value; that depends on what each row represents.
- A visual relationship between discounts and profit does not prove causation.
  

## Repository Structure
```text
Financial-Performance-Analysis/
├── README.md
├── data_dictionary.md
├── key_findings.md
├── recommendations.md
├── data_quality_report.md
└── screenshots/
    ├── financial-performance-overview.png
    └── profitability-segment-analysis.png
```

