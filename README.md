# Project Documentation: Employee Insights Dashboard
## Table of Contents
 - [Project Overview](#project-overview)
 - [Data Collection and Preprocessing](#data-collection-and-preprocessing)
 - [Tools and Technologies](#tools-and-technologies)
 - [Exploratory Data Analysis](#exploratory-data-analysis)
 - [Creating Metrics and Measures](#creating-metrics-and-measures)
 - [Dashboard Creation](#dashboard-creation)
 - [Insights and Analysis](#insights-and-analysis)
 - [Enhancements and Future Work](#enhancements-and-future-work)
 - [Conclusion](#conclusion)

## Project Overview
The Employee Insights Dashboard project aims to analyze employee behavior and trends within the company to derive actionable insights for HR decision-making. By examining working preferences, sick leave patterns, and other relevant metrics, the project seeks to provide valuable information to enhance employee well-being and organizational efficiency.

## Data Collection and Preprocessing
- **Data Sources**: The project utilizes data obtained from the company's CRM system and HR databases, including information on employee attendance, sick leave, and working preferences.
- **Data Cleaning**: The data underwent thorough cleaning to address issues such as missing values, duplicates, and inconsistencies. Power Query scripts were used to transform the data into a structured format suitable for analysis.
- **Attendance Key**: The attendance key provides a reference for interpreting the codes used in the dataset to denote different types of employee attendance, such as present, sick leave, work from home, etc. This key was used during the data cleaning and preprocessing phase to standardize attendance records.

### Attendance Key

| Code | Description                |
|------|----------------------------|
| P    | Present                    |
| PL   | Paid Leave                 |
| SL   | Sick Leave                 |
| HPL  | Half day Paid Leave        |
| HSL  | Half day Sick Leave        |
| WFH  | Work from Home             |
| FFL  | Floating Festival Leave    |
| HFFL | Half Day Floating Festival Leave |
| BL   | Birthday Leave             |
| LWP  | Leave without Pay          |
| HLWP | Half day Leave without Pay |
| BRL  | Bereavement Leave          |
| HBRL | Half Bereavement Leave     |
| HWFH | Half Work From Home        |
| WO   | Weekly Off                 |
| HO   | Holiday Off                |
| ML   | Menstrual Leave            |
| HML  | Half Day Menstrual Leave   |

## Tools and Technologies
- **Power BI**: Used for creating interactive visualizations and dashboard.
- ** Power Query**: data connectivity and preparation tool.
- **DAX (Data Analysis Expressions)**: Custom calculations for creating measures and calculated columns.
- **Microsoft Excel**: for initial data exploration, simple calculations.
- **SharePoint**: used for document management and content sharing within organizations.
- **GitHub**: for version control and collaboration.
  
## Exploratory Data Analysis (EDA)
- **Working Preferences Analysis**: Exploratory analysis revealed insights into employee working preferences, highlighting trends in working from home versus working from the office.
- **Sick Leave Patterns**: Examination of sick leave data uncovered patterns in sick leave percentages and reasons for sick leave, providing insights into employee wellness and potential health concerns.

## Creating Metrics and Measures
- **Presence Percentage**: A metric was created to calculate the percentage of days each employee was present in the office or working remotely.
- **WFH Percentage**: Another metric was developed to determine the percentage of days employees chose to work from home.
- **Sick Leave Percentage**: A metric was generated to quantify the percentage of days employees took sick leave, shedding light on potential health-related issues.
- **Dax-Measures**
  `
  Office Working days = Var totaldays = [Count]
  VAR nonworkdays = CALCULATE([Count],'Final Data'[Value] in {"HO", "WO"})
  RETURN
  totaldays-nonworkdays `

` SL % = DIVIDE('Measures (2)'[SL Count], [Office Working days]`
` WFH % = DIVIDE([WFH Count],'Measures (2)'[Present Days],0)`
` Attendace % = DIVIDE([Present Days],[Office Working days],0)`
` HFWH Count = CALCULATE([Count],'Final Data'[Value]="HWFH")`

## Dashboard Creation
- **Overview**: A Power BI dashboard was created to visualize key insights derived from the data analysis.
- **Layout and Design**: The dashboard features a user-friendly layout with interactive visualizations and drill-down capabilities for detailed analysis.
- **Key Visualizations**: Visualizations include line charts, bar graphs, and tables to present insights on working preferences, sick leave patterns, and employee attendance.

## Insights and Analysis
- **Working Preferences**: Analysis revealed that employees showed a preference for working from home on Thursdays and Fridays, potentially indicating a desire for flexibility towards the end of the workweek.
- **Sick Leave Patterns**: The dashboard highlighted an increase in sick leave percentages during certain months, prompting further investigation into potential health-related concerns or external factors impacting employee well-being.

## Enhancements and Future Work
- **Real-time Data Updates**: Future iterations of the project could incorporate real-time data updates to provide more timely insights into employee behavior.
- **Automated Alerts**: Implementation of automated alerts could notify HR stakeholders of significant deviations in attendance or sick leave patterns, enabling proactive intervention and support.
- **Security Enhancements**: Enhanced security measures, such as row-level security in Power BI, could be implemented to restrict access to sensitive employee data and ensure data privacy compliance.

## Conclusion
The Employee Insights Dashboard project has successfully provided valuable insights into employee behavior and trends within the organization. By leveraging data analytics techniques and visualization tools, HR stakeholders can make informed decisions to enhance employee well-being and organizational effectiveness.

