# AdvdentureWorks-Financial-Analysis
Enhancing Strategic Decision-Making Through Advanced Data Analytics at AdventureWorks

# Project Overview: AdventureWorks Sales and Operations Dashboard

## Problem Statement
At AdventureWorks, we identified key operational challenges through an extensive examination of our database, including sales performance, customer behavior, product returns, and inventory management. This project, using PowerBI, targets these critical areas to optimize business operations and enhance decision-making capabilities.

## Objectives
- **Sales Performance Analysis:** Evaluate and refine sales strategies to boost revenue.
- **Customer Retention and Value Optimization:** Understand and enhance customer engagement and value through effective segmentation.
- **Product Returns Management:** Minimize return rates and address quality issues.
- **Inventory Optimization:** Improve inventory management to balance stock levels and reduce costs.
- **Data Integration:** Consolidate multi-source data for real-time business insights.

## Intended Audience
The PowerBI dashboard is designed for:
- **C-Suite Executives:** For strategic decision-making based on key performance metrics.
- **Sales and Marketing Teams:** To tailor strategies based on detailed customer and sales data.
- **Product Management and Development Teams:** For product performance tracking and feedback integration.
- **Operations and Supply Chain Management:** To manage inventory and operational efficiency.

## Data Source
Data for this analysis comes from the Adventure Works database, a Microsoft SQL Server sample database widely used for educational and demonstrative purposes.

## Client Perspective
A business analytics graduate provided insights that shaped the dashboard to offer actionable intelligence across business operations, emphasizing the need for enhanced data visualization and customer segmentation.

## Detailed Steps Taken in the Project

### 1. Data Preprocessing
Detailed preprocessing steps were taken for critical data tables to ensure their readiness for analysis:

- **Product Lookup Table**
  - Promoted headers to column names and adjusted data types.
  - Specific columns formatted to currency and unnecessary columns removed.
  - Text was inserted before delimiters for correct parsing, and columns were renamed for clarity.

- **Customer Lookup Table**
  - Promoted headers set column names; data types were standardized.
  - Error records removed to clean the dataset, and specific rows filtered out.
  - Text manipulations included capitalizing each word and extracting segments for better parsing.
  - New columns such as a full name column and domain name column were added to enrich the data.

- **Calendar Lookup Table**
  - Promoted headers to set column names and standardized data types.
  - Added key temporal features such as day names, start of the week, month, quarter, and year.

### 2. Data Model Creation
After initial preprocessing, data was organized by creating an Entity-Relationship (ER) diagram:

- Utilized a snowflake schema to establish a structured relational schema connecting various lookup tables.
- Enhanced the capability of the PowerBI dashboard to provide integrated and actionable business insights by linking tables according to their relationships and constraints.

### 3. Calculated Fields and Measures with DAX
Dynamic measures crafted using Data Analysis Expressions (DAX) included:

- **Previous Month Orders:** `CALCULATE([Total Orders], DATEADD('Calendar Lookup'[Date], -1, MONTH))`
- **YTD Revenue:** `CALCULATE([Total Revenue], DATESYTD('Calendar Lookup'[Date]))`
- **10-day Rolling Revenue:** `CALCULATE([Total Revenue], DATESINPERIOD('Calendar Lookup'[Date], MAX('Calendar Lookup'[Date]), -10, DAY))`

### 4. Visualizing Data
Focus on constructing dynamic and interactive reports within PowerBI:

- Employed various visualization types to cater to diverse analytic needs across different user profiles.
- Implemented advanced features such as bookmarks, drill-through filters, tooltips to enhance the dashboard's interactivity.
- The visualization strategy was designed to ensure clear communication of data through structured, clean, and organized visual layouts.

## Discoveries and Insights from the Data

The analysis conducted through the PowerBI dashboard revealed significant insights into customer demographics, buying patterns, and sales performance at AdventureWorks:

### Customer Insights
- **Revenue Tracking:** Ability to track revenue per customer alongside orders by income level and occupation provided a nuanced understanding of the customer base.
- **Segmentation Utility:** Different groups were identified contributing variably to overall sales, which underscores the potential for targeted marketing strategies.
- **High-Value Customers:** Notably, high-income customers, like Mr. Maurice Shan who generated significant revenue from fewer orders, emphasize the importance of nurturing high-value relationships to bolster overall revenue.

### Sales Dynamics
- **Seasonal Trends:** Weekly revenue data displayed a significant upward trend, peaking in January 2022, suggesting impacts from seasonal sales likely influenced by holiday shopping.
- **Product Preferences:** Accessories and Bikes dominated the orders, indicating strong market preferences. Conversely, high return rates for products like the Sport-100 Helmets hinted at quality or customer satisfaction issues.
- **Emerging Challenges:** A recent dip in revenue and orders, coupled with an increase in returns, especially for Tires and Tubes, highlighted potential issues in product fit or customer expectations.

### Visual Insights
Incorporated screenshots from the dashboard provide a visual summary of these findings:
![Customer Insights Dashboard](url-to-customer-insights-dashboard-image)
![Sales Dynamics Dashboard](url-to-sales-dynamics-dashboard-image)

## Challenges Encountered and Solutions

During the development of the PowerBI dashboard, several challenges were faced, particularly in creating dynamic measures that accurately reflect business performance:

- **Dynamic Measures Difficulty:** Initial attempts at implementing measures like "Previous Month Profit" and "90-day Rolling Profit" faced challenges due to the complexity of DAX functions and the need for precise date manipulation.

- **Solutions Implemented:**
  - **Advanced DAX Utilization:** To resolve these, advanced DAX functions were employed. For "Previous Month Profit," the `CALCULATE` function combined with `DATEADD` was used to adjust the calculation context to the previous month, providing an accurate reflection of past performance.
  - **Rolling Calculations:** For the "90-day Rolling Profit," `CALCULATE` in conjunction with `DATESINPERIOD` and `MAX` created a moving sum of profit for the last 90 days, enhancing the dashboard’s capability to offer actionable insights through dynamic measures.

## Adjustments Made from the Original Plan

During the development of the AdventureWorks PowerBI dashboard, several adjustments were necessary to better meet the specific informational needs of different user groups within the company.

### Initial Challenges
Initially, our approach was too broad, focusing primarily on general data aggregation and display. This resulted in:
- A lack of actionable insights for different user groups.
- Data being too aggregated and not detailed enough for effective decision-making.

### Strategic Pivot
Feedback from users highlighted the need for more tailored insights and visualizations. To address this, we asked ourselves critical questions to redefine our approach:
1. **What type of data are we working with?**
2. **What do we want to communicate?**
3. **Who is the end user, and what do they need?**

### Implementation of a Structured Framework
Based on these questions, we adopted a structured framework that led us to:
- **Distinguish between different types of data:** Financial, time-series, and geospatial data each required specific visualization techniques.
- **Align visualizations with communication goals:** Focusing on illustrating trends, distributions, and relationships specific to user needs.
- **Customize views for specific departments:** For instance, detailed trend analysis was designed for financial executives, while operational data was tailored for regional managers.

### Outcomes
This strategic pivot greatly enhanced the effectiveness of the dashboard by:
- Providing customized views that catered to the diverse analytical needs of various departments.
- Significantly improving user engagement and satisfaction with the dashboard.
- Ensuring that the insights generated were not only relevant but also actionable, supporting strategic business decisions and operational efficiency.

