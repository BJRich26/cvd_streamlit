# cvd_streamlit

# Cardiovascular Event Risk Predictor - Streamlit App
# Project Overview

This repository contains a Streamlit web application for predicting cardiovascular disease event risk using our slected model: Logistic Regression. The app was created to evaluate can we predict cardiovascular disease events for a possible patient using demographic, clinical, lifestyle, and sleep-related health indicators.

The goal of the app is to provide an interactive demonstration of how our model can be deployed through Streamlit to generate a cardiovascular risk prediction from user-provided patient information. The thoguht process is to approach this like a doctor who finished a screening for a patient and through this method is trying to figure out is there a possibility for CVD (cardiovascula disease) based on the given features in this program.

This tool is for academic demonstration only and should not be used as medical advice or as a replacement for professional clinical judgment.

# Repository Contents:

This repository includes the following files:

README.md - This file explains the purpose of the project, how the Streamlit app works, and how to run it.

cvd_pred_app.py - This is the main Streamlit application file. It creates the user interface, collects input values, loads the trained model, runs the prediction, and displays the result.

cvd_logistic_predictor.sav - This is the saved machine learning model used by the Streamlit app. The app loads this file with pickle and uses it to predict cardiovascular disease event risk.

cvd_features.sav - This file contains the saved list of selected features used by the trained model. The Streamlit app uses this file to make sure the input columns are in the same order and format expected by the model.

requirements.txt - This file lists the Python packages needed to run the app. The main requirements are Streamlit and scikit-learn.

# App Purpose

The Streamlit app allows a user to enter patient information and receive a cardiovascular disease risk prediction.

The app collects information across several categories:

Demographics

Age

Gender

Race category

Health Indicators

BMI

Waist circumference

Systolic blood pressure

Total cholesterol

HDL cholesterol

Triglycerides

History of hypertension

History of diabetes

Lifestyle Factors

Smoking pack-years

Current smoking status

Alcohol drinks per week

Sleep Metrics

Sleep RDI / apnea severity

Sleep efficiency percentage

Percentage of sleep time with oxygen saturation below 90%

After the user enters these values, the app organizes the inputs into the same feature structure used during model training. The saved model then predicts whether the patient is at lower or higher cardiovascular disease event risk.

# How the Streamlit Process Works

The app follows this process:

1. Streamlit opens the web application interface.
2. The app loads the saved machine learning model from cvd_logistic_predictor.sav.
3. The app loads the selected feature list from cvd_features.sav.
4. The user enters patient information through number inputs, radio buttons, and selection boxes.
5. The app converts categorical responses into the encoded numeric values expected by the model.
6. The app stores the user input in a pandas DataFrame.
7. The DataFrame is reordered to match the saved feature list.
8. When the user clicks the prediction button, the model generates a prediction.
9. The model also estimates the probability of a cardiovascular disease event.
10. The app displays whether the patient is classified as lower CVD risk or higher CVD risk.
11. The app shows the estimated probability as a percentage.
12. The app displays a warning message for higher-risk predictions and a success message for lower-risk predictions.
13. Model Used

The deployed model is a trained logistic regression classifier saved as cvd_logistic_predictor.sav.

Logistic regression was selected for deployment because it is interpretable, efficient, and commonly used as a baseline model for binary classification problems. In a healthcare-related project, interpretability is especially important because users need to understand why a model might classify someone as higher or lower risk.

# Target Variable

The model predicts cardiovascular disease event risk as cvd_event.

The output is displayed as one of two classifications:

Lower CVD Risk

Higher CVD Risk

The app also displays the estimated probability of a cardiovascular disease event.

Input Features Used by the App

The app uses the following types of features:

Demographic: age, gender, and race category.

Clinical Health: BMI, waist circumference, blood pressure, cholesterol, HDL, triglycerides, hypertension, and diabetes.

Lifestyle Features: smoking status, smoking pack-years, and alcohol intake.

Sleep-related Features: sleep RDI, sleep efficiency, and oxygen desaturation during sleep.

These inputs reflect the project’s focus on combining traditional cardiovascular risk indicators with sleep-health metrics.

# How to Run the App Locally

To run this app on your own computer, follow these steps:

Download or clone this repository from GitHub.
Make sure all required files are in the same folder:

cvd_pred_app.py

cvd_logistic_predictor.sav

cvd_features.sav

requirements.txt

Open the project folder in a terminal or command prompt.
Install the required packages using the requirements.txt file.
Run the Streamlit app using the Streamlit command for cvd_pred_app.py.
A browser window should open with the Cardiovascular Event Risk Predictor app.
Enter patient values into the form.
Click the prediction button to generate the risk classification and estimated probability.
Required Packages

The app requires the following Python packages:

streamlit

scikit-learn

pandas

pickle is also used to load the saved model and feature list, but it is part of Python’s standard library and does not need to be installed separately.

# Streamlit Deployment Process

This app can be deployed through Streamlit Community Cloud.

The general deployment process is:

1. Upload the app files to a public GitHub repository.
2. Make sure the repository includes the main app file, saved model file, saved feature list file, and requirements.txt file.
3. Go to Streamlit Community Cloud.
4. Connect the GitHub account.
5. Select this repository.
6. Set cvd_pred_app.py as the main app file.
7. Deploy the app.
8. Streamlit will install the packages listed in requirements.txt and launch the app online.

# Important Deployment Notes

The saved model file and saved feature list file must remain in the same repository as the Streamlit app file.

The feature order matters. The app uses cvd_features.sav to make sure the user input columns match the order expected by the trained model.

If the model is retrained with new features, both cvd_logistic_predictor.sav and cvd_features.sav should be updated.

If new packages are added to the app, requirements.txt should also be updated.

# Academic Disclaimer

This application is for academic and educational use only.

The prediction output should not be interpreted as a medical diagnosis. Cardiovascular disease risk should be evaluated by qualified healthcare professionals using clinical judgment, medical history, physical examination, and appropriate diagnostic testing.

# Project Context

This Streamlit app was created as the deployment component of a machine learning final project. The broader project compared multiple machine learning models for cardiovascular disease prediction and evaluated their performance using metrics such as accuracy, recall, precision, F1-score, and ROC-AUC.

The app demonstrates how a trained model can be made interactive and accessible through a simple web interface.

Author

Brandon Richard, Faisal Alessa, Thomas Schlaerth

BSAN 6070: Introduction to Machine Learning

Spring 2026
