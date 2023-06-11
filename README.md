# Credit Risk Analysis Report

## Overview of the Analysis

#### Purpose of the Analysis 
> The purpose of the analyis is to use a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.

#### Explanation of the Financial Information the Data was on, and what Needed to be Predicted
> From the `lending_data.csv` file, the `loan_status` column consist of categorical variables, 0 and 1. A value of 0 in the `loan_status` column denotes a prediction that the loan is healthy. A value of 1 in the `loan_status` columnn denotes a prediction that the loan has a high risk of defaulting. 

#### Basic Information About the Variables Trying to be Predicted
> Performing a `value_counts` function on the labels variable y, there are 75,036 healthy loans and 2,500 loans that have a high risk of defaulting.   

#### Stages of the machine learning process of this analysis.<br>
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


#### Briefly Touch on the RandomOverSampler Method
Using the `RandomOverSampler` module to resample the data
> - An instance of `RandomOverSampler` is instantiated as `random_oversampler`.
> - The training data (`X_train` and `y_train`) is resampled via the `fit_resample` function.
> - The results are named `X_resampled` and `y_resampled`.
> - Calling the `value_counts` function on the `y_resampled` Series returns the following information, as the following code shows:


## Results

Describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * `Logistic Regression` Model with the Original Data
      * Balance Accuracy Score: `(TPs + TNs) ÷ (TPs + TNs + FPs + FNs)` `(18,663 + 563) ÷ (18,663 + 563 + 56 + 102)` `19,226 ÷ 19,384` = `.99`. - The accuracy measures how often the model was correct. It does so by calculating the ratio of the number of correct predictions to the total number of outcomes.
      * Precision Score: `TPs ÷ (TPs + FPs)` `18,663 / (18,663 + 56)` `18,663 / 18,719` = `.997` - This means that out of all the times that the model predicted a testing data observation to be the value 0, 99% of those predictions were correct.
      * Recall Score: `TPs / (TPs + FNs)` `18,663 / (18,663 + 102)` `18,663 / 18,765` = `.99` - By referencing the recall category for the 1 class, we can calculate that the model correctly predicted `612.81` instances `(619 × 0.99)`.


* Machine Learning Model 2:
  * `Logistic Regression` Classifier and the Resampled Data
      * Balance Accuracy Score: `(TPs + TNs) ÷ (TPs + TNs + FPs + FNs)` `(18,649 + 615) ÷ (18,663 + 615 + 4 + 116)` `19,264 ÷ 19,398` = `.99` - The accuracy measures how often the model was correct. It does so by calculating the ratio of the number of correct predictions to the total number of outcomes.
      * Precision Score: `TPs ÷ (TPs + FPs)` `18,649 / (18,649 + 4)` `18,649 / 18,653` = `.999` - This means that out of all the times that the model predicted a testing data observation to be the value 0, 99% of those predictions were correct.
      * Recall Score: `TPs / (TPs + FNs)` `18,649 / (18,649 + 116)` `18,649 / 18,765` = `.99` -  By referencing the recall category for the 1 class, we can calculate that the model correctly predicted `563.29` instances `(619 × 0.91)`.



## Summary
In evaluation of the two machine learning models, Logistic Regression with the Original Data and Logistic Regression Classified and the Resampled Data, they both performed comparatively well and merely identical according the the balance accuracy scores, precision scores and recall scores.  However on the F1 scores, the Logistic Regression Classified and the Resampled Data score was .99 while the Logistic Regression with the Original Data score was .90.  As a result of the F1 scores, the Logistic Regression Classified and the Resampled Data performed better because we know that the loan that has a high risk of defaulting is highly accurate.  I recommend the Logistic Regression Classified and the Resampled Data.
