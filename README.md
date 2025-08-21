# ShopNest-Store-Power-BI-Capstone


## Project Overview
This Power BI project analyzes sales, customer, product, and territory datasets to generate actionable business insights for "Shop Next Door".  
The focus is on sales performance, order delays, payment methods, product ratings, and seasonal trends.

*Datasets Used:*
- sales.csv
- customer.csv
- product.csv
- territory.csv

## Steps Followed

### Step 1: Data Collection
- Imported CSV files from the Datasets/ folder into Power BI.

### Step 2: Data Cleaning & Transformation
- Removed duplicates and handled missing values.
- Created relationships:
  ### Step 2: Data Cleaning & Transformation
- Removed duplicates and handled missing values.
- Created relationships between tables in the Model view:
  - CustomerID → orders
  - Customer ZIP Code → geolocation
  - OrderID → order_items
  - OrderID → order_payment
  - OrderID → order_reviews
  - ProductID → order_items
  - SellerID → order_items
  - Product Category Name → product_category
 
    
### Step 3: Data Analysis & Visualization
- Created DAX measures for revenue and sales:
```DAX
-- Total Sales
Total Sales = SUM(order_items[Price])

-- Total Freight
Total Freight = SUM(order_items[Freight Value])

-- Average Order Value
Average Order Value = AVERAGE(order_items[Price])

-- Total Orders
Total Orders = DISTINCTCOUNT(orders[Order ID])

-- Delayed Orders
Delayed Orders = 
CALCULATE(
    COUNTROWS(orders),
    orders[Order Status] = "delivered late")

-- On-Time Orders
OnTime Orders = 
CALCULATE(
    COUNTROWS(orders),
    orders[Order Status] = "delivered on time")

-- Total Customers
Total Customers = DISTINCTCOUNT(customers[Customer ID])

-- Total Products Sold
Total Products Sold = SUM(order_items[Order Item ID])
```

#### *Analysis Performed:*
1. *Top Categories by Total Prices*  
2. *Delayed Order Analysis*  
3. *Monthly Comparison of Delayed and On-Time Orders*  
4. *Payment Method Analysis*  
5. *Product Rating Analysis*  
6. *Statewide Sales Analysis*  
7. *Seasonal Sales Patterns*  
8. *Revenue Analysis*











