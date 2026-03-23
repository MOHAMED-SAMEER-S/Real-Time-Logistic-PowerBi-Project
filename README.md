
📌 Project Overview
SwiftRoute Logistics Dashboard is a multi-page, end-to-end Power BI solution built to monitor and optimize logistics operations across hubs, drivers, and vehicles. The dashboard enables operations managers and business stakeholders to make data-driven decisions using real-time KPIs, trend analysis, and performance breakdowns.

🎯 Business Objectives

Track overall logistics performance via KPIs like Total Orders, On-Time Delivery Rate, CSAT, and Average Delivery Time
Monitor hub capacity utilization and identify bottlenecks in order processing
Analyze driver performance — delays, experience-to-rating correlation, and individual profiles
Assess vehicle fleet health — active vehicles, breakdown patterns, and order distribution by model/type


📊 Dashboard Pages
Page 1 — Overview
KPIDescriptionTotal OrdersCurrent month orders + Previous Month + MoM % changeOn-Time Delivery Rate (%)Current vs Previous Month + MoM %Customer Satisfaction Score (CSAT %)Current vs Previous Month + MoM %Average Delivery Time (Hours)Current vs Previous Month + MoM %
Sections: Hub Summary · Driver Summary · Vehicle Summary

Page 2 — Hubs Overview

KPI Card — Total Number of Hubs
Clustered Column Chart — Orders Processed vs Hub Capacity
Ranked Bar Chart — Hub Performance Ranking
Matrix Chart — Hub Order Processing Time (daily hours per hub)


Page 3 — Drivers Overview

KPI Card — Total Number of Drivers
Scatter Plot — Driver Experience vs Performance Rating
Bar Chart — Drivers with Most Delays
KPI Card — Driver Profile Summary (Hire Date, YOE, Star Rating, Monthly Deliveries)
Line Chart — Monthly Trend of Orders per Driver


Page 4 — Vehicle Overview

KPI Card — Total Number of Vehicles
Donut Chart — Active vs Inactive Vehicles
Bar Chart — Total Orders by Vehicle Model
Scatter Chart — Vehicle Age vs Breakdown Count
Bar Chart — Breakdown by Vehicle Code & Model
Donut Chart — Orders by Vehicle Type


🛠️ Tools & Technologies
ToolUsagePower BI DesktopDashboard design & publishingDAXKPI measures — MoM%, YTD, MTD calculationsPower Query (M)Data cleaning & transformationData ModelingStar schema — fact & dimension table relationships

📐 Data Model

Star Schema design with a central fact table (Orders) linked to dimension tables:

Dim_Hub · Dim_Driver · Dim_Vehicle · Dim_Date


Relationships built for accurate cross-filtering across all report pages
Custom DAX measures for MoM comparisons and dynamic KPI cards


💡 Key DAX Measures (Examples)
DAX-- Month-over-Month Order Growth %
MoM Order Growth % = 
DIVIDE(
    [Total Orders] - [Previous Month Orders],
    [Previous Month Orders],
    0
)

-- On-Time Delivery Rate
On-Time Delivery Rate % = 
DIVIDE(
    COUNTROWS(FILTER(Orders, Orders[Delivery_Status] = "On Time")),
    COUNTROWS(Orders),
    0
) * 100

-- Average Delivery Time (Hours)
Avg Delivery Time (Hrs) = 
AVERAGE(Orders[Delivery_Duration_Hours])


📁 Repository Structure
swiftroute-logistics-dashboard/
│
├── SwiftRoute_Logistics.pbix        # Main Power BI report file
├── Business_Requirements.docx       # Business requirements document
├── README.md                        # Project documentation
└── screenshots/
    ├── overview_dashboard.png
    ├── hubs_overview.png
    ├── drivers_overview.png
    └── vehicles_overview.png

🚀 How to Use

Clone or download this repository
Open SwiftRoute_Logistics.pbix in Power BI Desktop
Refresh the data source if connected to a live dataset
Use the slicers (Year, Month) to filter KPIs dynamically
Navigate between pages using the report navigation tabs


👤 Author
Mohamed Sameer S — Junior Data Analyst
📧 mohamedsameera904@gmail.com
🔗 LinkedIn · GitHub · Portfolio
