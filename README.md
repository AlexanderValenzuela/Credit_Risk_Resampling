# Credit Risk Analysis Report

## Overview of the Analysis

#### Purpose of the Analysis 
> The purpose of the analyis is to use a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.

#### Explain the Financial Information the Data was on, and what Needed to Predict
> From the `lending_data.csv` file, the `loan_status` column consist of categorical variables, 0 and 1. A value of 0 in the `loan_status` column is predicted that the loan is healthy. A value of 1 in the `loan_status` columnn is predicted that the loan has a high risk of defaulting. 

#### Provide Basic Information About the Variables Trying to Predict
> Performing a `value_counts` function on the labels variable y, there are 75,036 healthy loans and 2,500 loans that have a high risk of defaulting.   

#### Describe the stages of the machine learning process you went through as part of this analysis.<br>
> 1. Prepare the Data<br>
- Load the `lending_data.csv` file from the Resources folder into a Pandas DataFrame.<br> 
- Note that you want to predict the `loan_status` variable. 
- Review the y variable series and the X variable DataFrame.
- Check the balance of the target value, y variable, using the `value_counts` function.

> 2. Split the data into training and testing sets<br>
- Using the `lending_data` DataFrame, separate the data into training and testing data. Start by defining the target (the    “loan_status” column) and the features of the data (all the columns except “loan_status”).<br>
- Split the features and target data into X_train, X_test, y_train, and y_test datasets by using the train_test_split function.
 
> 3. Model and fit the data into a logistic regression<br>
- Declare a `LogisticRegression model` and assign a `random_state` parameter of 1.<br>
- Fit the training data to the model, and save the model.

> 4. Predict the testing labels<br>
- Make predictions about `loan_status` by using the testing dataset, X_test, and save those predictions.<br>

> 5. Calculate and Evaluate the Model's Performance
- Calculate the accuracy score, generate a confusion matrix and print the classification report.


#### Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).
Using the `RandomOverSampler` moduel to resample the data
> - An instance of `RandomOverSampler` is instantiated as `random_oversampler`.
> - The training data (`X_train` and `y_train`) is resampled via the `fit_resample` function.
> - The results are named `X_resampled` and `y_resampled`.
> - Calling the `value_counts` function on the `y_resampled` Series returns the following information, as the following code shows:


## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.



* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.
