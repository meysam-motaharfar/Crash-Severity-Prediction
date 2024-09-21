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
| Crash_ID            | Unique identifier for each crash                               | Categorical |
| Crash_Severity      | Severity level of the crash (e.g., minor, severe, fatal)        | Categorical |
| Date                | Date of the crash                                              | Date        |
| Time                | Time of the crash                                              | Time        |
| Latitude            | Latitude of the crash location                                 | Numerical   |
| Longitude           | Longitude of the crash location                                | Numerical   |
| Weather_Condition   | Weather condition at the time of the crash                     | Categorical |
| Road_Surface        | Condition of the road surface (e.g., dry, wet, icy)             | Categorical |
| Vehicle_Type        | Type of vehicle involved (e.g., car, truck, motorcycle)         | Categorical |
| Driver_Age          | Age of the driver involved in the crash                        | Numerical   |
| Alcohol_Involved    | Whether alcohol was involved (True/False)                      | Boolean     |
| Speed_Limit         | Speed limit at the location of the crash                       | Numerical   |
| Crash_Location      | Location description (e.g., intersection, highway)             | Categorical |
| Light_Condition     | Lighting conditions (e.g., day, night, dawn)                   | Categorical |
| Road_Type           | Type of road (e.g., urban, rural, freeway)                     | Categorical |
                                                                   |                   |                   

## Modelling Overview


## Results and Conclusion 


### Future Iterations:



