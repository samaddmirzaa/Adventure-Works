**AdventureWorks Power BI Project**
The dataset is a folder of raw CSV files (transactions/sales, returns, products, customers, and territories).  

Interactive Power BI report built on the AdventureWorks dataset to monitor **sales performance, profitability, returns, products, and customers**.

The report includes KPI tracking (Orders, Revenue, Profit, Returns, Return Rate), geographic insights, product performance with targets, and customer segmentation.


## Report Pages

### 1) Executive Dashboard
High-level KPI dashboard with:
- KPI cards: **ORDERS**, **REVENUE**, **PROFIT**, **TOTAL RETURNS**, **RETURN RATE**
- Month-over-month KPI visuals (current vs previous month)
- **Revenue Trend** line chart
- **Orders by Category** bar chart
- **Top 10 Products** table including Orders/Revenue and Return %

Interactive filters on this page:
- **Year** slicer
- **Country** slicer

### 2) Map
Geographic view of performance:
- Map visual showing **Total Orders by Country**
- **Continent** slicer for regional filtering

### 3) Product Detail
Product performance and targets:
- Gauges for:
  - **Monthly Orders vs Target**
  - **Monthly Revenue vs Target**
  - **Monthly Profit vs Target**
- **Profit Trend** line chart (includes profit comparison using a what-if adjustment)
- **Returns Trend** area chart (Orders vs Returns)
- Slicers:
  - **Price Adjustment (%)** (what-if parameter)
  - **Product Metric Selection** (field parameter / metric selector)

### 4) Customer Detail
Customer KPIs and segmentation:
- KPI cards:
  - **Unique Customers**
  - **Average Revenue per Customer**
- **Customers Trend** line chart
- Donut charts:
  - **Orders by Education Level**
  - **Orders by Occupation**
- Table:
  - **Top 100 Customers** (Customer Key, Full Name, Orders, Revenue)
- **Year** slicer

### 5) Category Tooltip
Tooltip page (used for hover/drill experience):
- Multi-row summary (Revenue/Profit/Orders/Returns/Return Rate)
- **Weekly Orders** trend


## Key Measures Used in Visuals 
These measures are referenced directly by visuals in the report:
- `Measure Table[Total Orders]`
- `Measure Table[Total Revenue]`
- `Measure Table[Total Profit]`
- `Measure Table[Total Returns]`
- `Measure Table[Return Rate]`
- `Measure Table[Previous Month Orders]`
- `Measure Table[Previous Month Revenue]`
- `Measure Table[Previous Month Returns]`
- Targets:
  - `Measure Table[Order Target]`
  - `Measure Table[Revenue Target]`
  - `Measure Table[Profit Target]`
- What-if / adjusted metric:
  - `Measure Table[Adjusted Profit]`
- Customer metrics:
  - `Measure Table[Total Customers]`
  - `Measure Table[Average Revenue per Customer]`

## Data Model (Tables)
The model follows a star-schema pattern with Sales/Returns fact tables and standard dimensions:

**Core tables**
- `Sales Data` (fact)
- `Returns Data` (fact)
- `Calendar Lookup` (date dimension)
- `Customer Lookup` (customer dimension)
- `Product Lookup` + `Product Subcategories Lookup` + `Product Categories Lookup` (product dimensions)
- `Territory Lookup` (geography dimension)

**Supporting tables**
- `Rolling Calendar` (time intelligence support)
- `Measure Table` (centralized DAX measures)

**Parameters / selectors**
- `Price Adjustment (%)` (what-if parameter)
- `Product Metric Selection` (field parameter / metric selector)
- `Customer Metric Selection` (field parameter / metric selector)


