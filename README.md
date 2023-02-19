# Dubstech 4th Datathon Code Repository

## PROBLEM STATEMENT

The COVID-19 pandemic has put extreme stress on the health care workforce in the United States, leading to workforce shortages as well as increased health care worker burnout, exhaustion, and trauma. These pandemic-related challenges have taken place in a context of significant preexisting workforce shortages and maldistribution, as well as in a workforce where burnout, stress, and mental health problems (including an ongoing risk of post-traumatic stress disorder) were already significant problems. This has made it critical for the United States government and hospitals to better manage and prepare their resources and healthcare personnel. 

The aim of this project is to identify trends present in the data, define a metric to identify COVID burden of a hospital and predict the bed usage for 12 weeks based on the city/state specified.  

## DATASET

Link: https://healthdata.gov/stories/s/nhgk-5gpv

The dataset provides facility-level data for hospital utilization aggregated on a weekly basis (Friday to Thursday). These are derived from reports with facility-level granularity across two main sources: (1) HHS TeleTracking, and (2) reporting provided directly to HHS Protect by state/territorial health departments on behalf of their healthcare facilities. The hospital population includes all hospitals registered with Centers for Medicare & Medicaid Services (CMS) as of June 1, 2020. It includes non-CMS hospitals that have reported since July 15, 2020. It does not include psychiatric, rehabilitation, Indian Health Service (IHS) facilities, U.S. Department of Veterans Affairs (VA) facilities, Defense Health Agency (DHA) facilities, and religious non-medical facilities.

## DOCUMENTATION
Link to the detailed documentation.

## DASHBOARD
Here is a link to out [Tableau dashboard](https://public.tableau.com/app/profile/tharun.kumar.reddy5213/viz/OptimizersHospitalBedsDashboard/AnalysisDashboard?publish=yes).

## TASKS

1. **Machine Learning Modelling** to predict the `"inpatient_beds_used_covid_7_day_sum"` values for the next 12 weeks  for: 
- A specific city selected (`"city"`)
- A specific state selected

2. **Metric** to rank the COVID burden a hospital is experiencing.


3. **Data Analysis + Data Visualization**
- What trends do you noticed for the inpatient beds used overall as compared to inpatient beds used for COVID cases and Influenza cases? 
- What trends do you notice in the total inpatient beds used for COVID cases over time? 
- Is there a specific month or period of time when the total inpatient beds used for COVID significantly reduced? Was this a trend that held true for each age group? 
- What trends do you notice with respect to the total inpatient beds for COVID by specific age groups and time? 
- What trends do you notice in the vaccination status of healthcare personnel over time for hospitals, cities, states? Did any hospitals, cities, or states get vaccinated more slowly as compared to the general trend over time? 
- Which hospitals have had a significant increase in total inpatient beds used for COVID cases over time? 
- Which hospitals have had a significant fluctuation in total inpatient beds used for COVID cases over time? 
- Design and build a dashboard that helps a hospital understand how to better manage and prepare their resources (inpatient beds, nurses, docs). 



## CONTRIBUTORS

- [Juhi Choubey](https://github.com/jchoubey)
- [Tharun Kumar Reddy](https://github.com/TharunKumarReddy5) 
- [Avinash]()
- [Shrusti Ghela](https://github.com/shrusti-ghela)
- [Anuhya Bhagavatula](https://github.com/anuhyabs)
