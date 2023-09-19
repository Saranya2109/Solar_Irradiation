# Solar_Irradiation
# Solar Energy Efficiency Prediction Project

This README provides a detailed explanation of a Python code designed for predicting solar energy efficiency using machine learning techniques. The code is structured into several sections, each serving a specific purpose in the analysis and modeling process.

## Table of Contents

- [Introduction](#introduction)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Feature Analysis](#feature-analysis)
- [Data Preprocessing](#data-preprocessing)
- [Model Selection](#model-selection)
- [Evaluation and Prediction](#evaluation-and-prediction)
- [Submission](#submission)

---

## Introduction

The goal of this project is to predict solar energy efficiency based on various weather-related features. To understand the project better, let's briefly explain the key terms:

- **DHI (Diffuse Horizontal Irradiance)**: It represents the amount of solar radiation received from the sky (excluding direct sunlight) on a horizontal surface. DHI is crucial for understanding how much energy can be captured by solar panels on cloudy or overcast days.

- **DNI (Direct Normal Irradiance)**: DNI is the amount of solar radiation received directly from the sun on a surface perpendicular to the sun's rays. It measures the intensity of sunlight and is essential for assessing solar panel efficiency on clear, sunny days.

- **GHI (Global Horizontal Irradiance)**: GHI is the total amount of solar radiation received on a horizontal surface, including both direct sunlight and diffuse sky radiation. It represents the total energy available from the sun.

The dataset used for this project consists of historical weather and solar energy production data. We will use machine learning algorithms to build predictive models for three target variables: Clearsky DHI, Clearsky DNI, and Clearsky GHI, which are related to DHI, DNI, and GHI, respectively.

### Libraries Used

- **numpy**: For numerical operations.
- **pandas**: For data manipulation and analysis.
- **matplotlib** and **seaborn**: For data visualization.
- **sklearn.preprocessing**: For label encoding.
- **xgboost**: For building XGBoost regression models.

### Data Sources

The training data is loaded from the following file:
- **train.csv**: Historical data with features and target variables.

The test data is loaded from the following file:
- **test.csv**: Data for prediction.

---

## Exploratory Data Analysis (EDA)

In this section, we perform exploratory data analysis to understand the dataset better. The steps include loading the data, inspecting its structure, and visualizing key features.

- Loading the training and test datasets.
- Displaying basic information about the training dataset.
- Converting the 'Timestamp' column to a datetime format.
- Visualizing selected feature columns using line plots.
- Creating heatmaps to analyze feature correlations.

---

## Feature Analysis

In this section, we delve deeper into feature analysis, focusing on the correlation of features with the target variables (Clearsky DHI, Clearsky DNI, and Clearsky GHI).

- Creating heatmaps to visualize correlations between features and target variables.
- Calculating the GHI (Global Horizontal Irradiance) based on Clearsky DNI and Clearsky DHI.

---

## Data Preprocessing

Data preprocessing is a critical step in machine learning. In this section, we prepare the data for modeling by encoding categorical features and extracting relevant information from the 'Timestamp' column.

- Extracting day, month, week, hour, and minute information from the 'Timestamp' column.
- Label encoding categorical features.
- Dropping unnecessary columns ('Fill Flag', 'GHI_cal', 'Timestamp', 'TIME', 'DATE').

---

## Model Selection

In this section, we select and train regression models to predict the three target variables (Clearsky DHI, Clearsky DNI, and Clearsky GHI).

- Splitting the data into training and validation sets.
- Building three separate XGBoost regression models for each target variable.
- Tuning hyperparameters such as learning rate, max depth, and the number of estimators.

---

## Evaluation and Prediction

In this section, we evaluate the performance of our models and make predictions using the test dataset.

- Calculating the train and validation scores.
- Measuring Mean Squared Error (MSE) and R-squared (R²) scores.
- Predicting Clearsky DHI, Clearsky DNI, and Clearsky GHI for the test dataset.

---

## Storing Results

Finally, the submission file containing the predicted values for Clearsky DHI, Clearsky DNI, and Clearsky GHI is created.

- Applying post-processing to ensure non-negative values for predictions.
- Saving the submission to a CSV file ('solar_submission.csv') for further use.

This README provides an overview of the entire process, but for detailed code implementation and results, please refer to the Python script.
