Sales-Data-Analysis

Sales Data Analysis Dashboard
Project Documentation
Company Name: Afame Technologies

Project Overview
This project aims to analyze sales data, providing insights into product performance, regional sales, and sales forecasting. The dashboard helps Afame Technologies make data-driven decisions by understanding sales patterns and forecasting future trends.

Steps Involved

1. Data Cleaning
	Removed Unnecessary Columns: Dropped columns that were not relevant to the analysis, streamlining the dataset for clearer insights.
	Corrected Data Types: Ensured that each column had an appropriate data type (e.g., converting text to categorical, ensuring numeric columns were properly formatted). This step was crucial for accurate data analysis and calculation.

3. Data Transformation
	Calculated Column - `AvgDelivery`: Created a calculated column using DAX to determine the average delivery time for products. This was calculated by finding the average number of days between the order date and the delivery date.

DAX Code Example:
AvgDelivery = DATEDIFF('Orders'[Order Date],'Orders'[Ship Date],DAY)

5. Created Measures
	Measure - `Best_Selling_Product_Name`: Developed a DAX measure to identify the best-selling product by category and overall. This measure helps in identifying the top-performing products, giving insights into product demand across various categories.

DAX Code Example:
Best_Selling_Product_Name = SELECTCOLUMNS( TOPN(1, VALUES(Orders[Product Name]), CALCULATE(SUM(Orders[Sales])), DESC ), "Product", Orders[Product Name] )

4. Slicers/Filters
	Region Slicer: Added a slicer to filter the dashboard by region. This enables Afame Technologies to view sales data specific to each region, allowing regional sales comparison.
	Category Slicer: Implemented a slicer to filter by product category. This helps visualize the sales data for each product category independently, aiding in the analysis of category-wise performance.

6. Sales Forecasting
	15-Day Sales Forecast: Added a forecast visual that predicts sales for the next 15 days based on historical sales data. This forecast provides insights into upcoming sales trends, helping the company in stock and resource planning.
Forecasting was done using Power BI’s built-in analytics pane, which allowed for configuring the forecast length and confidence interval based on historical data patterns.

Key Visuals and Insights
1.	Sales Overview by Region and Category: Visualizations to analyze sales distribution across different regions and categories.
2.	 Top-Selling Products: Charts showing the best-performing products, both overall and by category.
3.	Sales Forecasting: A line chart predicting sales trends for the next 15 days.
4.	Total Sales: A bar chart displaying the total sales generated over a period of time.
5.	Total Profit: A line graph representing the company's profit trends based on sales and operational costs.

Conclusion
The dashboard developed for Afame Technologies provides clear, actionable insights into sales performance and future sales trends. By focusing on the best-selling products, regional and category analysis, and forecasting, the dashboard will support the company's decision-making processes in inventory management, marketing, and sales strategy planning.
