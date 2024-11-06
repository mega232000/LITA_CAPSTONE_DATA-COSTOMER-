# LITA_CAPSTONE_DATA-COSTOMER-
### Project Title : Costumer Data Analysis
### Project Overview
This Project Involves analyzing customer data for a subscription service to identify segments and trends ,it aims at understanding customer behaviour ,tracking subscription types and identifying key trends in cancellations and renewals, for better decison making

### Tools Used:
- Excel
- SQL
- Power BI
  
### Project Structure:
- Excel: Contains Excel files for data exploration and calculation.
- SQL: Contains SQL queries for data analysis.
- Power BI: Contains Power BI dashboard files(Data and Visualization).
- Data: Contains sales data(XLSX & CSV) files.

### Excel Files:
- Sales Exploration: Initial data exploration using pivot tables.
- Sales Metrics: Calculations for average sales per product and total revenue by region.

### SQL Queries:
- Sales_queries: Queries for total sales by product category, number of sales transactions by region, highest-selling product, total revenue per product, monthly sales totals, top 5 customers, and percentage of total sales by region.

### Power BI Dashboards:
- Sales Overview: Dashboard visualizing sales overview, top-performing products, and regional breakdowns.

### Data Files:
- Sales_data: Sales data used for analysis.

### Instructions Given;
1. Clone the repository.
2. Load the costumer data into your SQL Server environment.
3. Run SQL queries to extract insights.
4. Open Excel files to view calculations and pivot tables.
5. Open Power BI dashboard files to visualize insights.

### SQL Queries Documentation:
```SQL
SELECT * FROM CustomerData
```

-- 1. retrieve the total number of customers from each region.---
```SQL

SELECT Region, COUNT(CustomerID) AS TotalCustomers
FROM CustomerData
GROUP BY Region;
```

-- 2. find the most popular subscription type by the number of customers.--
```SQL
SELECT SubscriptionType, COUNT(CustomerID) AS MostPopularSubscriptionType
FROM CustomerData
GROUP BY SubscriptionType
ORDER BY MostPopularSubscriptionType DESC;
```
``` SQL
SELECT Top (1) SubscriptionType, COUNT(CustomerID) AS MostPopularSubscriptionType
FROM CustomerData
GROUP BY SubscriptionType
ORDER BY MostPopularSubscriptionType DESC
```
-- 3. find customers who canceled their subscription within 6 months.--
```SQL
SELECT CustomerName, SubscriptionStart, SubscriptionEnd
FROM CustomerData
WHERE Canceled = 'TRUE';
```



-- 4. calculate the average subscription duration for all customers.--
```SQL
SELECT AVG(SubscritionDuration) AS AverageSubscriptionDuration
FROM CustomerData;
```

-- 5. find customers with subscriptions longer than 12 months.--
```SQL
SELECT *
FROM CustomerData
WHERE (SubscritionDuration)) > 365;
```


-- 6. calculate total revenue by subscription type.--
```SQL
SELECT SubscriptionType, SUM(Revenue) AS TotalRevenue
FROM CustomerData
GROUP BY SubscriptionType
ORDER BY TotalRevenue DESC
```
 
-- 7. find the top 3 regions by subscription cancellations.
```SQL
SELECT  Top (3) Region, COUNT(CustomerID) AS Cancellations
FROM CustomerData WHERE Canceled = 'TRUE'
GROUP BY Region
ORDER BY Cancellations DESC;
```


-- 8. find the total number of active and canceled subscriptions.
SELECT 
```SQL
    SUM(CASE WHEN Canceled = 'TRUE' THEN 1 ELSE 0 END) AS TotalCanceled,
    SUM(CASE WHEN Canceled = 'FALSE' THEN 1 ELSE 0 END) AS TotalActive
FROM CustomerData;
```
### visualization

![costumer data one](https://github.com/user-attachments/assets/684645da-51cd-48c9-b0d7-2501c9ec034d)

![costumer file 2](https://github.com/user-attachments/assets/d505ae06-420a-45e5-b6a0-5060c4512011)

![costumer Data](https://github.com/user-attachments/assets/95aff3ca-1f43-45bb-b7c8-e57317b56592)

![costumer power bi](https://github.com/user-attachments/assets/5c75c303-8b66-49f1-acba-40e327179e2a)
