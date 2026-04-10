# SwiftRoute-Logistics-Performance-Analytics

## Project Overview 
This project optimizes supply chain efficiency by transforming raw logistics data into a 4-dashboard Power BI package that enables data-driven decisions for fleet maintenance, driver performance, and hub capacity through a Star Schema architecture and real-time KPI tracking.

This dashboard helps determine the under-utilised Hub capacity and identify whether the reasons for delays are due to drivers performance or vehicle breakdowns.

## Business Objectives
Key questions addressed :-
- Are the Hubs operated at their full potential ?
- How far does the experience impact performance ratings of Drivers ? Driver with the worst Performance Ratings ? ( they usually are those that have experience less than 2 years).
- Identifying the Type of Vehicles that deliver most orders?
- Identifying whether the increasing maintenance costs are due to old vehicles or increasing Breakdowns ?

## Source Data
- **Orders** (fact_table) :- ( 27,979 records )	→ Core dataset at the center of Star schema.
- **Vehicles** (dim_table) :- (45 records) 	→ used to Analyse the Fleet health, maintenance patterns, & cost inefficiencies.
- **Hubs**  (dim_table) :- (6 records) 	→ Enables capacity utilization analysis and identification of overloaded or underutilized hubs.
- **Drivers**  (dim_table) :- (55 records)  → Supports evaluation of driver efficiency, experience impact, and performance benchmarking.

| Table        | Columns         |
|--------------|-----------------|
|Orders        |OrderID, Actual_Delivery_Date, Delay_reason, DriverID, DriverName, HubName, IsDelayed, Is_On_Time, Order_Date, Order_Status, Vehicle_Name, Customer_Satisfaction_Score, Delivery_Time_Hours, Hub_processing_time_Hours |
|Vehicles      |Purchase date, Vehicle ID, Vehicle Model, Vehicle Status, Breakdown, Maintenance count Alert, Vehicle code, Vehicle Age |
|Hubs          |HubID, HubName, Hubcapacity |
|Drivers       |DriversID, DriverName, Employment Type, Hire date, Experience years, Performance rating |

## TECH STACK 
- **Tool:** Power BI Desktop
- **Language:** DAX (Data Analysis Expressions)
- **Key Concepts:** Time Intelligence, Conditional Formatting, Page Navigation.

## Data Model 
This analysis is built on the **Star schema** data model, with the 'Orders' fact_table at its core and supported by multiple dimensions table.
- **One-to-Many relationship** is established with all dimension tables
- Created **Date table** to enable time intelligence functions (MoM trends, Last Month comparisons, etc.).

## 💡 Key Insights

- **Hub Utilization** :- Most hubs, including **Houston** and **Dallas Main**, are operating close to their maximum capacity, with Total Orders nearly matching the Total Hub Capacity.
    
- **Hub Performance** :- The **El Paso Hub** leads in performance with a ranking of **84.4%**, while the **Fort Worth Hub** shows the most room for improvement at **75.0%**.
    
- **Driver Correlation** :- The **Experience vs. Rating** scatter plot indicates that the Driver having 2+ years Experience maintains a performance ranking of 3-4 despite being the top 10 drivers with Most Delays.
    
- **Operational Delays** :- A Top 10 group of drivers, responsible for the highest percentage of delayed deliveries generally falls in range 30%- 45% .
    
- **Fleet Health** :- Approximately **26.67%** (12 vehicles) of the fleet is currently under **Maintenance**, while **73.33%** (33 vehicles) remain **Active**.
    
- **Vehicle Performance** :- The **Mercedes Sprinter**, **Frieghtliner M2** and **Ford Transit** are the most utilized models, handling 45, 43 and 41 total orders respectively.

## Dashboard Preview 
1. **Executive Overview:** High-level KPIs (Total Orders, OTD %, CSAT, Avg Delivery Time) with Month-over-Month (MoM) growth tracking.
    
2. **Driver Performance:** Analysis of experience vs. ratings and identifying drivers with the highest delay rates.
    
3. **Hub Operations:** Comparison of Hub capacity vs. actual orders processed and daily processing time trends.
    
4. **Vehicle Fleet Health:** Correlation analysis between vehicle age and breakdown frequency.
