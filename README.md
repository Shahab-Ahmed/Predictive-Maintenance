# Predictive-Maintenance
Project goal
1. The client provided a dataset that had information on machine parts and it was my job to predict when the components would fail and also the type of failure . (Power, heat, overstrain, etc.)
2. The main issue was the highly imbalanced dataset. The data was composed of 96.6% 'No Failure' data points. This made training the model difficult since any implemented algorithm would naturally gravitate toward predicting 'No Failure' very often and would achieve a high accuracy by doing so. This problem was exasperated by the fact that certain types of failures that I was attempting to predict only had 18 data points in all.

Solution
1. I performed exploratory data analysis in order to determine the most important features to provide the model with. I then tested several different learning algorithms to see which one performed the best. I looked not only at the F1-Score for the model overall but also for its ability to accurately predict specific failures.
a. For example, logistic regression may have had an F1-score of 0.97 overall but, when looking at its ability to predict specific failure types, the F1 drops as low as 0. Thus, I determined that random forest was the best model for this problem because of its high F1-score on all error types.
2. In order to deal with the imbalanced dataset I tried several methods. I implemented undersampling on the 'No Failure' category but found that the loss of data hurt the model's ability to capture the data. I encountered a similar problem when implementing oversampling on the errors. The method that worked best was a data augmentation method known as SMOTE (Synthetic Minority Oversampling Technique). Based on a 2002 paper published in the Journal of Artificial Intelligence Research, SMOTE works by: identifying the minority class and it's K-nearest neighbor, drawing an imaginary line segment between the two, placing a new synthetic data point on that line segment and repeating. This method allowed me to create more data to feed my model and drastically improved performance.


