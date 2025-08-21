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
Total Sales = SUM(sales[OrderQuantity] * sales[ProductPrice])
Average Sales per Customer = AVERAGE(sales[OrderQuantity] * sales[ProductPrice])
Delayed Orders = CALCULATE(COUNTROWS(sales), sales[DeliveryStatus] = "Delayed")
OnTime Orders = CALCULATE(COUNTROWS(sales), sales[DeliveryStatus] = "On-Time")
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















