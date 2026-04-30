# Sales Analysis | Revenue, Trends and Insights
Excel. SQL. Power BI Project | Sales data | From raw data to Business insight

### Table of contents
- [Project Overview](#project-overview)
- [Tools $ Technologies](#tools--technologies)
- [Dataset Overview](#dataset-overview)
- [Data Cleaning Process](#data-cleaning-process)
- [Exploratory Analysis](#exploratory-analysis)
- [Power BI Dashboard](#power-bi-dashboard)
- [Key Insight](#key-insights)
- [Recommendations](#recommendations)
- [Future Work](#future-work)

### Project overview
This project analyse sales data to uncover trends in revenue, product performance, regional sales and customer engagement.
Using Excel for transformation and Power BI for visualization, the project turns raw transaction record into actionable insights.

### Tools and Technologies
* SQL
* Excel
* Power BI

### Dataset Overview
Colummns:
Transaction, Date,	Age, Location, Product ID, Product Name,	Category, Quantity,	Shipping Method,	Event,	Customer Satisfaction,	Unit Price, Total Price

### Sample Preview     

|	Date	| Age |	Location	| Product Name |	Category	| Quantity |	Shipping Method	|	Event	|	Customer Satisfaction |	Unit Price | Total Price |
|------|-----|-----------|--------------|------------|----------|------------------|-------|-----------------------|------------|--------------|
|11/01/2018|	58|	Prince Edward Island|	Toys_Product|	Toys	|4|	Standard|	None|	1	|48|	$194	|																
|23/11/2022 |	26	|Nunavut|	Electronics_Product	|Electronics	|4|	Overnight|	Black Friday|	4|	77|	$309|																	
|11/01/2018|	20	|New Brunswick|	Decorations_Product|	Decorations|	5	|Express|	Christmas Market|	3	|25|	$126|		

### Data Cleaning Process
- Converted Date to proper dateline format
- Removed missing or invalid values 
- Created new calculated fields:
- Total price = Quantity * Unit priice   

### Exploratory Analysis (SQL)
1. Revenue by Product
```sql
SELECT 
    product_name,
    SUM(total_sales) AS total_revenue
FROM sales_data
GROUP BY product_name
ORDER BY total_revenue DESC;
```
2. Sales by location
```sql
SELECT 
    location,
    SUM(total_sales) AS total_sales,
    SUM(quantity) AS total_quantity
FROM sales_data
GROUP BY location
ORDER BY total_sales DESC;
```
3. Sales by Product Category
```sql
SELECT 
    product_category,
    SUM(total_sales) AS revenue,
    AVG(unit_price) AS avg_price
FROM sales_data
GROUP BY product_category
ORDER BY revenue DESC;
```
4. Shipping Method Analysis
```sql
SELECT 
    shipping_method,
    COUNT(*) AS number_of_orders,
    SUM(total_sales) AS total_sales
FROM sales_data
GROUP BY shipping_method
ORDER BY total_sales DESC;
```
5. Sales Trend Over Time
```sql
SELECT 
    date,
    SUM(total_sales) AS daily_sales
FROM sales_data
GROUP BY date
ORDER BY date;
```

### Power BI Dashboard
Power BI dashboard includes the following visuals:
- 📈 Revenue and profit over tine
- 🗺️ Regional sales performance
- 📊 Best and worst-performing products
- 🚀 Monthly and quarterly growth trends
- 💹 Profit margins by category
- ⚖️ Interactive filters for product and region comparison
  
  <img width="925" height="516" alt="Screenshot 2026-04-28 235528" src="https://github.com/user-attachments/assets/2f87f90e-66ec-46a7-b2f7-0e818a2720dc" />
  
  <img width="911" height="510" alt="Screenshot 2026-04-29 000038" src="https://github.com/user-attachments/assets/1c2a1be0-1f5a-458b-a3d8-1e1ffb0ade50" />

### Key Insights
1. According to this dataset, revenue was generated as follows:
> Columbia generated the highest revenue.
> Newfoundland and Labrador generated the least revenue
2. In the product category:
> Toys, Electronics and Food ranked the top 3 produt that generated sales
3. Standard shipping method is the most used method of shipping products
4. Most sales was made in 2023 and sales declined the most in 2019

### Recommendations
* Shift focus to high-margin categorles such as Toys, Electronics and food categories.
* Revisit pricing strategles for low-margin but high-volume Items like Decorations and Cothing
* Apply successful regional strategies to underperforming areas.
* Plan inventory and promotions to maximize seasonal gains.
*Improve product and service quality to increase the rate of customer satisfaction
