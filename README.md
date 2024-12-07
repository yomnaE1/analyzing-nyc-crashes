# analyzing-nyc-crashes

**Collaborated with another person to finish this project. However, names were removed to respect privacy. Also, I uploaded an image of the accident map because it does not show up in the .ipynb file**

<ins> Table of Contents </ins>
- [Abstract](#abstract)
- [Problem Statement](#problem-statement)
- [Introduction](#introduction)
- [Data Ingestion](#data-ingestion)
- [Data Cleaning](#data-cleaning)
- [Data Transformation](#data-transformation)
- [Feature Engineering](#feature-engineering)
- [Exploratory Data Analysis](#eda)
- [Machine Learning Models](#ml-models)
- [Summary of Findings](#summary)
- [References](#references)

# Abstract

The "Motor Vehicle Collisions - Crashes" dataset includes details about crash events that have occured in New York city since 2012. The dataset is updated weekly and contains information about the crash date, crash time, zipcode, latitude, longitude, street names of each crash. Additionally, the dataset includes details such as the number of pedestrians, cyclists, or motorists who have been injured, contributing factors of each veichle causing the crash, and the types of veichles causing the crash. This dataset is important because it can help state government agencies, researchers, and transportation planners develop strategies to help improve traffic safety in other large cities in the US. Additionally, this dataset can be useful for veichle manufacturers who can update a veichle's safety features based on the types of crashes and veichles most involved in the crashes.

# **Raw Data Source**

https://catalog.data.gov/dataset/motor-vehicle-collisions-crashes

# **Project Goals**

 The goal of this project is to analyze the causes of crahses in New York City, and based on that analysis build three machine learning models, to accurately predict the number of persons killed in New York City, which will provide insights for future city planners that could help improve traffic safety in other large cities, to prevent these deaths.

 We aim to achieve this goal by performing the following steps:

 * Data Collection
 * Data Cleaning and Preprocessing
 * Data Visulaization
 * Exploratory Data Analysis
 * Machine Learning Models

# Problem Statement

According to the General Services Administration (GSA), there is "an average of 6.4 million car crashes occur in the U.S. each year" (*What are the odds*, 2024). Of those, there are approximately 43,000 fatal crashes that occur yearly in the US (Moore & Gollub, 2024). Moreover, major American cities, such as New York City, have a 20% relative collision likelihood (Bieber & Ramirez, 2023). These statistics are concering because car crashes have been shown to cause a large number of deaths and injuries, many of which could have been prevented. Thus, the goal of this data science project is to analyze vehicle crashes in a New York City to gain an understanding as to why there are many collisions and car crashes that could be occuring in major US cities. Based on this analysis, the project will also consist of an evaluation of three machine learning models to determine which one can accurately predict the number of persons killed in New York City. This analysis and modeling will be useful for future urban planning and policies, such as enforced speed limits, all of which can help reduce the number of deaths caused by vehicle crahses and collisions.

# Introduction

Vehicle collisions and crashes are a significant concern in urban areas, particularly in densely populated cities like New York City. According to the General Services Administration (GSA), an average of 6.4 million car crashes occur in the U.S. each year, with approximately 43,000 fatal crashes annually. Major American cities, such as New York City, have a 20% relative collision likelihood. These statistics highlight the urgent need to understand the factors contributing to these incidents to develop effective strategies for improving traffic safety.

# Data Ingestion

The purpose of this step was to load the dataset into Google Colab and observe the given data in the dataset to determine next steps for data cleaning. In this step, we identified the names of each feature as well as their datatypes. Additionally, we determined whether null values exist in the dataset, which will be later processed in the data cleaning stage.

# Data Cleaning

The purpose of the data cleaning step is to remove and fix null values and potential outliers in our dataset. This will help with a more accurate data analysis later on.

# Data Transformation

# Feature Engineering

Feature Creation: To enrich the dataset and facilitate more robust analyses, new features were generated. These include temporal attributes such as 'year', 'month', 'day_of_week', and 'hour'. Additionally, the binary indicator 'is_weekend' was introduced to distinguish between weekends and weekdays. Critical outcome variables, 'TOTAL INJURED' and 'TOTAL KILLED', were also incorporated to enhance the predictive capabilities of the dataset.

# Exploratory Data Analysis

The purpose of the Exploratory Data Analysis step was to understand the causes crashes in New York City.

# Machine Learning Models

Three machine learning models will be used here: Linear Regression, Logistic Regression, and Random Forest. The reason why these three models were used was to predict a numerical value based on the features, since the 'NUMBER OF PERSONS KILLED' column is numerical. All three of these models are usually used in classification and regression tasks, and our problem is regression. Since most of the features are all equally weakly correlated to the 'NUMBER OF PERSONS KILLED,' we decided to select the features of 'year', 'month,' 'hour,' 'is_weekend,' 'day_of_week_num,' and 'time_of_day_num' to predict the label of 'NUMBER OF PERSONS KILLED.' This is because the most distracted and inattentive driving occurs after leaving from work (hour 16) on Fridays, as seen from the Expolartory Data Analysis Section. However, although the location ('LATITUDE,' 'LONGITUDE,' and 'BOROUGH') for the most fatal crahes and injuries is weakly correlated to the 'NUMBER OF PERSONS KILLED,' distracted driving can often occur at any location, even if the borough is slightly less crowded in population size. Considering that all of the boroughs shown in the Exploratory Data Analysis have large populations, with minimal differences in the numercial value, features such as the time of day, week, year, month, and hour are shown to affect the number of cars on the road, and most people are in veichles when they leave or arrive from work.

# Summary of Findings

Driver Inattention/Distraction: This is the most common contributing factor to crashes, accounting for a significant portion of incidents. The most driver inattention/distraction occurs in the afternooons on Friday, when most people leave from work.

High-Risk Areas: Brooklyn and Queens have the highest number of injuries and fatalities, likely due to their dense populations.

Features selected for models: Although Brooklyn and Queens have some of the most dense population sizes, the features of the time of day, year, hour, month, and day of the week have been used since they have the most affect on the number of cars congested on the road (since most people are in cars when they leave or first arrive to work), and they affect distracted driving/inattention (since people are usually tired and distracted when they come home from work).

Predictive Accuracy: The models, including Linear Regression, Logistic Regression, and Random Forest Classifier, have been effective in predicting the number of fatalities based on the various selected features of time of day, year, hour, month, and day of the week for class 0.0. However, it could have done better with classes 1.0-4.0.

Significance: These insights can help state government agencies, researchers, and transportation planners develop targeted strategies to improve traffic safety and reduce the number of vehicle collisions in urban areas. Additionally, vehicle manufacturers can use this information to enhance safety features in their vehicles, ultimately contributing to safer roads.

Feedback for city planners based on the results: Enforce stricter rules to limit distracted driving, especially during the time when people leave and go to work.

Feedback for vehicle manufacturers: Create cars that are safter for the road. People's lives matter more than the saving on costs by including less features that reduce accidents.

Future Work:

- Undersampling the majority class of 0.0 for the machine learning models to (hopefully) more accurately predict the number of deaths for all cases, based on the features provided.
- Utilize AI tools, such as Open source AI models, to predict the number of deaths from the crashes.

# References

- Bieber, C., & Ramirez, A. (2023, October 25). The cities where you’re most likely to get in a car accident. Forbes. https://www.forbes.com/advisor/legal/auto-accident/cities-most-car-accidents/

- Jones, B. (2024, November 8). What types of cars cause the most accidents?. Jones Law Group - Your Lawyers for Life. https://jlgtampabay.com/car-accident/cars-that-cause-the-most-accidents/#:~:text=Sedans%20are%20among%20the%20most,among%20sedan%20drivers%20and%20passengers.

- Moore, T., & Gollub, H. (2024, January 16). Fatal car crash statistics 2024. USA Today. https://www.usatoday.com/money/blueprint/auto-insurance/fatal-car-crash-statistics/#:~:text=There%20are%20nearly%2043%2C000%20fatal,accidents%20in%20the%20United%20States.

- Moretti, R., & Kelly, C. B. (2024, July 2). News release: New York traffic fatalities increased 15 percent over past five years... TRIP. https://tripnet.org/reports/addressing-americas-traffic-safety-crisis-new-york-news-release-07-02-2024/

- Population of NYC by borough in 2024. Metropolis Moving. (2024, February 2). https://metropolismoving.com/blog/new-york-city-population-in-2024/

- What are the odds of getting in a car crash?. Law Offices of Bryan Musgrave. (2024, June 24). https://www.bryanmusgrave.com/what-are-the-odds-of-getting-in-a-car-crash/#:~:text=The%20General%20Services%20Administration%20(GSA,car%20accidents%20in%20their%20lives.
