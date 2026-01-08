# DSA210 Project - The Relationship Between Menstrual Cycle Phases and Study Focus in Female Students

## Table of Contents
- [Project Overview](#project-overview)
- [Motivation](#motivation)
- [Data Sources and Dataset Description](#data-sources-and-dataset-description)
- [Data Collection and Preprocessing](#data-collection-and-preprocessing)
- [Exploratory Data Analysis (EDA) and Hypothesis Testing](#exploratory-data-analysis-(-eda-)-and-hypothesis-testing)
- [Machine Learning Methods and Analysis](#machine-learning-methods-and-analysis)

# Project Overview
I am Beril Nur Serbest, a Computer Science and Engineering student in Sabancı University. I am making  this project for DSA210 couse. This study focuses on examining how different phases of menstrual cycle influence study focus among female students. By analyzing self tracked data collected with Google Forms and Beije application, this study aims to observe cognitive focus and learning efficiency patterns accross different menstrual phases.

# Motivation 
Menstrual cycle periods can effect physical activity levels, mood and cognitive performance due to hormonal fluctuations and physical pains which can influence the study habbits and focus of a person. Understanding the relation between menstrual cycle and stdy focus can help female strudents: 
- Optimize productivity and improve study efficiency by taking hormonal fluctuations into consideration.
- Schedule their academic tasks during high-focus phases to decrease the amount of time they spend working on the tasks.
- Contribute to data-driven insights on women’s cognitive performance.

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

# Exploratory Data Analysis (EDA) and Hypothesis Testing
This study investigates how menstrual cycle phases influence study focus and productivity among female students.
The analysis is based on self-tracked daily study logs, menstrual cycle data from the Beije mobile application, and additional behavioral indicators (coffee consumption, painkiller usage, exam period).

We evaluated the following core hypothesis:
- Null Hypothesis (H₀):
Menstrual period days (is_period = 1) significantly reduce daily study duration.
- Alternative Hypothesis (H₁):
Menstrual period days (is_period = 1) do nnot significantly reduce daily study duration.

This hypothesis is based on the assumption that hormonal fluctuations, menstrual cramps, fatigue, and mood-related symptoms commonly experienced during menstruation may negatively impact cognitive focus and academic productivity.Therefore, it is reasonable to expect a decrease in study focus and study time during the menstrual period.

## Statistical Test Used
Since the predictor variable (menstrual period status) is categorical (binary) and the outcome variable (daily study hours) is quantitative, a mean comparison test was required. Normality checks (Shapiro-Wilk) and variance tests (Levene) indicated non-normal distributions. Therefore, the non-parametric Mann–Whitney U test was selected.

## Hypothesis Test Result
Daily study hours were compared between menstrual period days and non-period days using the Mann–Whitney U test, selected due to violations of normality in both groups (Shapiro–Wilk p < 0.001). Although variance equality was satisfied (Levene test p > 0.05), the non-normal distribution required a non-parametric mean comparison test.
The Mann–Whitney U test (one-sided, testing whether period days reduce study hours) indicated no statistically significant difference between the two groups (U = 2888, p = 0.451). The effect size (rank-biserial correlation = 0.0123) was extremely small, suggesting that menstrual period status does not meaningfully influence study duration.
Overall, the statistical results do not support the hypothesis that menstrual period days significantly reduce study focus or productivity. Visual analyses (boxplots and time-series plots) similarly show overlapping distributions and no substantial decline during the menstrual phase.

## Visualization Summary
To better understand the relationship between menstrual cycle phases and study behavior, several exploratory data visualizations were generated. These visualizations supported the statistical analysis and helped reveal behavioral patterns across menstrual and non-menstrual days.
- Study Hours: Period vs Non-Period (Boxplot): This boxplot provided an initial comparison of the distribution of daily study hours across menstrual and non-menstrual days. The overlapping distributions and similar medians visually aligned with the Mann–Whitney U results, suggesting no major decline during menstruation.
- Study Hours Over Time (Time-Series Plot): Daily study hours were plotted chronologically to examine temporal trends and possible dips aligned with menstrual days. No consistent downward shift overlapping period days was observed, reinforcing the lack of a significant effect.
- Study Hours by Cycle Day (Line Plot): Study hours were visualized day-by-day during the menstrual phase (cycle_day = 1–8). This plot helped inspect whether early menstrual days (typically Days 1–3) were associated with lower study productivity. The trend remained relatively stable, with no notable decline.
- Painkiller Usage × Cycle Day × Study Hours: Painkiller usage served as a proxy for menstrual discomfort severity. Visualizations comparing users vs non-users across cycle days showed no strong differences in study hours, indicating that pain severity may not have significantly influenced study duration in this dataset.
- Exam Period × Menstrual Status × Study Hours: A grouped visualization explored how exam stress interacts with menstrual status. Exam days influenced study hours more strongly than menstrual status, suggesting external academic factors may override physiological influences.

### Rolling Average Trend Analysis (3-Day Moving Average) 
To better visualize underlying trends and reduce the noise caused by daily fluctuations, a 3-day moving average (rolling mean) was applied to the study hour time series. This smoothing technique highlighted general patterns more clearly and allowed for a more interpretable comparison between menstrual and non-menstrual periods. The rolling-average plots showed stable study performance across the menstrual cycle, further supporting the statistical test results.

## Interpretation of Visual Results
Although the hypothesis assumed that menstrual period days would reduce study hours due to hormonal and physiological effects, the visualizations did not indicate a strong downward trend. Study hour patterns remained relatively stable across cycle days, and fluctuations appeared more related to exam periods rather than menstrual status. Painkiller usage also did not show meaningful variation in study duration.
These observations supported the statistical finding that menstrual period status did not significantly impact study productivity in this dataset.

# Machine Learning Methods and Analysis
To examine and strengthen the results obtained from hypothesis testing and visualizations, supervised machine learning methods were also applied to evaluate whether menstrual cycle status can predict daily study duration among female students.

## Machine Learning Task Definition
The machine learning task was formulated as a supervised regression problem, where the target variable is daily study duration (in hours), and the input features consist of menstrual cycle indicators and behavioral factors.
- Target Variable: study_hours_daily
- Feature Variables: is_period, exam_period, coffee_consumption, painkiller_usage
Given the temporal nature of the dataset, preserving chronological order was essential to ensure realistic model evaluation.

## Train–Test Strategy
To avoid data leakage, a time-aware train–test split was used. The dataset was divided chronologically into 80% training data and 20% testing data, without shuffling. This approach simulates real-world prediction by training models on past observations and evaluating them on future data.
### Models Applied
The following supervised learning models were implemented and compared to get the most accurate result:
--- 1.) Multiple Linear Regression: Used as an interpretable baseline model to examine the direction and magnitude of each feature’s effect on study duration.
- 2.) Decision Tree Regressor: Applied to capture potential non-linear relationships between menstrual cycle variables and study behavior.
- 3.) Random Forest Regressor: Used as an ensemble model to improve prediction stability and to obtain reliable feature importance estimates.

### Evaluation Metrics
Model performance was evaluated using standard regression metrics:
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R² Score
These metrics were computed on the test set for all models to ensure fair comparison.

## Machine Learning Analysis Results
Across all models, predictive performance was limited, which is expected given the behavioral and highly variable nature of daily study habits. However, feature importance analysis revealed consistent patterns:



