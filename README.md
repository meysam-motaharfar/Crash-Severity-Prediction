Predicting Crash Severity in Baton Rouge  
================================================

AUTHORS: Meysam Motaharfar and Mohammad Ali Izadifar

### Table of Contents
1. [Project Overview](#project-overview)
2. [Data Preprocessing](#data-gathering-and-preprocessing)
3. [Data Visualization](#data-visualization)
5. [Modelling](#modelling-overview)
6. [Results and Conclusion](#results-and-conclusion)

## Project Overview
The primary aim of this analysis is to develop a predictive model that can accurately assess the severity of vehicle crashes. This model serves as a crucial tool for policymakers, traffic management authorities, and public safety officials, enabling them to implement more targeted interventions to improve road safety. By predicting crash severity, resources can be allocated more efficiently, and preventative measures can be tailored to specific risk factors associated with severe accidents. Predictive analytics in traffic safety can help mitigate the consequences of traffic accidents by providing timely insights and facilitating proactive measures.

<b> Key Performance Indicator: </b>
How efficiently does the model predict the crash severity compared to actuall severities?

## Data set description

The dataset for this project was sourced from the Louisiana Department of Transportation and Development (LA DOTD), covering detailed records of traffic accidents from 2016 to 2021. Each record in the dataset provides comprehensive details about each traffic accident, including geographic coordinates, road conditions, vehicle characteristics, driver demographics, environmental factors, and the severity of the crash. The dataset contains approximately 49,336 records with 54 features, ensuring a rich basis for analysis. Among these 54 features 30 of them (24 categorical, 3 numerical, and 3 boolean) were selected for the purpose of this study. Here is the dictionary for data set: 

| Feature Name        | Description                                                    | Data Type   |
|---------------------|----------------------------------------------------------------|-------------|
| ROAD_COND_CD          | Unique identifier for each crash                               | Categorical |
| ROAD_TYPE_CD      | Severity level of the crash (e.g., minor, severe, fatal)        | Categorical |
| DSURF_COND_CD                | Date of the crash                                              | Date        |
| SURF_TYPE_CD                | Time of the crash                                              | Time        |
| PAVEMENT_TYPE            | Latitude of the crash location                                 | Numerical   |
| SHOULDER_TYPE_PRI           | Longitude of the crash location                                | Numerical   |
| PRI_ROAD_TYPE   | Weather condition at the time of the crash                     | Categorical |
| ROAD_REL_CD        | Condition of the road surface (e.g., dry, wet, icy)             | Categorical |
| ALIGNMENT_CD        | Type of vehicle involved (e.g., car, truck, motorcycle)         | Categorical |
| Driver_Age          | Age of the driver involved in the crash                        | Numerical   |
| ACCESS_CNTL_CD  | Whether alcohol was involved (True/False)                      | Boolean     |
| INTERSECTION        | Speed limit at the location of the crash                       | Numerical   |
| VEH_COND_CD      | Location description (e.g., intersection, highway)             | Categorical |
| VEH_LIGHTING_CD     | Lighting conditions (e.g., day, night, dawn)                   | Categorical |
| VEH_TYPE_CD           | Type of road (e.g., urban, rural, freeway)                     | Categorical |
| DR_SEX          | Unique identifier for each crash                               | Categorical |
| ALCOHOL      | Severity level of the crash (e.g., minor, severe, fatal)        | Categorical |
| DRUGS                | Date of the crash                                              | Date        |
| LIGHTING_CD                | Time of the crash                                              | Time        |
| WEATHER_CD            | Latitude of the crash location                                 | Numerical   |
| PEDESTRIAN           | Longitude of the crash location                                | Numerical   |
| TRAFF_CNTL_CD   | Weather condition at the time of the crash                     | Categorical |
| TRAFF_CNTL_COND_CD       | Condition of the road surface (e.g., dry, wet, icy)             | Categorical |
| VIOLATIONS_CD        | Type of vehicle involved (e.g., car, truck, motorcycle)         | Categorical |
| VISION_OBSCURE_CD         | Age of the driver involved in the crash                        | Numerical   |
| ACCESS_CNTL_CD  | Whether alcohol was involved (True/False)                      | Boolean     |
| MAN_COLL_CD       | Speed limit at the location of the crash                       | Numerical   |
| DR_AGE      | Location description (e.g., intersection, highway)             | Categorical |
| LATITUDE           | Type of road (e.g., urban, rural, freeway)                     | Categorical |

## Modelling Overview


## Results and Conclusion 


### Future Iterations:



