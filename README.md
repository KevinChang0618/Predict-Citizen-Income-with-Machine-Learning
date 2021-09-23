# Project Goal
Use different classification models to classify citizen's income with 50k or below 50k. And choose the best model with lowest classification error rate.

# Methods
1. Select Variables.  
- Use STEPWISE variable selection to avoid the multicollinearity from our full model. We applied the Forward Stepwise Function from the null model to full, and have a model with the lowest AIC as our selected predictors in the study.  

2. Build five different models to test our data. We use Logistic Regression, LDA, QDA, KNN, and Classification Tree to run our data.  
- Logistic Regression with confusion matrix get accuracy 84.4% and error rate 15.2%. Use 10 Folds Cross-Validation to avoid overfitting.  
- LDA with confusion matrix get accuracy 83.64% and error rate 16.36%.  Use LOOCV (Leave one out cross-validation, default for LDA in R) to avoid overfitting.
- QDA with confusion matrix get accuracy 68.35% and error rate 31.95%.  Use LOOCV (Leave one out cross-validation, default for QDA in R) to avoid overfitting.
- KNN with confusion matrix get accuracy 79.67% and error rate 20.33%. Use 10 Folds Cross-Validation to avoid overfitting and use ROC Curve to check model performance. Tune the K value to find best KNN model.  
- Classification Tree with confusion matrix get accuracy 84.46% and error rate 15.54%. Use 10 Folds Cross-Validation to avoid overfitting and prune the tree to find the best tree with how many nodes and the lowest deviance.

# Conclusion
Based on above method results, the data analysis fit Logistic Regression the best with the lowest prediction classification error rate. And we also find that the group of people who have a wife, have a PhD background and work  related to technology such as computer engineering that have the most possible probability to be classified as high income citizens in the US. The analysis result reveals that males have significantly more income than females on average. In other words, this data has a gender gap on income, which was a society issue back to 1996. Besides, older people are more likely to have higher income. 
