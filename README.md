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

The primary goal of this project is to develop a predictive model that accurately assesses the severity of vehicle crashes. Traffic accidents remain a significant public safety challenge, necessitating predictive models to evaluate crash severity effectively. The developed model can serve as a crucial tool for policymakers, traffic management authorities, and public safety officials by enabling proactive interventions to improve road safety.

### Methodology

In this study, various machine learning techniques were employed to predict crash severity based on multiple factors, such as road conditions, vehicle conditions, traffic conditions, and driver attributes. The dataset, sourced from detailed traffic accident records, underwent comprehensive exploratory data analysis to identify key predictors of crash severity.

The following models were tested:

- Logistic Regression
- Decision Trees
- Random Forests
- K-Nearest Neighbors
- Support Vector classifier
- Multilayer Perceptrons

To address class imbalance in the data, techniques such as SMOTE (Synthetic Minority Over-sampling Technique) and Random Over Sampling were implemented. A flexible and generalized pipeline was developed to automate data handling, including the imputation of missing values, preprocessing, and the selection of different encoders, samplers, and classifiers.


<b> Key Performance Indicator: </b>
How efficiently does the model predict the crash severity compared to actuall severities?

## Data set description

The dataset for this project was sourced from the Louisiana Department of Transportation and Development (LA DOTD), covering detailed records of traffic accidents from 2016 to 2021. Each record in the dataset provides comprehensive details about each traffic accident, including geographic coordinates, road conditions, vehicle characteristics, driver demographics, environmental factors, and the severity of the crash. The dataset contains approximately 49,336 records with 54 features, ensuring a rich basis for analysis. Among these 54 features 30 of them (24 categorical, 3 numerical, and 3 boolean) were selected for the purpose of this study. Here is the dictionary for data set: 

| Feature Name        | Description                                                    | Data Type   |
|---------------------|----------------------------------------------------------------|-------------|
| SEVERITY_CD         | The severity of crashes (fatal, severe, moderate, complaint and no injury)                             | Categorical |
| ROAD_COND_CD        | Road conditions at the time of the crash (e.g., bumps, holes)                      | Categorical |
| ROAD_TYPE_CD        | Type of road where the crash occurred (e.g., one way road, two-way road with a physical separation)                         | Categorical |
| SURF_COND_CD        | Surface condition of the road (e.g., dry, wet, ice)                               | Categorical |
| SURF_TYPE_CD        | Type of road surface (e.g., dirt, gravel, concrete)                                          | Categorical |
| PAVEMENT_TYPE       | Type of pavement on the road (gravel, graded, brick)                                  | Categorical |
| SHOULDER_TYPE_PRI   | Type of shoulder on the road                                   | Categorical |
| PRI_ROAD_TYPE       | Primary road type at the crash location (e.g, street, highway)                       | Categorical |
| ROAD_REL_CD         | Relation of crash to the road (e.g., shoulder, median)                 | Categorical |
| ALIGNMENT_CD        | Road alignment (e.g., straight, curve)                         | Categorical |
| ACCESS_CNTL_CD      | Type of access control at the crash location                   | Categorical |
| VEH_COND_CD         | Condition of the vehicle involved in the crash (defective break, defective headlights)                | Categorical |
| VEH_LIGHTING_CD     | Vehicle lighting condition during the crash                    | Categorical |
| VEH_TYPE_CD         | Type of vehicle involved in the crash (e.g., SUV, truck, school bus)                         | Categorical |
| DR_SEX              | Driver's sex                                                   | Categorical |
| LIGHTING_CD         | Lighting conditions during the crash (e.g, daylight, dark, dusk)                          | Categorical |
| WEATHER_CD          | Weather conditions at the time of the crash (e.g, clear, cloudy, rain, foggy)                  | Categorical |
| TRAFF_CNTL_CD       | Type of traffic control at the crash site (e.g., stop sign, yield sign, red signal on)                     | Categorical |
| TRAFF_CNTL_COND_CD  | Condition of the traffic control at the crash site             | Categorical |
| VIOLATIONS_CD       | Any traffic violations related to the crash (e.e., failure to yield, failure to signal)                    | Categorical |
| VISION_OBSCURE_CD   | Factors that obscured vision (e.g., rain, building, parked vehicles)            | Categorical |
| ACCESS_CNTL_CD      | Access control at the location of the crash                    | Categorical |
| MAN_COLL_CD         | Manner of collision (e.g., head-on, rear-end)                  | Categorical |
| DR_AGE              | Age of the driver involved in the crash                        | Numerical   |
| LATITUDE            | Latitude of the crash location                                 | Numerical   |
| LONGITUDE           | Longitude of the crash location                                | Numerical   |
| PEDESTRIAN          | Whether pedestrians were involved                              | Boolean     |
| INTERSECTION        | Whether the crash occurred at an intersection                  | Boolean |
| ALCOHOL             | Whether alcohol was involved                                   | Boolean     |
| DRUGS               | Whether drugs were involved                                    | Boolean     |


## Modelling Overview


## Results and Conclusion 


### Future Iterations:



