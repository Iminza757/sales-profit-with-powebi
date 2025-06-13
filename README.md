# sales-profit-with-powebi
Data analysis and Visualization with Microsoft Power BI

POWER BI SALES & PROFIT ANALYSIS REPORT - FULL PROJECT DOCUMENTATION

Project Title: Root Cause Analysis of Low Profits in Sales Data using Power BI

Author: Cynthia Iminza


PROJECT OVERVIEW

This Power BI report aims to uncover why profits are significantly lower than sales in a U.S. Superstore dataset. By integrating data modeling, cleaning, transformation, and advanced visualizations, I created a fully interactive report that offers actionable insights for business improvement.


 1. DATA SOURCE & IMPORT

    
•	File: SuperStoreUS-2015.xlsx
•	Source Tool: Microsoft Excel
•	Imported into: Power BI Desktop
•	Sheets Used: Orders, Returns, Users



 3. DATA CLEANING & PREPARATION

Columns Removed

•	Postal Code: Dropped due to lack of relevance to business insights and granularity too low for decision-making.

Null Value Handling

•	Product Base Margin:
o	Only one null found →replaced it with 0 

DATA TYPE CONFIGURATION

Column	Data Type	Notes

Sales	Currency	Converted for formatting

Profit	Currency	

Discount	Percentage	Formatted and reduced to 0 decimal place

Product Base Margin	Percentage	Transformed to % for better interpretation

Quantity Ordered	Whole Number	

State, City, Region	Text	Set as categorical fields


 4. COLUMN TOOLS & DATA VALIDATION

Column Quality

Checks for error, valid and empty values, helping ensure clean and consistent input.

Column Distribution

Displays frequency of values in each column to help spot outliers or skewed entries.

Column Profile

Provides statistical details (min, max, avg, distinct, unique) for in-depth column understanding.

Reason: These tools ensure trust in the dataset and are crucial for professional-grade reporting.


 5. DATA MODELING & RELATIONSHIPS

Relationship Setup:

•	Orders ↔ Returns: [Order ID] → One-to-Many

•	Orders ↔ Users: [Region] → Many-to-One

Cardinality Choices:

•	Returns contains only some Order IDs → One-to-Many, Single Direction

•	Users table is a lookup for Region → Many Orders to one Region → Many-to-One

Why this matters: Proper cardinality ensures correct aggregations, performance optimization, and logic in filtering.


 6. MEASURES & DAX

Created Measures:

•	Total Sales = SUM(Orders[Sales])

•	Total Profit = SUM(Orders[Profit])

•	Total Quantity Ordered = SUM(Orders[Quantity Ordered])

•	Return Status =

Return Status =

IF(COUNTROWS(RELATEDTABLE(Returns)) > 0, "Returned", "Not Returned")

These measures support dynamic visuals and interactive filtering.


 7. VISUALIZATIONS & INSIGHTS

KPIs

•	Total Sales, Total Profit, Total Quantity Ordered

•	Filterable via Product Category and Region slicers

Visuals Used:

•	Decomposition Tree: Investigate profit decline causes (by category, segment, region, discount, shipping cost, status)


 8. INTERPRETATIONS & BUSINESS INSIGHTS

Major Findings:

•	Profits lag sales due to:

•	 High shipping costs (especially for furniture)

•	 Corporate customer segment contributing highest losses

•	 Furniture category at high loss rates

•	 Discounts correlated with returned or unprofitable orders



Regional Breakdown:

•	East & West had significant losses

•	Corporate orders in these regions, especially for Furniture, caused the most profit leakage

Segment Breakdown:

•	Home Office, Small Business, and Corporate showed losses despite good sales volumes

 
 8. RECOMMENDATIONS

•	Optimize freight partnerships for bulky product categories

•	Revise discount policies especially on low-margin items

•	Monitor return rates and build strategies to reduce them

•	Consider product redesigns or bundling for high-loss categories



10. FINAL REPORT CAPABILITIES

This report answers:

•	Why profits lag sales?

•	Which customer segments or regions are loss drivers?

•	How shipping costs impact bottom-line?

•	Where returns and discounts reduce profitability?

It empowers decisions across:

•	Operations (freight)

•	Sales (customer strategy)

•	Finance (margin protection)

