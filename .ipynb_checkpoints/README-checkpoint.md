# Credit Risk Classification

![Credit Risk](Images/cc-image.png)

## Background

Credit risk poses a classification problem that’s inherently imbalanced. This is because healthy loans easily outnumber risky loans. In this notebook, we’ll use various techniques to train and evaluate models with imbalanced classes. Using a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.

Using our knowledge of the imbalanced-learn library, we’ll use a logistic regression model to compare two versions of the dataset. First, we’ll use the original dataset then resample the data by using the `RandomOverSampler` module from the imbalanced-learn library.

For both cases, we’ll get the count of the target classes, train a logistic regression classifier, calculate the balanced accuracy score, generate a confusion matrix, and generate a classification report.

Based on the analysis will create a credit risk analysis report.

- - -

## Files

* [Analysis Notebook](credit_risk_resampling.ipynb)
* [Data Files](Resources)
* [Report](report-template.md)

- - -
## Steps followed:

* Split the Data into Training and Testing Sets

* Prediction using a Logistic Regression Model with the Original Data 

* Prediction using a Logistic Regression Model with Resampled Training Data 

* Prediction using a Random Forest Model with Resampled Training Data 

* 

## Summary

* [Report: Credit Risk Analysis](report-credit-risk-analysis.md)


