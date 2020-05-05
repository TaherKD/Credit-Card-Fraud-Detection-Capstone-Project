# Credit-Card-Fraud-Detection-Capstone-Project
The aim of this project is to predict fraudulent credit card transactions using machine-learning models.

## Project Understanding
Banks need to be cautious about their customers’ transactions, as they cannot afford to lose their customers’ money to fraudsters. Every fraud is a loss to the bank as the bank is responsible for the fraud transactions if it is reported within a certain time frame by the customer.

## Data Understanding
The data set contains customer level data and was obtained from Kaggle. The data set includes credit card transactions made by European cardholders over a period of two days in September 2013.It contains thousands of individual transactions that took place over a course of two days and their respective labels.

The data set has also been modified with Principal Component Analysis (PCA) to maintain confidentiality. Apart from ‘time’ and ‘amount’, all the other features (V1, V2, V3, up to V28) are the principal components obtained using PCA. The feature 'time' contains the seconds elapsed between the first transaction in the data set and the subsequent transactions. The feature 'amount' is the transaction amount. The feature 'class' represents class labelling, and it takes the value 1 in cases of fraud and 0 in others.

The data can be found <a href="https://www.kaggle.com/mlg-ulb/creditcardfraud">here.</a>

## Project Pipeline
**The approach followed is mentioned below along with the links for the relevant portions :**

**1. Importing the dataset and understanding the dataset**
1. Importing the credit default dataset
2. Analyzing the response variable  - `Class` - Data Imbalance, Fraud Rate
3. `auc_score` can be used as evaluation metric since the data is heavily imbalanced 


**2. Exploratory Data Analysis - `TIME` and `AMOUNT` variables**
1. Univaraite and Bivariate analysis for `Time` and `Amount` Variables
2. Creation of new column `hour` based on the time data provided
3. Check for any issues with the dataset provided


**3. Data Preparation for the modelling**
1. Understanding the distribution of various features and calculating skew
2. Train and Test split of the data
3. Transforming features and standardizing data of train and test data using power transformation
4. Checking the distribution and skew of the data after transformation


**4. Modelling the Data using normal and oversampled dataset**

All the models tried on the provided dataset include hyperparameter tuning based on cross validation `roc_auc` score and evlauation of the model on test dataset using metrics such as classification report, recall, precision, f1score, acccuracy etc.

1. Modelling on Normal Dataset
    - Logistic Regression
    - Random Forest
    - Lightgbm
    - XGBoost
    
2. Modelling on Random oversampled data
    - Using Random oversampling to balance the fraud class of the dataset
    - visualizing random oversampled data
    - Logisitc Regression
    - Random Forest
    - Lightgbm
    - XGBoost
    
3. Modelling on synthetic oversampling using SMOTE
    - Using SMOTE to balance the fraud class of the dataset
    - visualizing the newly created data points by SMOTE
    - Logisitc Regression
    - Random Forest
    - Lightgbm
    - XGBoost
    
4. Modelling on synthetic oversampling using ADASYN
    - Using ADASYN to balance the fraud class of the dataset
    - visualizing the newly created data points by ADASYN
    - Logisitc Regression
    - Random Forest
    - Lightgbm
    - XGBoost

**5.Comparison of the Models and Selecting the best models**
1. Comparison of test roc_auc score, repeated cross_validation scores for the various models tried and selecting the best model from Normal, Random oversampled, SMOTE and ADASYN models created
2. Understanding Feature importance based on the best model
3. Evaluating various metrics such as recall, f1score for the best models and identifying optimal threshold using KS STASTIC
    - Checking out roc_auc curve, precision-recall curve and sensitivity-specificity to curve to understand the metrics at various thresholds
    - Using various metrics to determine the best_threshold - pr curve, max f1score and ksstatistic
    - Identifying right threshold based on precision and recall of the above three methods
4. Final Metrics based on the optimal threshold selected


**6. Cost/Financial Analysis**
