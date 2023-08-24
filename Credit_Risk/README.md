# Credit-Risk-Classification


Table of Contents:
Overview of the Analysis
Model Results

Summary


Overview of the Analysis.

The Logistic Regression Algorithm is the best tool to use for our machine learning model since it is widely used to predict the probability of a target variable in classification problems.

Logistic Regression Model that generated an accuracy score of 95%. Although the model generated a high accuracy, the model's recall value (0.91) for non-healthy loans is lower than the recall value (0.99) for healthy loans. This indicates that the model will predict loan statuses as healthy better than being able to predict loan statuses as non-healthy. This is because the dataset is imbalanced, meaning that most of the data belongs to one class label (in this case, healthy loans greatly outweighed non-healthy loans).

Looking at the code in step 3 [Split the Data into Training and Testing Sets], using the value_counts function, we can see that the data is highly imbalanced. The majority class is healthy loans [0], and the minority class is non-healthy loans [1]:


# output
0    75036
1     2500


According to the confusion matrix in step 3 [Create an LRM w/ Original Imbalanced Data]:

Out of the 18,765 loan statuses that are healthy (low-risk), the model predicted 18,663 as healthy correctly and 102 as healthy incorrectly.

Out of the 619 non-healthy loan statuses (high-risk), the model predicted 563 as non-healthy correctly and 56 as non-healthy incorrectly.

Classification Report of Imbalanced DataSet


# output
0    56271
1    56271


The oversampled model performs better due to the dataset being balanced. The model's non-healthy loan recall value increased from 0.91 to 0.99, indicating that the model does an exceptional job of catching mistakes, such as labeling non-healthy (high-risk) loans as healthy (low-risk).

According to the confusion matrix in step 3 [Create a LRM w/ Resampled(oversampled) Data]:

Out of the 18,765 loan statuses that are healthy, the model predicted 18,649 as healthy correctly and 116 as healthy incorrectly.

Out of the 619 non-healthy loan statuses (high-risk), the model predicted 615 as non-healthy correctly and four as non-healthy incorrectly.

Classification Report of Imbalanced DataSet


Results

                      Logistic Regression Model fitted with Imbalanced Data:

The Logistic Regression model fitted with the Imbalanced DataSet predicted healthy loans 100% of the time and non-healthy loans 85% of the time.


The model fitted with imbalanced data has a higher possibility of making these errors:

    A healthy loan (low-risk) is classified as a non-healthy loan (high-risk).
    A non-healthy loan (high-risk) is classified as healthy (low-risk).

According to the model's recall scores, the model made 1% of mistakes when predicting healthy loans and 9% of errors when predicting non-healthy loans.

Classification Report of Imbalanced DataSet




                  Logistic Regression Model fitted with Balanced (oversampled) Data:

The Logistic Regression model fitted with the OverSampled DataSet predicted healthy loans 100% of the time and predicted non-healthy loans 84% of the time.



    A healthy loan (low-risk) is classified as a non-healthy loan (high-risk).
    A non-healthy loan (high-risk) is classified as healthy (low-risk).

According to the model's recall scores, the model made 1% of mistakes when predicting healthy loans and 1% of errors when predicting non-healthy loans.

Classification Report of Imbalanced DataSet

    The model generated an accuracy score of 99% due to the balanced dataset.

    Accuracy Score of Imbalanced DataSet


Summary
A lending company might want a model that requires classifying healthy loans and non-healthy loans correctly most of the time:

Healthy loans being identified as non-healthy loans might be more costly for a lending company since it might cause the loss of customers.

Non-healthy loans being identified as healthy loans might also be more costly for a lending company due to the loss of funds being provided by the lender.

The Logistic Regression model fitted with OverSampled data performed much better than the model equipped with Imbalanced data due to the data being balanced and generating a higher accuracy score and a higher recall, indicating that the model will make fewer mistakes when classifying non-healthy loans.


The lending company would most likely want fewer False Positives due to the high possibility of a lender losing provided funds when classifying non-healthy loans as healthy. The data below is shown in the confusion matrices, which indicate how many healthy/non-healthy loans the model predicted correctly/incorrectly.

The model fitted with Imbalanced Data:

    56 (FALSE POSITIVES) --> The actual value is healthy, and the predicted value is non-healthy

    102 (FALSE NEGATIVES) --> The actual value is non-healthy, and the predicted value is healthy


The model fitted with Balanced Data:

    4 (FALSE POSITIVES) --> The actual value is healthy, and the predicted value is non-healthy

    116 (FALSE NEGATIVES) --> The actual value is non-healthy, and the predicted value is healthy



