# FYS2021_assignments
The assignments to the course FYS-2021 Machine learning

PART 1

The first assignment is to prepare a database in a csv file for machine learning. The csv file is read into a dataframe.
This particular data set is of songs of different genres, that has a number of features. We focus on the genres Classical and Pop, and the features "loudness" and "liveness". The Classical song get the label 0 and the Pop songs get the label 0. The labels are put in a vector and the features in a matrix. The whole data set is then divided into a training set and a test set.

PART 2

Then logistic regression is run on the data. This is done without sklearn, so first the sigmoid function is defined. Then the cost function, which I have chosen to be MSE. Further the gradient descent is defined in a function and then the prediction function is defined, which will return a list of predicitions. Then all features are normalized by calculating the mean and the standard deviation for the training and test features, and then subtracting the mean and dividing by the standard deviation. This is done to make sure the feature values are on the same scales, to improve convergence (i.e. that the gradient descent converges faster, because the features are on a similar scale). After that the intercept (or bias) term is included. Without this the intercept will pass through the origin, which might not be a good fit for the data. Then the weight are initialized as a vector of zeros. 

Then I have a commented out section where I've tested different learning rates and the effect is visualized in a plot. The learning rate is set to 0.1 and the number of iterations of the gradient descent is set to 1000.  

The I define a function to calculate the accuracy, where correct predcitions are found by checking if the predictions match the labels. Accuracy is then calculated as the nuber of correct predictions divided by the number of labels (len(labels)). What is returned from this function is the accuracy times 100, to get the percent. 

Then to see if there is a siginificant difference between the accuracy of the test and training sets, I run the whole thing 10 times. The result for each iteration is printed to the terminal. Then I calculate the mean and standard deviation for these 10 results, and perform a t-test to see if there is a significant difference between the test and traning accuracy. An interpretation (if the difference is significant or not), significance level set to 0.05, is printed to terminal. 

PART 3

Setting up a confusion matrix. First the predicitons on the test set is run, so we get a list of the test predictions. THen we initialize the confusion matrix components (TP, TN, FP, FN). All of these values are calculated in a for loop, by checking if the test labels for the sample matches the predicted test label values, and for every sample the right component increases by 1. When that is done the resultant values are put in a new np.array, which is the confusion matrix. The matrix is then printed to the terminal.

The final part, finding a classical song that a Pop fan would appreciate. Was somewhat confusing, as the result I got was rock/metal songs. I decided to sort on feature Loudness and genre Classical. The song with the highest loudness that was classified as a classical song was "Go faster” by Richie Kotzen. I checked the csv file and yes, the classical genre was littered with metal songs. 
