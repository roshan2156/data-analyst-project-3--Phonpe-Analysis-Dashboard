📱 PhonePe Transaction Analysis Dashboard | Power BI
📌 Project Overview
This project is an end-to-end PhonePe Transaction Analysis Dashboard developed using Power BI. The dashboard provides insights into transaction performance, payment success rates, customer demographics, and month-over-month business growth. It demonstrates the complete data analytics workflow, including data cleaning, data modeling, DAX calculations, and interactive dashboard development.

🎯 Objectives
Analyze overall transaction performance.
Monitor payment success rates.
Compare current and previous month transaction performance.
Identify top-performing services and customers.
Analyze user demographics by age group.
Compare weekday and weekend transaction patterns.
Build an interactive business intelligence dashboard for decision-making.
🛠️ Tools & Technologies
Power BI Desktop
Power Query
DAX (Data Analysis Expressions)
Microsoft Excel
Data Modeling
Star Schema
📂 Dataset
The project uses three tables:

All_Transactions
All_Users
Date_Table (Created using DAX)
🔄 Data Cleaning (Power Query)
The following data preparation steps were performed:

Removed duplicate records
Checked and handled missing values
Corrected data types
Renamed columns for better readability
Verified data quality using Column Quality and Column Distribution
Standardized Payment Status:
Insufficient Amount → Pending
Wrong PIN → Pending
Server Error → Pending
Created Age Segment using Conditional Column:
Age	Segment
≤ 26	Gen Z
≤ 42	Millennials
≤ 58	Gen X
> 58	Boomers
📅 Date Table
Created a custom Date Table using DAX.

Date_Table =ADDCOLUMNS(    CALENDAR(        MIN(All_Transactions[Date]),        MAX(All_Transactions[Date])    ),    "Year", YEAR([Date]),    "Month No.", MONTH([Date]),    "Month", FORMAT([Date], "MMM"),    "Quarter", "Q" & FORMAT([Date], "Q"),    "Weekday", FORMAT([Date], "dddd"),    "Day No.", WEEKDAY([Date],2),    "Weekend",    IF(WEEKDAY([Date],2)>=6,"Weekend","Weekday"))
Additional Steps:

Marked Date Table as Date Table
Sorted Month by Month No.
Sorted Weekday by Day No.
⭐ Data Modeling
Implemented a Star Schema.

Relationships:

Date_Table ➜ All_Transactions
All_Users ➜ All_Transactions
📊 KPI Measures
Created a dedicated Measures Table.

KPIs:

Total Transaction Value
Total Transactions
Successful Transactions
Success Rate
Total Users
Previous Month Transaction Value
Previous Month Transactions
Transaction Value MoM %
Total Transaction MoM %
📈 Dashboard Visualizations
The dashboard contains the following visualizations:

KPI Cards

Total Transaction Value
Total Transactions
Success Rate
Total Users
Previous Month Transaction Value
Transaction Value MoM %
Slicer

Month
Line Chart

X-Axis: Month
Y-Axis: Total Transaction Value
Shows monthly transaction trends.
Clustered Bar Chart

X-Axis: Service
Y-Axis: Total Transaction Value
Compares transaction value across different services.
Stacked Column Chart

X-Axis: Month
Y-Axis: Total Transactions
Legend: Payment Status
Displays monthly transactions categorized by payment status.
Donut Chart

Legend: Age Segment
Values: User_ID
Shows user distribution by generation.
Donut Chart

Legend: Weekend
Values: Total Transactions
Compares weekday and weekend transactions.
Clustered Bar Chart

X-Axis: Weekday
Y-Axis: Total Transactions
Displays transaction count across weekdays.
Top 5 Customers

X-Axis: Name
Y-Axis: Total Transaction Value
Applied Top N Filter to display the top 5 customers based on transaction value.
💡 Custom Tooltips
Created Report Page Tooltips for:

Service-wise Total Transaction Value
Weekend vs Weekday Total Transactions
🎨 Dashboard Features
Interactive KPI Cards
Dynamic Month Slicer
Time Intelligence Analysis
Month-over-Month Growth
Report Page Tooltips
Top N Filtering
Professional Dashboard Layout
Responsive Visualizations
📊 Business Insights
Monitored monthly transaction performance.
Analyzed payment success rates.
Compared current month with previous month using MoM analysis.
Identified top-performing services.
Identified Top 5 customers based on transaction value.
Analyzed customer demographics.
Compared weekday and weekend transaction patterns.
Evaluated transaction performance by payment status.
📚 Skills Demonstrated
Data Cleaning
Data Transformation
ETL
Power Query
DAX
Data Modeling
Star Schema
Time Intelligence
KPI Development
Dashboard Development
Business Intelligence
Data Visualization
📸 Dashboard Preview
<!-- Replace the links below with your actual GitHub image URLs -->
Dashboard View 1
Dashboard Screenshot 1

Dashboard View 2
Dashboard Screenshot 2

📁 Project Structure
text

📦 PhonePe-Transaction-Analysis-Dashboard
│
├── Dataset
├── Power BI Dashboard (.pbix)
├── Dashboard Screenshots
├── README.md
└── LICENSE
🚀 Future Enhancements
Add Year-over-Year (YoY) Analysis
Create Drill-through Reports
Add Bookmarks and Navigation Buttons
Publish Dashboard to Power BI Service
Implement Row-Level Security (RLS)
👨‍💻 Author
Roshan Patil

Email
LinkedIn
GitHub
