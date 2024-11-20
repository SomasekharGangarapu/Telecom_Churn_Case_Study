# TELECOM CHURN CASE STUDY
> This project aims to leverage machine learning techniques to accurately predicting the likelihood of telecom customers being churned . This involves analyzing a dataset with three months of data to identify patterns associated with default risks.


## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Data Preparation and Initial Assessment](#data-preparation-and-initial-asssessment)
* [Data Cleaning](#data-cleaning)
* [Exploratory Data Analysis (EDA)](#eda)
* [Train Test Split](#Train-Test-Split)
* [Principle Component Analysis](#PCA)
* [Model Building](#model-building)
* [Conclusions](#Conclusions)

## General Information
Background

This project is part of the PG Program in AI & ML program, specifically within a Machine Learning course.

Goal

To build a machine learning model that is able to predict churning customers based on the features provided for their usage.

Business Problem

In the telecom industry, customers are able to choose from multiple service providers and actively switch from one operator to another. In this highly competitive market, the telecommunications industry experiences an average of 15-25% annual churn rate. Given the fact that it costs 5-10 times more to acquire a new customer than to retain an existing one, customer retention has now become even more important than customer acquisition.

Dataset

The dataset used in this project `train.csv` includes historical data on past telecom customters, covering their usage patterns for 3 months

Customers usually do not decide to switch to another competitor instantly, but rather over a period of time (this is especially applicable to high-value customers). In churn prediction, we assume that there are three phases of customer lifecycle :

1. <u>The ‘good’ phase:</u> In this phase, the customer is happy with the service and behaves as usual. We will consider June and July months from datase as 'good' phase.

2. <u>The ‘action’ phase:</u> The customer experience starts to sore in this phase, for e.g. he/she gets a compelling offer from a competitor, faces unjust charges, becomes unhappy with service quality etc. In this phase, the customer usually shows different behaviour than the ‘good’ months. It is crucial to identify high-churn-risk customers in this phase, since some corrective actions can be taken at this point (such as matching the competitor’s offer/improving the service quality etc.). Considering August month as 'action' phase.

3. <u>The ‘churn’ phase:</u> In this phase, the customer is said to have churned. Considering the fourth month (September) as the ‘churn’ phase.

## Data preparation and initial assessment
* Load and inspect the dataset for completeness and integrity.
* Assess initial data quality and structure to identify areas requiring cleaning or transformation.

## Data cleaning
* Handling irrelevant, irreliable, or non-informative columns
* Handling missing values
* Handling Outliers

## Exploratory Data Analysis
* EDA analysis on top fields
* Define new fields and plot trends

## Train Test Split
* Splitting dataset into train and test df

## Principle Component Analysis
* PCA on scaled data.
* Identify top principal components

## Model Building
* Build different models and identify the best

## Conclusions
 **Technical:**

 * **Data Preprocessing:** The initial dataset underwent extensive cleaning, including handling irrelevant columns, missing values (imputed with 0), and outliers (capped using the k-sigma method).  This preprocessing step was crucial for ensuring the quality of the data fed into the models.

 * **Feature Engineering:** New features were derived from existing ones (e.g., 'drop_in_arpu_during_action_phase') to capture potential relationships between variables and churn probability.  These engineered features improved the model's ability to identify patterns indicative of churn.

 * **Dimensionality Reduction:** Principal Component Analysis (PCA) was employed to reduce the number of features while preserving 95% of the variance in the data. This not only improved model training efficiency but also helped mitigate the curse of dimensionality.

 * **Model Selection and Tuning:** Several models (Logistic Regression, Random Forest, AdaBoost, and XGBoost) were trained and compared.  Pipelines were used to ensure consistent preprocessing for each model.  Hyperparameter tuning using GridSearchCV and RandomizedSearchCV was conducted to optimize model performance.  The XGBoost model ultimately yielded the best results.


 * **Handling Class Imbalance:**  SMOTE (Synthetic Minority Over-sampling Technique) was used within the pipelines for Logistic Regression, Random Forest, and AdaBoost models to address the class imbalance issue in the training data.  XGBoost's `scale_pos_weight` parameter helped handle imbalance without separate oversampling.

 * **Feature Importance:** XGBoost's feature importance scores were used to identify the most influential features in predicting churn.  This analysis can guide further investigation and potentially lead to more targeted customer retention strategies.


 **Business:**

 * **Customer Churn Drivers:**  The analysis revealed several key factors associated with customer churn.  Decreases in ARPU, outgoing minutes of usage (OG_MOU), incoming minutes of usage (IC_MOU), recharge numbers, recharge amounts, and 3G data usage during the action phase (the last two months) strongly correlated with a higher probability of churn.

 * **Proactive Retention Strategies:**  The model can be used to identify customers at high risk of churning, allowing for proactive intervention.  Targeted campaigns or incentives can be deployed to these at-risk customers to encourage them to stay.

 * **Resource Allocation:** Understanding the drivers of churn enables more efficient allocation of resources. Resources can be focused on retaining high-value customers identified as being at risk, rather than on customers who are less likely to churn.

 * **Model Deployment:** The final model (XGBoost) can be used to continuously monitor and predict churn probabilities in real-time, providing valuable insights for ongoing customer retention efforts.

## Acknowledgements
* Thanks to the instructors from UpGrad and IIITB for guidance and feedback.

## Contact
Created by [@SomasekharGangarapu] - feel free to contact us!


<!-- Optional -->
<!-- ## License -->
<!-- This project is open source and available under the [... License](). -->
