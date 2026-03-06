# send-performance-capacity-tool-dfe
Tool for SEND performance and capacity based on DfE published research (https://assets.publishing.service.gov.uk/media/69834976f13d4f72241ca9de/Time_spent_on_process_for_new_education__health_and_care_plans_by_local_authority_professionals_research_report.pdf) and SEN2 data.

SEN2 data is published yearly around June/July. The tool read the assessments and requests file directly from the web: https://explore-education-statistics.service.gov.uk/find-statistics/education-health-and-care-plans/2025. This will need to be pointed again after each census release. 

The open source Python code has been used to clean the data needed to generate four forecasting models which have been made available in the SEND EHCNA Team Capacity Tool (download from D2I website). 

The SEND EHCNA Team Capacity Tool is a self‑diagnostic workforce modelling tool designed to support Local Authorities in identifying capacity gaps across their SEND services, including Educational Psychology, SEND Casework, and SEND Management.
The tool incorporates published SEN2 data for All Requests Received in Year and applies a suite of four different forecasting approaches, allowing users to select the method most appropriate to their local context and trend patterns. These approaches help LAs estimate future demand and assess whether their workforce structure is sufficient to meet statutory timescales and caseload expectations for the EHCNA process.
To reflect real‑world practice, the tool also allows users to set the percentage of a worker’s time allocated to the EHCNA process. This means the model can account for the significant proportion of staff time required for other statutory and non‑statutory activities, such as early intervention, consultations, reviews, tribunals, school support, and cross‑agency collaboration. By adjusting this availability factor, LAs can see the true staffing need after accounting for competing priorities.
Overall, the tool provides a transparent, flexible, and evidence‑informed way for LAs to understand their SEND workforce capacity, identify pressure points, and plan more effectively for future demand.

The dataset includes four different forecasting models. Each model produces a percentage growth estimate for the next year based on historic trends in EHC request volumes (published SEN2 data). Each model is designed to capture a slightly different type of behaviour in the data. 
The same approcah is applyed to refusal to assess and refusal to issue rates

Option 1 — Crude Average YoY %
This method takes the average of all available year‑on‑year percentage changes.
It treats every year equally and is useful when the LA’s trend is relatively flat or when only limited information is available.
How it’s calculated:
- Compute YoY % for each year
- Take the simple average of all YoY % values

Option 2 — Last‑Year Only YoY %
This method uses only the most recent year’s percentage change as the forecast for the next year.
It is useful when there has been a sharp change recently, and the recent behaviour is the most important indicator.
How it’s calculated:
Use the YoY % between the latest year and the one before it
Apply that same percentage as next year’s growth

Option 3 — Weighted Average of the Last 3 Years
This method looks at the last 3 YoY % values but gives more weight to recent years.
It is useful when recent behaviour is important, but the forecast should not rely entirely on last year alone.
How it’s calculated:
Take the three most recent YoY % changes
Apply weights (e.g., 1 for oldest, 2 for middle, 3 for most recent)
Compute the weighted average

Option 4 — Linear Trend YoY %
This method fits a straight-line trend through all available YoY % values and projects that line forward into the next year.
It is helpful when the LA’s requests follow a long‑term upward or downward pattern, or when there is a lot of year‑to‑year volatility.
How it’s calculated:
Plot YoY % against year
Fit a simple linear regression line (y = ax + b)
Use the line to predict the YoY % for the next year

Together, these four models provide:
a long-term average (Option 1)
a short-term indicator (Option 2)
a balanced recent trend (Option 3)
a long-term direction of travel (Option 4)
This allows each LA to receive the forecast model that best reflects its historical behaviour.
