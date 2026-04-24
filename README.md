PROJECT TITLE: "Sales Performance Dashboard".

THE GOAL:
        "Designed and developed an end-to-end power BI dashboard to enable business stakeholders
        to monitor sales performance, identify revenue drivers, and uncover profitability trends
        across regions and product categories. The solution focuses on transforming raw transactional
        data into actionable insights for strategic decision making.

TECHNICAL BREAKDOWN:
  
 1. ETL Process (Power Query)
     The foundation of the project involved processing a raw dataset of 51,290 rows.
     I utilized the Power Query Editor to perform the following Extract, Transform, and Load (ETL)
    steps:
    Data Cleaning: Identified and handled missing values and removed duplicate records to ensure a "Single Source of Truth."
    Data Type Optimization: * Converted Postal Code to Text to prevent the loss of leading zeros.
    Standardized Order Date and Ship Date into proper Date formats for accurate time-series analysis.
    Financial Accuracy: Adjusted Sales and Profit columns to Fixed Decimal Number (Currency) to maintain
     precision during complex DAX calculations.
    
 2. Data Modeling (Star Schema)
    To ensure the dashboard was fast and scalable, I architected a Star Schema model. This involves separating
    transactional data (Facts) from lookup data (Dimensions):
    Fact Table: Orders (Contains all numeric metrics and keys).
    Dimension Tables: People (Regional Managers) and Returns (Order status).
    Relationships: Established One-to-Many relationships.
    Connected Orders to People via the Region field.
    Connected Orders to Returns via the Order ID field.
    
 3. DAX Measure Development
    I moved beyond basic drag-and-drop visuals by developing custom DAX (Data Analysis Expressions) measures.
     This ensures the KPIs are dynamic and respond correctly to any applied filters:
    Total Revenue: Total Revenue = SUM(Orders[Sales])
    Purpose: Calculates gross sales across the entire global dataset.
    Total Profit: Total Profit = SUM(Orders[Profit])
    Purpose: Tracks the bottom-line profitability for executive review.
    Formatting: All measures were formatted as Currency ($) with 0 decimal places to provide a clean, professional "Executive View."
    
 4. Interactive Cross-Filtering
    The core value of this dashboard is its Interactivity. By establishing a proper data model,
    I enabled Cross-Filtering across the entire report:
    How it Works: When a user interacts with a visual (e.g., clicking on a specific Manager in the Bar Chart),
    the filter "flows" through the Star Schema relationships.
    The Benefit: This instantly updates the Revenue Trend (Line Chart) and KPI Cards to reflect only that manager's data.
    This allows stakeholders to perform "Drill-Down" analysis into specific categories or regions
     without needing multiple separate reports.



KEY INSIGHTS:
       Top Revenue Driver:
       Identified Technology as the highest-grossing category, contributing significantly to the $13M total sales,
       suggesting a focus on tech inventory for growth.
       Regional Powerhouses: Discovered that the Western and Central regions consistently outperform others, 
       pinpointing high-performing managers (like Anna or Chuck) whose strategies could be scaled.
       
  Profitability vs. Volume:
       Noticed that while Office Supplies has the highest volume of orders, Technology maintains a much higher profit margin per unit.
       Return Rate Impact: Analyzed the Returns table to find that certain segments have higher return rates,
       highlighting a $X amount of "at-risk" revenue that needs quality control.
       
   Growth Trends:
       Used the Line Chart to identify a clear seasonal spike in Q4 (November/December), allowing for better workforce
       and inventory planning for peak periods.
