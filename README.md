# Module 18 Challenge: Neural Network Challenge 1

## Problem Statement
Create a model to predict the likelihood that a student loan applicant will repay their loan based on information about previous student loan recipients.

## Solution
As instructed, we use the `credit_ranking` feature provided in the data with values `0` and `1` to decide whether an applicant is likely to repay their student loan. A `credit_ranking` value of `1` indicates the applicant will most likely repay their loan, whereas a value of `0` indicates that they will most likely not repay their loan.  
We use a deep-learning neural network with two hidden layers to classify the data.

Since all the features have numeric data types (float or int), no encoding is necessary.

Following the instructions provided, after splitting the data into `X` and `y` und further splitting `X` and `y` into training and test datasets, respectively, we scale the `X_train` and `X_test` data using the `StandardScaler`.

We then create a neural network with two hidden layers. We train the data using 50 epochs. That is sufficient because the accuracy and loss do not change much after 40 epochs of training.

Following best practice, we first use 27 nodes for hidden layer 1 and 2. This corresponds to about 2.5 times the number of features (which is 11). This yields a loss of 0.543 and an accuracy of 0.752.  
We then use 6 nodes for the first hidden layer and 3 nodes for the second hidden layer. This was given in the output to the starter file. This yields a loss of 0.518 and an accuracy of 0.745.  
Since loss and accuracy are very close we kept the smaller numbers of nodes for our final model.

After building and training the model we export it to a Keras file at `saved_model/student_loans.keras`.

We then reload the model and generate predictions and generate and print a classification report for the test dataset. From the classification report, we obtain an overall accuracy score of 0.74 consistent with the accuracy scores obtained above.