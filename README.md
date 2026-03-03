# Analysis of Frostbites

## Project Overview
This project focuses on the statistical analysis of frostbite cases in Poland between 2021 and 2025 . The goal is to identify patterns related to demographics, severity, and seasonal trends based on regional data.

## Key Insights
* The Mortality Paradox: While men account for 85% of hospitalizations, the mortality rate among women is significantly higher at 22%, compared to 13.5% for men.
* Trend Shift (2021–2025): There is a notable decrease in severe frostbite cases with necrosis (ICD-10: T34), accompanied by a rise in systemic hypothermia cases (ICD-10: T68). This shift suggests changing demographics within high-risk groups.
* The Pandemic Effect: A sharp decline in hospitalizations was observed in 2020, followed by a surge in 2021. This indicates a "diagnostic gap" and delayed treatments caused by the COVID-19 pandemic.

## The Process
1.**Import data**
* Imported raw clinical datasets in CSV format directly into Power BI.
  
2.**Cleaning data**
* In Power Query removed duplicates to ensure statistical validity.
* To maintain calculation continuity, values marked as "<5" were replaced with a constant numerical value of 2 by Replace Values. This approach enabled mathematical operations while maintaining an acceptable margin of statistical error.
  
3.**Visualization**
* Implemented "Top N" filters to isolate the 3 most frequent medical conditions, reducing visual clutter and focusing on high-impact diagnoses.
* Created dynamic integrated slicers for Year, Gender, and Age Group, enabling deep-dive correlation analysis across various demographics.
* Utilized line charts with synchronized timelines and Zoom Sliders for precise observation of shifts between 2021 and 2025.

4.**UX/UI Optimization**
* Configured advanced interactions between visuals, allowing the dashboard to instantly recalculate and update all metrics based on user selection.


## Tools
* Data Transformation: Power Query
* Analytics: DAX
* Visualization: Power BI Dashboards
* Documentation : GitHub


## Podgląd projektu
![image]("https://github.com/MagdalenaZda/analysis-of-frostbites/tree/assets")

##  Data Source
https://dane.gov.pl/pl/dataset/3819,swiadczenia-z-rozpoznaniem-odmrozenia-i-hipotermii
