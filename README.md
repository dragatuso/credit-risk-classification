# credit-risk-classification
The repository includes the julyter notebook with the code developped for analyzing the credit risk data in the csv file, and this README that includes the Credit Risk Analysis Report.
Most of the code was developped based on the activities completed and reviewed during Module 20 of the bootcamp.


## Credit Risk Anlysis Report

## Overview of the Analysis
The purpose of the analysis is to predict the credtiworthiness of a group of borrowers. For doing so, I built a model that aims to identify each creditworthiness by labeling a group of loans between 'healthly-loan' (`0`) and 'high-risk loan' (`1`), using a dataset of historical lending activity from a peer-to-peer lending services company. 

The dataset used to predict the loans' creditworthiness contains 77,536 loans with a total balance of 760,284,100. 93.9% of the balance corresponds to healthy laons while 6.1% is from high-risk loans. If we consider the number of loans, 96.8% are healthy loans, while 3.2% are high.risk loans. Therefore, analyzing the loan status distribution by loan balance or by number of loans does not change much the results. With the model we are predicting this percentage of loans by status category.

The process for building the model included the following parts: reading the lending data from the and creating a pandas dataframe, creating the labels set (`y`) from the “loan_status” column and then creating the features (`X`) DataFrame from the remaining column, splitting the data into training and testing sets by using train_test_split, fitting a logistic regression (using the `LogisticRegression` method) model by using the training data (`X_train` and `y_train`), saving the predictions on the testing data labels by using the testing feature data (`X_test`) and the fitted model, and evaluating the model's performance by generating a confusion matriz and a classification report.

## Results
The following are the accuracy scores and the precision and recall scores of the machine learning model.
    * Accuracy: 0.99
    * Precision: 1.00 for `0` and 0.85 for `1`
    * Recall: 0.99 for `0` and 0.92 for `1`

## Summary
Considering the 99% of accuracy, in general the model predicts really well the healthy loan and high-risk loan labels. In addition, when analizing the precision and recall scores for each label in more detail, we can also notice that in both cases for the healthy loan the scores are 100% and 99%, respectively, which indicate that the model is really good for identifying the '0' loans. However, when analyzing the precision and recall scores for the '1' loans, I noticed that the model was not that accurate in identifying them: There is 15% of loans that were classified as high risk loans but are not, and there is a 8% of loans that are high risk loans but were not recognized as such by the model.

In general, I would recommend this model because, for this analysis, it is more important to predict the `1`'s and although there are some false positives for high risk loans and the model takes a conservative approach identifying some loans as high risk that are not, it is better to be more conservative for loans in situation 1.