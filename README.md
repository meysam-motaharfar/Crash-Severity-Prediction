Predicting Crash Severity in Baton Rouge  
================================================

AUTHORS: Meysam Motaharfar and Mohammad Ali Izadifar

### Table of Contents
1. [Project Overview](#Project-Overview)
2. [Dataset Overview and Feature Dictionary](#Dataset-Overview-and-Feature-Dictionary)
3. [Data Preprocessing and Visulaization](#Data-Preprocessing-and-Visualization)
4. [Model Development](#Model-Development)
5. [Results and Conclusion](#results-and-conclusion)
6. [Challenges and Future Directions](#Challenges-and-Future-Directions)

## Project Overview

Traffic accidents remain a significant public safety challenge, necessitating predictive models to evaluate crash severity effectively. The primary goal of this project is to develop a predictive model that accurately assesses the severity of vehicle crashes. This study employs various machine learning techniques to predict crash severity based on multiple factors, including road conditions, vehicle conditions, traffic conditions, and driver attributes. The dataset, sourced from detailed traffic accident records, undergoes comprehensive exploratory data analysis to identify key predictors of crash severity. To address class imbalance in the data, techniques such as SMOTE (Synthetic Minority Oversampling Technique) and Random Over Sampling are implemented. A flexible and generalized pipeline was developed to automate data preprocessing and predictions, including the imputation of missing values, encoding the categorical features, samplers, and classifiers. The findings can be summarized as follows: 1) Logistic Regression emerged as a reliable baseline model due to its balanced performance and robustness in handling class imbalance, 2) Random Forests, as an ensemble method, showed promise, but required careful hyperparameter tuning to avoid overfitting, and 3) more complex models, like Multilayer Perceptrons, exhibited varying degrees of overfitting, indicating the need for further refinement. The developed model can serve as a crucial tool for policymakers, traffic management authorities, and public safety officials by enabling proactive interventions to improve road safety.

<b> Key Performance Indicator: </b>
The model's effectiveness is evaluated based on its recall performance, which measures the model's ability to correctly identify severe crashes from the total number of actual severe crashes. A high recall indicates that the model successfully captures most of the critical cases, ensuring fewer severe accidents are missed.

## Dataset Overview and Feature Dictionary

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


## Data Preprocessing and Visualization

Before model development, several preprocessing steps were applied to ensure data quality. This included:
- **Imputation of Missing Values**: Numerical features were imputed using the mean, and categorical features were imputed with a constant value.
- **Encoding**: Categorical variables were encoded using techniques like One-Hot Encoding.
- **Sampling**: To address class imbalance, techniques like SMOTE and Random Over Sampling were employed.

### Visualization Example
![Crash Severity Conditions](images/The_number_of_crashes_for_different_severity_conditions.png)
This visualization depicts the distribution of crashes by severity level.

## Exploratory Data Analysis (EDA)

Exploratory Data Analysis (EDA) was conducted to uncover patterns and relationships within the dataset. We performed both **univariate** and **bivariate** analyses to understand the distribution of variables and their correlations with crash severity. For example:
- **Univariate Analysis**: Revealed that the majority of crashes resulted in 'No Injury' incidents.
- **Bivariate Analysis**: Showed strong correlations between crash severity and factors such as road conditions and driver age.

Key observations from EDA include:
- **Alcohol involvement** is significantly associated with higher severity levels (e.g., fatal and severe crashes).
- **Older vehicles (15-20 years old)** are more likely to be involved in severe and fatal crashes.

### Visualization Example
Here’s a heatmap of correlations between features and crash severity:
![Correlation Heatmap](images/correlation_heatmap.png)

## Feature Engineering

Feature engineering was an essential part of improving model performance. New features were derived from existing data to capture additional information:
- **Vehicle Age**: Calculated as `CAR_AGE = Crash_Year - Vehicle_Year`.
- **Interaction Terms**: Features such as **Alcohol** and **Lighting Conditions** were combined to create interaction terms, helping to predict severe crash outcomes.

Final feature set:
- **Road and Environmental Factors**: Road condition, surface type, weather conditions, lighting.
- **Vehicle and Driver Characteristics**: Vehicle condition, driver age, alcohol/drug involvement.
- **Traffic Conditions**: Type of traffic control at the crash site.

  
## Model Development

Multiple machine learning models were developed to predict crash severity, including:
- Logistic Regression
- Decision Trees
- Random Forests
- K-Nearest Neighbors
- Multilayer Perceptrons
- Support Vector Classifiers

A generalized pipeline was created to automate the selection of encoders, samplers, and classifiers, streamlining the experimentation process.

## Hyperparameter Tuning

Each model underwent hyperparameter tuning using techniques like **GridSearchCV** to optimize their performance. For example:
- **Logistic Regression**: We tuned the regularization strength (C parameter).
- **Random Forest**: Hyperparameters such as the number of trees, maximum depth, and minimum samples split were optimized.
  
Here's an example of hyperparameter tuning for Logistic Regression:

```python
from sklearn.linear_model import LogisticRegression
from sklearn.model_selection import GridSearchCV

# Logistic Regression with hyperparameter tuning
classifier = LogisticRegression(class_weight='balanced', random_state=42)
param_grid = {'C': [0.001, 0.01, 0.1, 1, 10]}
grid_search = GridSearchCV(classifier, param_grid, cv=5, scoring='recall_macro')
grid_search.fit(X_train, y_train)

## Results and Conclusion

<div align="center">
    <img width="700" alt="Model Performance" src="https://github.com/user-attachments/assets/fc893868-badd-4d4b-a67f-71fc346dadd8">
</div>

Key findings:
- **Logistic Regression** performed well, achieving a recall score of 0.431 on the test set.
- **Random Forests** had the highest overall performance after tuning, with a recall score of 0.452, but required careful adjustment to avoid overfitting.
- Complex models like **K-Nearest Neighbors** and **Multilayer Perceptrons** showed varying degrees of overfitting, requiring further refinement.

## Challenges and Future Directions

Some challenges faced during this project included:
- **Class Imbalance**: Most crashes were non-severe, making it difficult to predict the minority classes (severe and fatal crashes).
- **Overfitting**: Complex models like Multilayer Perceptrons and Random Forests showed signs of overfitting, indicating the need for more advanced regularization techniques.
  
Future work will focus on:
1. **Improving Feature Engineering**: Creating more meaningful features, especially interactions between variables, to improve model accuracy.
2. **Advanced Modeling**: Exploring deep learning models and hierarchical classification approaches to handle the class imbalance more effectively.
3. **Real-Time Prediction**: Implementing real-time predictive analytics for crash severity to support traffic management systems.

   
