# Report: Credit Risk Analysis  

## Overview of the Analysis

In this analysis we have worked on **Credit Risk classification** problem that’s inherently imbalanced, _to identify credit-worthiness of potential borrowers_.
Credit risk is the risk of borrower not repaying loan, credit card or any other type of loan. Sometimes customers pay some installments of loan but don't 
repay the full amount which includes principal amount plus interest, ending up as a loss to the bank. Our aim was to identify such customers and classify them
in 'high risk' category.
Our dataset being imbalanced i.e., healthy loans easily outnumbering risky loans, we approached this problem using Imblearn(Imbalanced - learn) 
library. Imblearn techniques are the methods by which we can generate a data set that has an equal ratio of classes. The predictive model built on 
this type of data set would be able to generalize well. We mainly have two options to treat an imbalanced data set that are Upsampling and Downsampling.   

We are using a dataset of historical lending activity from a peer-to-peer lending services company. Dataset contains all the necessary financial information 
of the borrower ,forming our feature set to train our model with: 
* loan_size        -> Size of loan amount requested by the borrower
* interest_rate    -> per annum Interest rate on the loan amount 
* borrower_income  -> Income of the borrower
* debt_to_income   -> Debt to income ratio
* num_of_accounts  -> Number of existing loan accounts 
* derogatory_marks -> Derogatory marks against the borrower
* total_debt       -> The total debt  
 
  **_loan_status_** is our target column that we trained our model to perform prediction on. '0' as 'Healthy' and '1' as 'High risky' loan.  

### Steps followed for the analysis:
* Split the Data into Training and Testing Sets
* Create a Logistic Regression Model with the Original Data
* Predict a Logistic Regression Model with Resampled Training Data using Random oversampling
...
* Predict a Logistic Regression Model with Resampled Training Data using SMOTE
* Predict a Random Forest Model with Resampled Training Data using SMOTE

Though initial intention was to check the performance of the model with and without random oversampling approach from imblearn library using Logistic 
Regression classifier but we went ahead and tried synthetic resampling approach using SMOTE as well. With SMOTE Logistic regression classifier and RF 
classifier were used to check the performance of both the classifiers. 
So in this report we'll summarize the result we achieved with and withour Random oversampling using Logistic Regression model.

## Results

Below are the result of metrics generated by our _classification report_: 

**Logistic Regression Model 1**(Without resampling):

* Precision: 100% precise in predicting healthy loans, but only 87% precise in predicting high-risk loans(on average, the model was 99% precise in classifying loans)
* Accuracy : 94% accurate in correctly classifying loans 
* Recall   : 100% in predicting healthy loans, but 89% recall in predicting high-risk loans i.e., it is classifying 11% of high risk loans as healthy

**Logistic Regression Model 2**(With random-oversampling):

* Precision: 93% (an average--in predicting low-risk loans, the model was 100% precise, though the model was only 87% precise in predicting high-risk loans)
* Accuracy : 99.6% accurate in correctly classifying loans 
* Recall   : 100% in predicting healthy loansas well as high-risk loans(due to significant low no. of False postives)

## Summary

From the _classification report_ we can see that with random oversampling and sythetic sampling approach imporved the performance of the model by correctly classifying 
true negative and reduced number of _False Positives_ i.e, high risk loans labeled as healthy. Hence this modelling approach seems to be reliable compared to working 
on orginal/imbalanced dataset.
Usually the performance of any model depends on the problem you are trying to solve. For e.g., in our scenario False positive is an important factor for our 
model as we need to correctly flag high-risk loans and if any high-risk loan is incorrectly labeled as healthy loan then the company would have to face the loss 
if the loan is processed. However in a scenario where model needs to predict whether the patient has a disease or not, False negative is the important measure 
to identify the performance of the model.

**In conclusion** 2nd model, trained on resampled data using random oversampling performed better than our 1st model that was trained on original dataset.
Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
