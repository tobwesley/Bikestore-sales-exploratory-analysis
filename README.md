# Bikestore-sales-exploratory-analysis
Data exploration of a Bike store sales data set using Microsoft SQL.

SELECT *
FROM [dbo].[Data$]

--What are the top 5 categories with the highest total unit sold?
SELECT TOP 5 [category_name], SUM([total_units]) AS Total_unit_sold
FROM dbo.Data$
GROUP BY [category_name]
ORDER BY Total_unit_sold DESC

--Top 10 cities with the highest revenue?
SELECT TOP 10 city, SUM(revenue) AS Total_revenue
FROM dbo.Data$
GROUP BY city
ORDER BY Total_revenue DESC

--Sales rep with the highest revenue made?
SELECT TOP 1 sales_rep, SUM(revenue) AS Total_revenue
FROM dbo.Data$
GROUP BY sales_rep
ORDER BY Total_revenue DESC

--Can you identify the top-performing products or services in terms of revenue?
SELECT TOP 5 product_name, SUM(revenue) AS Total_revenue
FROM dbo.Data$
GROUP BY product_name
ORDER BY Total_revenue DESC


--Are there specific customers contributing significantly to revenue?
SELECT TOP 5 customers, SUM(revenue) AS Total_revenue
FROM dbo.Data$
GROUP BY customers
ORDER BY Total_revenue DESC
