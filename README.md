# Task 3: Power BI Dashboard Design

## Project Title
Amazon Sales Dashboard - Power BI Business Analysis

## Objective
The objective of this project is to design an interactive Power BI dashboard for business stakeholders. The dashboard analyzes sales performance, customer behavior, product performance, regional performance, order status, and growth opportunities.

## Dataset
Dataset used: `Amazon.csv`

The dataset contains 100,000 sales orders with the following columns:

- OrderID
- OrderDate
- CustomerID
- CustomerName
- ProductID
- ProductName
- Category
- Brand
- Quantity
- UnitPrice
- Discount
- Tax
- ShippingCost
- TotalAmount
- PaymentMethod
- OrderStatus
- City
- State
- Country
- SellerID

## Dataset Summary
- Total rows: 100,000
- Date range: 2020-01-01 to 2024-12-29
- Unique orders: 100,000
- Unique customers: 43,233
- Unique products: 50
- Total sales: 91.83M
- Total quantity sold: 300,140
- Average order value: 918.26

## Tools Used
- Power BI Desktop
- Microsoft PowerPoint
- GitHub

## Key KPIs
- Total Sales
- Total Orders
- Total Quantity Sold
- Average Order Value
- Total Customers
- Total Products
- Estimated Profit
- Estimated Profit Margin
- Return Rate
- Cancellation Rate
- Year-over-Year Sales Growth

## Power BI Dashboard Pages

### 1. Executive Overview
This page provides a high-level business summary with KPI cards, sales trend, category performance, and order status breakdown.

### 2. Sales & Profit Trends
This page analyzes monthly and yearly sales trends, estimated profit trends, average order value, and growth percentage.

### 3. Product & Category Analysis
This page shows top products, top categories, product quantity sold, sales by brand, and discount impact.

### 4. Customer Analysis
This page highlights top customers, customer count, repeat purchase opportunities, and customer contribution to revenue.

### 5. Region Analysis
This page analyzes sales by country, state, and city using maps, bar charts, and regional ranking tables.

### 6. Business Recommendations
This page summarizes key findings and recommended business actions.

## Important DAX Measures

```DAX
Total Sales = SUM('Amazon'[TotalAmount])

Total Orders = DISTINCTCOUNT('Amazon'[OrderID])

Total Quantity = SUM('Amazon'[Quantity])

Average Order Value = DIVIDE([Total Sales], [Total Orders])

Total Customers = DISTINCTCOUNT('Amazon'[CustomerID])

Total Products = DISTINCTCOUNT('Amazon'[ProductID])

Total Shipping Cost = SUM('Amazon'[ShippingCost])

Total Tax = SUM('Amazon'[Tax])

Estimated Cost = SUMX('Amazon', 'Amazon'[UnitPrice] * 'Amazon'[Quantity] * 0.70)

Estimated Profit = [Total Sales] - [Estimated Cost] - [Total Shipping Cost]

Estimated Profit Margin % = DIVIDE([Estimated Profit], [Total Sales])

Returned Orders = CALCULATE([Total Orders], 'Amazon'[OrderStatus] = "Returned")

Cancelled Orders = CALCULATE([Total Orders], 'Amazon'[OrderStatus] = "Cancelled")

Return Rate % = DIVIDE([Returned Orders], [Total Orders])

Cancellation Rate % = DIVIDE([Cancelled Orders], [Total Orders])

Sales Previous Year =
CALCULATE(
    [Total Sales],
    SAMEPERIODLASTYEAR('Amazon'[OrderDate])
)

Sales Growth % =
DIVIDE([Total Sales] - [Sales Previous Year], [Sales Previous Year])
```

Note: The dataset does not include product cost, so profit is estimated using an assumed cost rate of 70% of gross item value. If actual cost data is available, replace the estimated cost formula with actual cost.

## Dashboard Features
- KPI cards for executive summary
- Date slicer for time-based filtering
- Country, state, city, category, brand, payment method, and order status slicers
- Line charts for sales and estimated profit trends
- Bar charts for category, product, customer, and region performance
- Map visual for geographical analysis
- Matrix/table visual for detailed business drilldown
- Consistent professional color theme

## Key Insights
- Total sales are approximately 91.83M across 100,000 orders.
- Sales are available from 2020 to 2024.
- Electronics is the highest sales category, followed by Sports & Outdoors and Books.
- United States contributes the highest sales among countries.
- Delivered orders form the majority of order status.
- Memory Card 128GB, LED Desk Lamp, and Mechanical Keyboard are among the top products by sales.
- Top customers such as Pooja Kapoor and Vihaan Singh contribute significant revenue.

## Business Recommendations
- Focus marketing campaigns on high-performing categories such as Electronics and Sports & Outdoors.
- Improve inventory planning for top-selling products.
- Monitor returned and cancelled orders to reduce revenue leakage.
- Study regional performance and prioritize high-sales countries and cities.
- Use customer segmentation to target high-value customers with loyalty offers.
- Track monthly and yearly sales growth to identify seasonal patterns.
- Add actual cost data in the future to calculate accurate profit and margin.

## Final Outcome
This Power BI dashboard helps business stakeholders monitor sales performance, identify growth opportunities, evaluate regional performance, track top customers and products, and make data-driven business decisions.

