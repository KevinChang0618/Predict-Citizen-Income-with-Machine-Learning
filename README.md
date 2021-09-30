# Project Goal
Use different classification models to classify citizen's income with 50k or below 50k based on the US Census income dataset from 1994. This dataset was extracted by Barry Becker from the 1994 Census database. What factors influence people’s income is an interesting topic for academic researchers who study about the US personal financial structure or even household financial income. This study may be helpful to other researchers to study further. 

# Methods
1. Select Variables.  
- Use <b>STEPWISE</b> variable selection to avoid the multicollinearity from our full model. We applied the Forward Stepwise Function from the null model to full, and have a model with the lowest AIC as our selected predictors in the logistic regression, LDA, and KNN models.  

2. Build five different models to test our data. We try Logistic Regression, LDA, KNN, Classification Tree, and Random Forest to run our data.  
- <b>Logistic Regression</b> with confusion matrix get accuracy 84.4% and error rate 15.2%. Use 10 Folds Cross-Validation to avoid overfitting.  
- <b>LDA</b> with confusion matrix get accuracy 83.64% and error rate 16.36%.  Use LOOCV (Leave one out cross-validation, default for LDA in R) to avoid overfitting.
- <b>KNN</b> with confusion matrix get accuracy 82.8% and error rate 17.8%. Use <b>'Scale()' scaling on X variables</b> to enhance model performance and plot ROC Curve to check model performance with tuning the K value to find best KNN model.  
- <b>Classification Tree</b> with confusion matrix get accuracy 80.7% and error rate 19.3%. Use 10 Folds Cross-Validation to avoid overfitting and prune the tree to find the best tree with how many nodes and the lowest deviance.
- <b>Random Forest</b> with confusion matrix get accuracy 65.04% and error rate 34.96% at first. After tuning (use for-loop to find lowesr error rate to get best number of variables to split on each nodes and how many trees should build), we have 14.29% error rate. Also, we find capital gain and relationship are two most important variables to affect our response.

# Conclusion
Based on above method results, we get Rondom Forest to be the best model with the lowest prediction classification error rate. And we also find that the group of people who have a wife, have a PhD background and work  related to technology such as computer engineering that have the most possible probability to be classified as high income citizens in the US. The analysis result reveals that males have significantly more income than females on average. In other words, this data has a gender gap on income, which was a society issue back to 1996. Besides, older people are more likely to have higher income.  

# Resource
Data from UCI research database: https://archive.ics.uci.edu/ml/datasets/Adult
