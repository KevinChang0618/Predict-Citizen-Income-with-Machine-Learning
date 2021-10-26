# Project Goal
Use different <b>classification models</b> to classify citizen's income with 50k or below 50k based on the US Census income dataset from 1994. This dataset was extracted by Barry Becker from the 1994 Census database. What factors influence people’s income is an interesting topic for academic researchers who study about the US personal financial structure or even household financial income. This study may be helpful to other researchers to study further. 

# Methods.
1. Data Preprocessing.  
- Remove observation with missing value. Because those observations only have 7% in the data, they don't have too much impact. However, if we have more missing value such as 30% missing values, I would choose to use mean/ median/ mode to predict them or I can use KNN model to predict them.  
- Check data distribution and remove outliers because outliers will impact our model severe.
2. Select Variables.  
- Use <b>STEPWISE</b> variable selection to avoid the multicollinearity from our full model. We applied the Forward Stepwise Function from the null model to full, and have a model with the lowest AIC as our selected predictors in the logistic regression, LDA, and KNN models.  

3. Build five different models to test our data. We try Logistic Regression, LDA, KNN, Classification Tree, and Random Forest to run our data.  
- <b>Logistic Regression</b> with confusion matrix get accuracy 84.9% and error rate 15.1%. Use 10 Folds Cross-Validation to avoid overfitting.  
- <b>LDA</b> with confusion matrix get error rate 15.34%.  Use LOOCV (Leave one out cross-validation, default for LDA in R) to avoid overfitting.
- <b>KNN</b> with confusion matrix get error rate 17.22%. Use <b>'Scale()' scaling on X variables</b> to enhance model performance and plot ROC Curve to check model performance with tuning the K value to find best KNN model.  
- <b>Classification Tree</b> with confusion matrix get error rate 19%. Use 10 Folds Cross-Validation to avoid overfitting and prune the tree to find the best tree with how many nodes and the lowest deviance.
- <b>Random Forest</b> with confusion matrix get error rate 14.69% at first. After tuning (use for-loop to find lowesr error rate to get best number of variables to split on each nodes and how many trees should build), we have 14.66% error rate. Also, we find capital gain and relationship are two most important variables to affect our response.

# Conclusion
Based on above method results, we get Rondom Forest to be the best model with the lowest prediction classification error rate. And we also find that captial gain, relationship, education number, age, and marital status are top five important variables to impact classification result of citizen income group in the US. The analysis result reveals that males have significantly more income than females on average and technical support has the highest probability belonging greater 50K group. In other words, this data has a gender gap on income, which was a society issue back to 1996. Besides, older people are more likely to have higher income.  

# Resource
Data from UCI research database: https://archive.ics.uci.edu/ml/datasets/Adult
