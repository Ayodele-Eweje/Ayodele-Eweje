# Power BI Build Guide

## 1. Data model
Load `../data/sales_performance_sample.csv` as table `Sales`. Create the Date table using the DAX expression in `DAX_Measures.dax`, mark it as a date table, and relate Date[Date] to Sales[Date].

## 2. Page 1 — Executive Overview
- Five KPI cards: Total Revenue, Gross Profit, Gross Margin %, Total Orders, Average Order Value.
- Line chart: Date[Year Month] on axis; Total Revenue and Gross Profit as values.
- Horizontal bar: Region by Total Revenue, descending.
- Column chart: Product by Total Revenue.
- Slicers: Year, Region, Channel.

## 3. Page 2 — Commercial Performance
- Clustered bar: Product with Total Revenue and Gross Profit.
- Donut: Channel by Total Revenue.
- Bar: Customer Segment by Total Revenue.
- Matrix: Region rows, Product columns; values Total Revenue, Gross Profit, Gross Margin %.
- Add conditional formatting to gross margin.

## 4. Page 3 — Trend & Growth
- Line chart: Year Month against Total Revenue.
- Line chart: Year Month against Gross Profit.
- Cards: Revenue YoY %, Profit YoY %.
- Slicers: Year, Region, Product, Channel.

## 5. Formatting
- Apply theme.json.
- Use consistent currency formatting and display percentages to one decimal place.
- Sort Year Month by a numeric YearMonth sort column if needed; create it as YEAR([Date])*100+MONTH([Date]) in the Date table.
- Add descriptive titles, alt text and clear tooltips.
- Ensure all slicers interact as intended.

## 6. Validation
- Confirm row count is 648 and OrderID is unique.
- Check Gross Profit = Revenue − Cost.
- Check Gross Margin % = Gross Profit / Revenue.
- Confirm Date table covers the full sales date range.
- Test all slicers and cross-highlighting.
