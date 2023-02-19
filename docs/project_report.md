# PROJECT REPORT

## PROBLEM STATEMENT

The COVID-19 pandemic has put extreme stress on the health care workforce in the United States, leading to workforce shortages as well as increased health care worker burnout, exhaustion, and trauma. These pandemic-related challenges have taken place in a context of significant preexisting workforce shortages and maldistribution, as well as in a workforce where burnout, stress, and mental health problems (including an ongoing risk of post-traumatic stress disorder) were already significant problems. This has made it critical for the United States government and hospitals to better manage and prepare their resources and healthcare personnel. 

The aim of this project is to identify trends present in the data, define a metric to identify COVID burden of a hospital and predict the bed usage for 12 weeks based on the city/state specified.

## DATASET

### Description
The dataset provides facility-level data for hospital utilization aggregated on a weekly basis (Friday to Thursday). These are derived from reports with facility-level granularity across two main sources: (1) HHS TeleTracking, and (2) reporting provided directly to HHS Protect by state/territorial health departments on behalf of their healthcare facilities. The hospital population includes all hospitals registered with Centers for Medicare & Medicaid Services (CMS) as of June 1, 2020. It includes non-CMS hospitals that have reported since July 15, 2020. It does not include psychiatric, rehabilitation, Indian Health Service (IHS) facilities, U.S. Department of Veterans Affairs (VA) facilities, Defense Health Agency (DHA) facilities, and religious non-medical facilities.

### Data Dictionary



## DATA CLEANING

The data file had some issues such as unclean data and missing values. We have performed certain data cleaning steps in order to bring the data to more usable manner.

1. For averages, calculations are based on the number of values collected for a given hospital in that collection week. Suppression is applied to the file for sums and averages less than four (4). In these cases, the field will be replaced with “-999,999”.
1. Cleaned 

## DATA ANALYSIS & VISUALIZATION

- **What trends do you noticed for the inpatient beds used overall as compared to inpatient beds used for COVID cases and Influenza cases?** 
    
    The data for COVID cases is much more than the data for Influenza.Percentage of inpatient beds used for patients of both confirmed COVID and influenza. It can be seen from the graph the inpatient bed use was the highest around November 2020. The inpatient bed usage reduces significantly but there are occasional peaks in January 2022 and November-December 2022.

- **What trends do you notice in the total inpatient beds used for COVID cases over time?** 
    
    ![q2](https://github.com/TharunKumarReddy5/optimizers-dubstech-2023/tree/main/plots/q2.png?raw=true)
    
    The graph a number of spikes and dips in the graph. The highest peak is around January 2021 and then again at Spetember 2021 and January 2022.

- **Is there a specific month or period of time when the total inpatient beds used for COVID significantly reduced? Was this a trend that held true for each age group?**

    Significant dip is noticed between January - March in 2021 and 2022.

- **What trends do you notice with respect to the total inpatient beds for COVID by specific age groups and time?**
    
    The age groups 40-59 and 60+ seem to be similar to have a similar trend to the overall trend with peaks around Jan 2021, Aug 2021 and Jan 2022 but the age group 0-19 is significantly different from the overall trend and other age groups. As we can see in the image above, the peaks for this age group are around Jan 2022 and July 2022. The age group 20-39 is somewhat closely aligning with the overall trend except the first peak of Jan 2021.
    
- What trends do you notice in the vaccination status of healthcare personnel over time for hospitals, cities, states? Did any hospitals, cities, or states get vaccinated more slowly as compared to the general trend over time? 
- Which hospitals have had a significant increase in total inpatient beds used for COVID cases over time? 
- Which hospitals have had a significant fluctuation in total inpatient beds used for COVID cases over time? 

- Design and build a dashboard that helps a hospital understand how to better manage and prepare their resources (inpatient beds, nurses, docs). 

    Link to dashboard: [Tableau dashboard](https://public.tableau.com/app/profile/tharun.kumar.reddy5213/viz/OptimizersHospitalBedsDashboard/AnalysisDashboard?publish=yes).

## METRIC DESIGN
Metric to rank the COVID burden a hospital is experiencing.


## MODELLING
Machine Learning Problem to predict the `"inpatient_beds_used_covid_7_day_sum"` values for the next 12 weeks  for a **specific state** selected.

**Step 1:** 128 Features classified into 3 buckets:

- 7 day sum
- 7 day coverage
- 7 day average

Out of the 3, the focus was on 7 day sum features with a base understanding that it is most relevant to the target variable. Instead of using 7 day average, the latter metric can be derived from 7 day sum and 7 day coverage. This human centered decision helped in reducing the number of variables to start working with.


**Step 2:** Feature Cross Correlation:
Trend visualization revealed that majority of 7 day sum features are highly correlated. Buckets were created for these features and only 1 feature out of each bucket was selected to proceed. This evaluation too helped greatly in eliminating feature redundancy.


**Note:** Since we are working with multivariate time series forecasting, we considered 2 different approaches:
- Traditional multivariate Time-series analysis using VAR
- Panel Data Regression (considering state/city/hospital_pk/is_metro_micro variable as xcovariates)

Due to time-constraint, we were only able to develop a VARMAX model to forecast 12 week target value per state. Addressing the same problem with Panel Data Regression would be very interesting future scope.


**Step 3:** Multivariate Time-Series Stationarity corrected:
A brief check to observe stationarity in multiple time series was performed using adfuller test. It was observed that most of the tim eseries were stationary (based off on p-values). No further change was made.


**Step 4:** Feature Granger-Causality measured:
One of the most interesting things with multivariate time-series analysis is to check if one time series is "dependent" on another. And if so, what lag of the latter time series is most significant in predicting the former. This was verified using granger-causality test between the target variable and the independent selected features.


**Step 5:** (Cross-Validation) Multivariate Vector Auto Regression to get maxlag:
VAR() function from statsmodels package has a great method - select_order - that provides a collection of AIC values (and other performance metrics such as BIC too) for a range of lags and also identifies the maximum lag at which AIC value is minimum (most optimal). Using this, we arrived at AR = 4 measure for our model.


**Step 6:** VARMAX(4,0) model finalized at state-level:
Finally, a function was written to encapsulate VARMAX(4,0) training model and was then executed to forecast teh target value for 12 upcoming weeks.

