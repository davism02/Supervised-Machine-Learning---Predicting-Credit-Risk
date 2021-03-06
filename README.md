# Supervised Machine Learning Homework - Predicting Credit Risk

In this assignment, I built a machine learning model that attempts to predict whether a loan from LendingClub is high risk or not.

## Background

LendingClub is a peer-to-peer lending services company that allows individual investors to partially fund personal loans as well as buy and sell notes backing the loans on a secondary market. LendingClub offers their previous data through an API.

You will be using this data to create machine learning models to classify the risk level of given loans. Specifically, you will be comparing the Logistic Regression model and Random Forest Classifier.

### Retrieve the data

In the `Generator` folder in `Resources`, there is a [GenerateData.ipynb](/Resources/Generator/GenerateData.ipynb) notebook that will download data from LendingClub and output two CSVs: 

* `2019loans.csv`
* `2020Q1loans.csv`

I used the entire year's worth of data (2019) to predict the credit risk of loans from the first quarter of the next year (2020).

Note: these two CSVs have been undersampled to give an even number of high risk and low risk loans. In the original dataset, only 2.2% of loans are categorized as high risk. To get a truly accurate model, special techniques need to be used on imbalanced data. Undersampling is one of those techniques. Oversampling and SMOTE (Synthetic Minority Over-sampling Technique) are other techniques that are also used.

## Preprocessing: Convert categorical data to numeric

Create a training set from the 2019 loans using `pd.get_dummies()` to convert the categorical data to numeric columns. Similarly, create a testing set from the 2020 loans, also using `pd.get_dummies()`. Note! There are categories in the 2019 loans that do not exist in the testing set. If you fit a model to the training set and try to score it on the testing set as is, you will get an error. I used code to fill in the missing categories in the testing set. 

## Consider the models

I created and compared two models on this data: a logistic regression, and a random forests classifier. Before I created, fit, and scored the models, made a prediction as Random Forrest would perform better for this data.

## Fit a LogisticRegression model and RandomForestClassifier model

# Analysis for Logistic Regression, both the training and the testing score increased for the scaled data over the unscaled data.
    Logistic regression unscaled data:
        Training Score: 0.6980295566502464
        Testing  Score: 0.5776265418970651
    
    Logistic regression with scaled data is
        Training Score: 0.7079638752052545 
        Testing  Score: 0.7679710761378137


# For the analysis of Random Forest Classifier, there was not much difference between unscaled and scaled testing data.
    Random Forest Classifier unscaled data:
        Training Score: 1.0
        Testing Score: 0.647809442790302

    Random Forest Classifier model scores are:
        Training Score: 1.0 
        esting Score: 0.6401531263292216

# Overall the Logistic Regression was a better predictor over the Random Forrest for both scaled and unscaled testing data.??

## Rubric


### References

LendingClub (2019-2020) _Loan Stats_. Retrieved from: [https://resources.lendingclub.com/](https://resources.lendingclub.com/)

- - -

?? 2021 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.
