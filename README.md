**AdventureWorks Power BI Project**
The dataset is a folder of raw CSV files (transactions/sales, returns, products, customers, and territories).  

Interactive Power BI report built on the AdventureWorks dataset to monitor **sales performance, profitability, returns, products, and customers**.

The report includes KPI tracking (Orders, Revenue, Profit, Returns, Return Rate), geographic insights, product performance with targets, and customer segmentation.


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


