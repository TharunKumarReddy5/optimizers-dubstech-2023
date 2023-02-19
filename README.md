# Dubstech 4th Datathon Code Repository

## PROBLEM STATEMENT

The COVID-19 pandemic has put extreme stress on the health care workforce in the United States, leading to workforce shortages as well as increased health care worker burnout, exhaustion, and trauma. These pandemic-related challenges have taken place in a context of significant preexisting workforce shortages and maldistribution, as well as in a workforce where burnout, stress, and mental health problems (including an ongoing risk of post-traumatic stress disorder) were already significant problems. This has made it critical for the United States government and hospitals to better manage and prepare their resources and healthcare personnel. 

The aim of this project is to identify trends present in the data, define a metric to identify COVID burden of a hospital and predict the bed usage for 12 weeks based on the state specified.  

## DATASET

Link: https://healthdata.gov/stories/s/nhgk-5gpv

#### Description
The dataset provides facility-level data for hospital utilization aggregated on a weekly basis (Friday to Thursday). These are derived from reports with facility-level granularity across two main sources: (1) HHS TeleTracking, and (2) reporting provided directly to HHS Protect by state/territorial health departments on behalf of their healthcare facilities. The hospital population includes all hospitals registered with Centers for Medicare & Medicaid Services (CMS) as of June 1, 2020. It includes non-CMS hospitals that have reported since July 15, 2020. It does not include psychiatric, rehabilitation, Indian Health Service (IHS) facilities, U.S. Department of Veterans Affairs (VA) facilities, Defense Health Agency (DHA) facilities, and religious non-medical facilities.

### Data Dictionary

Please find the detailed Data Dictionary [here](https://docs.google.com/spreadsheets/d/1A4rVaa1xtjPEzdTpjK58IFEsyH971xoKUanahzRE-i8/edit#gid=0).

## DOCUMENTATION
Link to the **[Project Report](https://github.com/TharunKumarReddy5/optimizers-dubstech-2023/tree/main/docs/project_report.md)**.

## DASHBOARD
Here is a link to out **[Tableau dashboard](https://public.tableau.com/app/profile/tharun.kumar.reddy5213/viz/OptimizersHospitalBedsDashboard/AnalysisDashboard?publish=yes)**.
![tableau](https://github.com/TharunKumarReddy5/optimizers-dubstech-2023/blob/main/tableau/tableau.jpg?raw=true)

## TASKS

1. **Machine Learning Modelling** to predict the `"inpatient_beds_used_covid_7_day_sum"` values for the next 12 weeks  for a specific state selected.

![model](https://github.com/TharunKumarReddy5/optimizers-dubstech-2023/blob/main/plots/model.jpg?raw=true)
**RMSE across all states is 3342.**

Detailed explanation **[here](https://github.com/TharunKumarReddy5/optimizers-dubstech-2023/blob/main/docs/project_report.md#modelling)**.

2. **Metric** to rank the COVID burden a hospital is experiencing.

![metric](https://github.com/TharunKumarReddy5/optimizers-dubstech-2023/blob/main/plots/metric.jpg?raw=true)

Hosiptal Burden Index based on Intital weights:
![metric_op](https://github.com/TharunKumarReddy5/optimizers-dubstech-2023/blob/main/plots/metric_op.jpg?raw=true)

Detailed explanation **[here](https://github.com/TharunKumarReddy5/optimizers-dubstech-2023/blob/main/docs/project_report.md#metric-design)**.

3. **Data Analysis + Data Visualization**

- **What trends do you notice in the total inpatient beds used for COVID cases over time?** 
    
    ![q2](https://github.com/TharunKumarReddy5/optimizers-dubstech-2023/blob/main/plots/q2.png?raw=true)
    
    The graph a number of spikes and dips in the graph. The highest peak is around January 2021 and then again at Spetember 2021 and January 2022.
- **What trends do you notice with respect to the total inpatient beds for COVID by specific age groups and time?**
    
    ![q3](https://github.com/TharunKumarReddy5/optimizers-dubstech-2023/blob/main/plots/q3.jpg?raw=true)

    The age groups 40-59 and 60+ seem to be similar to have a similar trend to the overall trend with peaks around January 2021, August 2021 and January 2022 but the age group 0-19 is significantly different from the overall trend and other age groups. As we can see in the image above, the peaks for this age group are around January 2022 and July 2022. The age group 20-39 is somewhat closely aligning with the overall trend except the first peak of January 2021.

Detailed explanation **[here](https://github.com/TharunKumarReddy5/optimizers-dubstech-2023/blob/main/docs/project_report.md#data-analysis--visualization)**.

## CONTRIBUTORS

- [Juhi Choubey](https://github.com/jchoubey)
- [Tharun Kumar Reddy](https://github.com/TharunKumarReddy5) 
- [Avinash Vaka](https://github.com/avinash-vaka)
- [Shrusti Ghela](https://github.com/shrusti-ghela)
- [Anuhya Bhagavatula](https://github.com/anuhyabs)