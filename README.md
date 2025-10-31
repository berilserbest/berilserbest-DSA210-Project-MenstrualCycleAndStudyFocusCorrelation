# DSA210 Project - The Relationship Between Menstrual Cycle Phases and Study Focus in Female Students in Turkey

## Table of Contents
- [Project Overview](#project-overview)
- [Motivation](#motivation)
- [Data Sources and Dataset Description](#data-sources-and-dataset-description)
- [Data Collection and Preprocessing](#data-collection-and-preprocessing)
- [Analysis Plan](#analysis-plan)
- [Tools and Technologies](#tools-and-technologies)

# Project Overview
I am Beril Nur Serbest, a Computer Science and Engineering student in Sabancı University. I am conducting this project as a part of DSA210 couse. This study focuses on examining how different phases of menstrual cycle influence study focus among female students in Turkey. By analyzing self tracked data collected with Google Forms, this study aims to uncover patterns in cognitive focus and learning efficiency accross different menstrual phases.

# Motivation 
Menstrual cycle periods can effect physical activity levels, mood and cognitive performance due to hormonal fluctuations and physical pains which can influence the study habbits and focus of a person. Understanding the relation between menstrual cycle and stdy focus can help female strudents: 
- Optimize productivity and improve study efficiency by taking hormonal fluctuations into consideration.
- Schedule their academic tasks during high-focus phases to decrease the amount of time they spend working on the tasks
- Contribute to data-driven insights on women’s cognitive performance in Turkey

# Data Sources and Dataset Description
This project relies on self-collected data from female students in Turkey. The Google Forms used to colect the related data. The dataset includes following information: 
- age : age of the participant
- cycle_start : the starting date of the menstrual cycle
- cycle_end : the ending date of the menstrual cycle
- period_length : avarega menstrula period length (will be calculated based on the cycle_start and cyclye_end data of the participant)
- painkiller_usage : the data indicating wheter the participant use painkiller during the menstrual period
- study_hours_daily_M : the daily study duration of the participant during the menstrual cyclye period (hours)
- study_hours_daily : the daily study duration of the participant outside the menstrual cycle period (hours)
- exam_period : the data indicating wheter is it the exam period or not
- coffee_consumption : the data indicating wheter the participant consumes coffe during the menstrual cycle period.

# Data Collection and Preprocessing 
## Data Collection:
Participants will record their daily study hours, focus levels, coffee consumption, painkiller usage, and menstrual cycle dates through Google Forms. Data will be collected for at least one full menstrual cycle per participant (ideally 4–6 weeks). Additional context variables such as exam period and age will also be recorded to ensure that the study focus is mostly related with the menstrual cycyle and no other thing. 

## Data Preprocessing: 
- Data Cleaning: Handle missing or inconsistent entries, standardize date formats, and correct typos.
- Calculation and Categorization: Calculating average menstrual period length (period_length) based on cycle_start and cycle_end and categorizing each day into menstrual phase (Menstrual / Follicular / Ovulatory / Luteal) using the cycle data. Converting boolean variables (painkiller_usage, exam_period, coffee_consumption) into numerical format (e.g., 0 = No, 1 = Yes).
- Mergin Data: Combine all clean participant given data and calculated data into one SQL based database and create the dataset. 


