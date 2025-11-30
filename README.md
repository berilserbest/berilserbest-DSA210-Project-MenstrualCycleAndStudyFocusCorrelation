# DSA210 Project - The Relationship Between Menstrual Cycle Phases and Study Focus in Female Students in Turkey

## Table of Contents
- [Project Overview](#project-overview)
- [Motivation](#motivation)
- [Data Sources and Dataset Description](#data-sources-and-dataset-description)
- [Data Collection and Preprocessing](#data-collection-and-preprocessing)
- [Data Analysis](#data-analysis)

# Project Overview
I am Beril Nur Serbest, a Computer Science and Engineering student in Sabancı University. I am making  this project for DSA210 couse. This study focuses on examining how different phases of menstrual cycle influence study focus among female students in Turkey. By analyzing self tracked data collected with Google Forms, this study aims to observe cognitive focus and learning efficiency patterns accross different menstrual phases.

# Motivation 
Menstrual cycle periods can effect physical activity levels, mood and cognitive performance due to hormonal fluctuations and physical pains which can influence the study habbits and focus of a person. Understanding the relation between menstrual cycle and stdy focus can help female strudents: 
- Optimize productivity and improve study efficiency by taking hormonal fluctuations into consideration.
- Schedule their academic tasks during high-focus phases to decrease the amount of time they spend working on the tasks
- Contribute to data-driven insights on women’s cognitive performance in Turkey

# Data Sources and Dataset Description
This project relies on self-collected data from female students in Turkey. The Google Forms and Beije application used to colect the related data. The dataset includes following information: 
- cycle_start : the starting date of the menstrual cycle
- cycle_end : the ending date of the menstrual cycle
- period_length : avarega menstrula period length (will be calculated based on the cycle_start and cyclye_end data of the participant)
- painkiller_usage : the data indicating wheter the participant use painkiller during the menstrual period
- study_hours_daily : the daily study duration of the participant (hours)
- exam_period : the data indicating wheter is it the exam period or not
- coffee_consumption : the data indicating wheter the participant consumes coffe during the menstrual cycle period.

# Data Collection and Preprocessing 
## Data Collection:
Participants will record their study hours, coffee consumption status, painkiller usage status and wheter it is exam period or not daily, through Google Forms. The cycle_start and cycle_end information will be collected via an menstrual cycle application called Beije, then the period_length will be calculated depending on these information. Data will be collected for at least one full menstrual cycle of the participant (ideally 4–6 weeks). The exam period, coffe consumption and painkiller usage  information will also be recorded to ensure that the study focus is mostly related with the menstrual cycyle and no other factors.

## Data Preprocessing: 
- Data Cleaning: Handling missing or inconsistent data, such as blanks or extreme entries. Standardize date formats, and correct typos.
- Calculations and Convertions : Calculating average menstrual period lengt based on cycle_start and cycle_end. Converting boolean variables (painkiller_usage, exam_period, coffee_consumption) into numerical format (e.g., 0 = No, 1 = Yes).
- Mergin Data: Combine all clean participant given data and calculated data into one SQL based database and create the dataset. 

# Data Analysis
## Exploratory Data Analysis (EDA) and Hypothesis Testing
This study investigates how menstrual cycle phases influence study focus and productivity among female students in Turkey.
The analysis is based on self-tracked daily study logs, menstrual cycle data from the Beije mobile application, and additional behavioral indicators (coffee consumption, painkiller usage, exam period).

We evaluated the following core hypothesis:

-Null Hypothesis (H₀):
Menstrual period days (is_period = 1) do not significantly reduce daily study duration.
-Alternative Hypothesis (H₁):
Menstrual period days (is_period = 1) significantly reduce daily study duration.

This hypothesis is based on the assumption that hormonal fluctuations, menstrual cramps, fatigue, and mood-related symptoms commonly experienced during menstruation may negatively impact cognitive focus and academic productivity.


