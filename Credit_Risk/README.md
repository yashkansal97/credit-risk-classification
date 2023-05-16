# Module 12 Report Template

## Overview of the Analysis

In this challenge, the focus is on analyzing credit data for various borrowers and their loan status, to create a machine learning model which would allow the user to predict whether a loan is "Healthy" or "High-Risk" based on the information of the borrower.

To create this model, we have been provided information on various borrowers and their loans, and whether these loads were classified as "healthy" or "high-risk". The information provided includes the loan amount, the interest rate on the loan, the borrower's income, their debt-to-income ratio, number of accouts, derogatory remarks on the accounts, and total debt. For all these loans, we are also provided the laon status, i.e., whether these "healthy" (0) loans or "high-risk" (1) loans.

As for the analysis, we first determine the value counts for each label (0 or 1) for "loan status" in order to understand the distribution and the ratio of how are model should be predicting 0 and 1. In this dataset, the value counts for "0" were 75036 and for "1" were 2500. This indicated that the dataset has significantly more samples for "healthy" loans and some resampling might be needed. 

After this, we begin to build are machine leaning model. 
1. We first determine the input variables (X), which was every variable except "loan status", which was our output (y). 
2. After defining X and y, we split these into the training and test set. Doing so would allow us to train our model on the training set and use the X_test to predict y and compare it with y_test to analyze the performance of the model.
3. After splitting into training and test sets, we initiate a logistic regression model to classify these loans. 
4. We then proceed to training our model on the training set by fitting it on X_train and y_train. 
5. Using the fitted model, we predict the y values.
6. Using the y_test values and the predicted y values, we get the balanced accuracy score, the confusion matrix and the classification report. 
7. Now, since we had earlier realized that we have significantly more samples of one label compared to another, we create new random samples (resample) to train another model to address the over sampling of one label. 
8. After creating new samples, we confirm that we have equal number of samples for both labels. (This is confirmed by value counts: 0 - 56271, 1, 56271)
9. Once this new training set is created, we repeat steps 3 to 6 to analyze this new model.

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
    * Balanced Accuracy Score: 0.952
    * Precision Scores:
        * 0: 1.00
        * 1: 0.85
    * Recall Scores: 
        * 0: 0.99
        * 1: 0.91

* Machine Learning Model 2:
    * Balanced Accuracy Score: 0.994
    * Precision Scores:
        * 0: 1.00
        * 1: 0.84
    * Recall Scores: 
        * 0: 0.99
        * 1: 0.99    

## Summary

Observing the results, the balanced accuracy score of model 2 (0.994) is higher than that of model 1 (0.952). This indicates that the performance of model 2 is better. Furthermore, looking at the precision and recall scores, even though the precision scores are almost identical, the recall score for "high-risk" (*1*) loans is significantly better for model 2 (0.99 for model 2 vs 0.91 for model 1). This indicates that model 2 is much better at predicting "high-risk" loans, when compared to the performance of model 1. This overall indicates that model 2 is performing better than model 1, especially when it comes to classifying "high-risk" loans. 

Specifically, for this problem, correctly classifying "high-risk" loans is more important than correctly classifying "healthy" loans. This is because when categorizing loans, it is important that the model is correctly flagging "high-risk" loans because if these loans weren't categorized as such and they default, they could cost the loaning entity the entire principal amount. Whereas, in case a "healthy" loan is wrongly categorized as "high-risk" loan, the loaning company only looses out on the profit made from the interest payments, which is inherently significantly lower than the principal amount. 

In conclusion, model 2 is the recommended model given it's better overall performance, and especially because of its better performance when classifying "high-risk" loans.