
# SEND Performance and Capacity Tool (DfE)

![Version Badge](https://img.shields.io/badge/version-1.0.0-blue)
![Licence Badge](https://img.shields.io/badge/licence-MIT-green)

Tool for SEND performance and capacity based on published DfE research and SEN2 data.

- DfE Research Report:  
  https://assets.publishing.service.gov.uk/media/69834976f13d4f72241ca9de/Time_spent_on_process_for_new_education__health_and_care_plans_by_local_authority_professionals_research_report.pdf  

- SEN2 Data Source:  
  https://explore-education-statistics.service.gov.uk/find-statistics/education-health-and-care-plans/2025

SEN2 data is published yearly around June or July. The tool reads the Assessments and Requests file directly from the web, so the link will need updating after each census release.

---

## Overview of the Tool

The open source Python code is used to clean SEN2 data and generate four forecasting models. These models are incorporated into the SEND EHCNA Team Capacity Tool (available from the D2I website).

The tool is a self diagnostic workforce modelling resource designed to support Local Authorities in identifying capacity gaps across SEND services, including:

- Educational Psychology  
- SEND Casework  
- SEND Management  

It uses published SEN2 counts for all requests received in the year and applies four different forecasting approaches. Users can choose the method most suitable for their local trend patterns.

The tool also lets users set the proportion of a worker's time allocated to EHCNA activity. This reflects real world practice where staff spend time on:

- Early intervention  
- Consultations  
- Reviews  
- Tribunals  
- School support  
- Cross agency collaboration  

This helps Local Authorities estimate the true staffing requirement once competing priorities are accounted for.

Overall, tool provides transparent, flexible and evidence informed method for understanding SEND workforce capacity, identifying pressure points and planning for future demand.

---

## Forecasting Models

The dataset includes 4 forecasting models. Each model produces a percentage growth estimate for the next year based on historic EHC request volumes. The same method is applied to refusal to assess and refusal to issue rates.

### Option 1: Crude Average Year on Year Percentage

Simple average of all available year on year percentages.  
Useful when the trend is relatively flat or there is limited historic data.

**Calculation**

- Compute each year's percentage change  
- Take the simple average  

---

### Option 2: Last Year Only Year on Year Percentage

Uses only the most recent year on year change.  
Useful when a recent shift is the most important indicator.

**Calculation**

- Take the most recent percentage change  
- Apply it to forecast the next year  

---

### Option 3: Weighted Average of the Last Three Years

Uses the latest three year on year percentages with more weight on recent years.  
Useful when recent behaviour is important but should not fully dictate the forecast.

**Calculation**

- Identify the latest three year on year values  
- Apply weights, for example:  
  - Oldest: 1  
  - Middle: 2  
  - Most recent: 3  
- Compute the weighted average  

---

### Option 4: Linear Trend Year on Year Percentage

Fits a linear trend through all available year on year values and projects it forward.  
Useful when there is a consistent upward or downward pattern or high volatility.

**Calculation**

- Plot year on year percentage by year  
- Fit a linear regression line  
- Use it to predict next year’s value  

---

## Summary of Model Purposes

- **Option 1**: Long term average  
- **Option 2**: Short term indicator  
- **Option 3**: Balanced recent trend  
- **Option 4**: Long term direction of travel  

These options let each Local Authority choose the forecast approach that best reflects its historical pattern.
