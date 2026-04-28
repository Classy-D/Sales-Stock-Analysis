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
This project analyse sales data to uncover trends in revenue, product performance, regional sales and profitability.
Using Excel for transformation and Power BI for visualization, the project turns raw transaction record into actionable insights.

### Tools and Technologies
* Excel
* Power BI

### Dataset Overview
Colummns:
Transaction, Date,	Age, Location, Product ID, Product Name,	Category, Quantity,	Shipping Method,	Event,	Customer Satisfaction,	Unit Price, Total Price

### Sample Preview     

|	Date	| Age |	Location	| Product Name |	Category	| Quantity |	Shipping Method	|	Event	|	Customer Satisfaction |	Unit Price | Total Price	|	
|------|-----|-----------|--------------|------------|----------|------------------|-------|-----------------------|------------|--------------|
|11/01/2018|	58|	Prince Edward Island|	Toys_Product|	Toys	|4|	Standard|	None|	1	|48|	$194	|																
|23/11/2022 |	26	|Nunavut|	Electronics_Product	|Electronics	|4|	Overnight|	Black Friday|	4|	77|	$309|																	
|11/01/2018|	20	|New Brunswick|	Decorations_Product|	Decorations|	5	|Express|	Christmas Market|	3	|25|	$126|																	
### Data Cleaning Process
- Converted Date to proper dateline format
- Removed missing or invalid values 
- Created new calculated fields:
- Revenue = Quantity * Unit priice  
- Profit_Margin 

### Exploratory Analysis (SQL)
1. Monthly Revenue Trend
```sql
SELECT
  DATE_TRUNC("nonth", Date) AS Month,
  SUM(Quantity • Unit Price) AS Total_Revenue stock sales
GROUP BY Month
ORDER BY Month;
```
2. Top 5 Products by Total Sales
```sql
SELECT
  Product Nano,
  SUM(Total Sales) AS Revenue
FROM stock_sales
GROUP BY Product None
ORDER BY Revenue DESC
LIMIT 5;
```
3. Revenue by Region
```sql
SELECT
Region,
SUM(Total_Sales) AS Revenue
FROM stock sales
GROUP BY Region
ORDER BY Revenue DESC;
```
Profitability by Category
```sql
SELECT
Category,
SUM(Profit) AS Total Profit,<img width="1366" height="768" alt="Screenshot (27)" src="https://github.com/user-attachments/assets/791e2deb-f949-478c-b11d-b5d5f7b5ef99" />
<img width="1366" height="768" alt="Screenshot (27)" src="https://github.com/user-attachments/assets/c90fcb3c-641a-49a8-8a94-3993cebf0c34" />

ROUND (SUM(Profit) / SUM(Units Sold * Unit Price), 2) AS Profit Margin
FROM stock_sales
GROUP BY Category;
```
### Power BI Dashboard
Power BI dashboard includes the following visuals:
- 📈 Revenue and profit over tine
- 🗺️ Regional sales performance
- Best and worst-performing products
- Monthly and quarterly growth trends
- Profit margins by category
- Interactive filters for product and region comparison Note: Dashboard screenshot on link can be added here.

<img width="950" height="533" alt="Screenshot 2026-04-26 164059" src="https://github.com/user-attachments/assets/acc0d471-fe2e-4d50-ac1c-d3c853ffb1ad" />

### Key Insights
1. The West region consistently generated the highest revenue.
> US had the highest revenue
2. Phones sold in large quantities but had lower profit margins.
3. Profitability peaked during the fourth quarter due to seasonal sales.
4. Some products with high units sold contributed less to total profit.

### Recommendations
* Shift focus to high-margin categorles such as laptops and accessories.
* Revisit pricing strategles for low-margin but high-volume Items.
* Apply successful regional strategies from the West to other underperforming areas.
* Plan inventory and promotions ahead of the fourth quarter to maximize seasonal gains.

### Future Work
Integrate automated SQL reporting Into B1 tools
Develop forecasting models using Python or Power B1
Bullda web dashboard for self-service reporting (e.g., Streanitor Dash)

Dataset Source

[Download Dataset](https://github.com/Classy-D/Sales-Stock-Analysis/edit/main/README.md)
(Google Drive)
