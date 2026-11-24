# Business Performance Dashboard | Power BI

A portfolio project demonstrating how to turn operational sales data into business performance insights using Power BI.

> **Data note:** This project uses entirely synthetic sample data generated for demonstration. It does not represent actual results from any employer or client.

## Business questions
- How are revenue, gross profit and gross margin trending?
- Which regions, products, channels and customer segments contribute most?
- How is performance changing year over year?
- What is the average order value and volume of units sold?

## Dashboard layout
1. **Executive Overview:** Revenue, gross profit, gross margin, orders, revenue trend and revenue by region.
2. **Commercial Performance:** Product, channel and customer-segment contribution; revenue and margin comparisons.
3. **Trend & Growth:** Monthly revenue/profit trend, year-over-year performance and slicers for year, region, product and channel.

## Files
- `data/sales_performance_sample.csv` — 648 synthetic order records across 2024–2026.
- `powerbi/DAX_Measures.dax` — core measures and Date table expression.
- `powerbi/theme.json` — report theme.
- `powerbi/BUILD_GUIDE.md` — steps to assemble the report in Power BI Desktop.

## Build in Power BI Desktop
1. Open Power BI Desktop.
2. Select **Get data → Text/CSV** and import `data/sales_performance_sample.csv`.
3. Rename the query/table to **Sales**. Set Date to Date, Units to Whole Number, and Revenue/Cost to Whole Number or Fixed Decimal.
4. Open **Modeling → New table** and paste the Date table expression from `powerbi/DAX_Measures.dax`.
5. Create the relationship `Date[Date]` (one) to `Sales[Date]` (many); mark Date as the date table.
6. Add the measures from the DAX file.
7. Import `powerbi/theme.json` from **View → Themes → Browse for themes**.
8. Build visuals using the layout in the build guide.

## Suggested visuals
- KPI cards: Total Revenue, Gross Profit, Gross Margin %, Total Orders, Average Order Value.
- Line chart: monthly Total Revenue and Gross Profit.
- Bar chart: Total Revenue by Region.
- Clustered bar: Total Revenue and Gross Profit by Product.
- Donut: Revenue by Channel.
- Matrix: Region × Product with Revenue, Gross Profit and Gross Margin %.
- Slicers: Year, Region, Product, Channel and Customer Segment.

## Analytical definitions
- **Gross Profit** = Revenue − Cost.
- **Gross Margin %** = Gross Profit ÷ Revenue.
- **Average Order Value** = Revenue ÷ distinct order count.
- **Revenue YoY %** compares current-period revenue with the equivalent prior-year period.

## Portfolio integrity
This is a demonstration project. Replace the synthetic CSV with an authorised, anonymised business dataset before using it for real operational decisions. Do not present sample figures as actual company performance.
