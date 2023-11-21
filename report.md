# Credit Risk Analysis Report

## Overview of the Analysis

The purpose of this analysis was to train a supervised machine learning model to classify loans as "healthy" or "high-risk" based on:
* loan_size
* interest_rate
* borrower_income
* debt_to_income
* num_of_accounts
* derogatory_marks
* total_debt

The data used in the training and testing of this model included 77,536 loans, 2500 of which (~3%) were "high-risk". 

By splitting the data into training and testing data subsets, a Logistic Regression model was fitted to the training data and then tested against the test data, to see how the model's predictions on loan status ("healthy" or "high-risk") compared to the actual loan status.

Due to a skew in the class distribution (i.e., the data had many more healthy loans than high-risk loans), a second Logistic Regression model was fitted and then tested using randomly oversampled data. This resampling rebalances the class distribution so the model does not ignore the minority class (in this case, the high-risk loans). 

## Results

* Machine Learning Model 1:
  * Accuracy: 0.952
  * Precision for 0 (healthy) prediction: 1.00
  * Precision for 1 (high-risk) prediction: 0.85
  * Recall for 0 (healthy) prediction: 0.99
  * Recall for 1 (high-risk) prediction: 0.91


* Machine Learning Model 2:
  * Accuracy: 0.994
  * Precision for 0 (healthy) prediction: 1.00
  * Precision for 1 (high-risk) prediction: 0.84
  * Recall for 0 (healthy) prediction: 0.99
  * Recall for 1 (high-risk) prediction: 0.99
  

## Summary

Model 2 is outperforms Model 1, as demonstrated by the higher recall score, which indicates a lower false negative rate and therefore a lessened risk of approving a high-risk loan (because there is a lessened risk of falsely predicting loans to be healthy). This improvement results in a greater accuracy score, which measures the overall percentage of correct predictions. 

If the goal of the model is to minimize risk of funding high-risk loans while simultaneously maximizing the number of funded healthy loans, Model 2 may be satisfactory. Less than 1% of all high-risk loan applications would be approved when based solely on the model's predictions (4 out of 619 in the model's confusion matrix test data). Further, approximately 0.6% of all healthy loans would be denied (116 out of 18,765 in the model's confusion matrix test data).