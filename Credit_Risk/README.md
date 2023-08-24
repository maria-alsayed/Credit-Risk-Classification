# Credit-Risk-Classification


Table of Contents:
Overview of the Analysis
Model Results

Summary


Overview of the Analysis.

The Logistic Regression Algorithm is the best tool to use for our machine learning model since it is widely used to predict the probability of a target variable in classification problems.

Using the dataset provided by the lending company, I created a Logistic Regression Model that generated an accuracy score of 95%. Although the model generated a high-accuracy, the models recall value (0.91) for non-healthy loans is lower than the recall value (0.99) for healthy loans. This indicates that the model will predict loan status's as healthy better than being able to predict loan status's as non-healthy. This is due to the dataset being imbalanced, meaning that most of the data belongs to one class label (in this case healthy loans greatly outweighed non-healthy loans).

Taking a look at the code in step 3 [Split the Data into Training and Testing Sets], using the value_counts function, we are able to see that the data is highly imbalanced. The majority class is healthy loans [0] and the minority class is non-healthy loans [1]:

# code
y.value_counts()

# output
0    75036
1     2500
Name: loan_status, dtype: int64

According to the confusion matrix in step 3 [Create a LRM w/ Original Imbalanced Data]:

Out of the 18,765 loan status's that are healthy (low-risk), the model predicted 18,663 as healthy correctly and 102 as healthy incorrectly.

Out of the 619 loan status's that are non-healthy (high-risk), the model predicted 563 as non-healthy correctly and 56 as non-healthy incorrectly.

Classification Report of Imbalanced DataSet

.

# code
y_oversampled.value_counts()

# output
0    56271
1    56271
Name: loan_status, dtype: int64

The oversampled model performs better due to the dataset being balanced. The models non-healthy loans recall value increased from 0.91 to 0.99 indicating that the model does an exceptional job in catching mistakes such as labeling non-healthy (high-risk) loans as healthy (low-risk).

According to the confusion matrix in step 3 [Create a LRM w/ Resampled(oversampled) Data]:

Out of the 18,765 loan status's that are healthy, the model predicted 18,649 as healthy correctly and 116 as healthy incorrectly.

Out of the 619 loan status's that are non-healthy (high-risk), the model predicted 615 as non-healthy correctly and 4 as non-healthy incorrectly.

Classification Report of Imbalanced DataSet


Results

                                           Logistic Regression Model fitted with Imbalanced Data:

The Logistic Regression model fitted with the Imbalanced DataSet predicted healthy loans 100% of the time and predicted non-healthy loans 85% of the time.


The model fitted with imbalanced data has a higher possibility of making these mistakes:

    a healthy loan (low-risk) is classified as a non-healthy loan (high-risk).
    a non-healthy loan (high-risk) is classified as a healthy loan (low-risk).

According to the models recall scores, the model made 1% of mistakes when predicting healthy loans and made 9% of mistakes when predicted non-healthy loans.

Classification Report of Imbalanced DataSet




                                           Logistic Regression Model fitted with Balanced (oversampled) Data:

The Logistic Regression model fitted with the OverSampled DataSet predicted healthy loans 100% of the time and predicted non-healthy loans 84% of the time.



    a healthy loan (low-risk) is classified as a non-healthy loan (high-risk).
    a non-healthy loan (high-risk) is classified as a healthy loan (low-risk).

According to the models recall scores, the model made 1% of mistakes when predicting healthy loans and made 1% of mistakes when predicted non-healthy loans.

Classification Report of Imbalanced DataSet

    The model generated an accuracy score of 99% due to the dataset being balanced.

    Accuracy Score of Imbalanced DataSet


Summary
A lending company might want a model that requires classifying healthy loans and non-healthy loans correctly most of the time:

healthy loans being identified as a non-healthy loan might be more costly for a lending company since it might cause the loss of customers.

non-healthy loans being identified as a healthy loan might also be more costly for a lending company due to the loss of funds being provided by the lender.

The Logistic Regression model fitted with OverSampled data performed much better than the model fitted with Imbalanced data due to the data being balanced and generating a higher accuracy score and a higher recall, indicating that the model will make extremely fewer mistakes when classifying non-healthy loans.


The lending company would most likely want fewer False Positives due to the high possibility of a lender loosing provided funds when classifying non-healthy loans as healthy. The data below is shown in the confusion matrices which indicates how many healthy/non-healthy loans the model predicted correctly/incorrectly.

Model fitted with Imbalanced Data:

    56 (FALSE POSITIVES) --> The actual value is healthy and the predicted value is non-healthy

    102 (FALSE NEGATIVES) --> The actual value is non-healthy and the predicted value is healthy


Model fitted with Balanced Data:

    4 (FALSE POSITIVES) --> The actual value is healthy and the predicted value is non-healthy

    116 (FALSE NEGATIVES) --> The actual value is non-healthy and the predicted value is healthy


