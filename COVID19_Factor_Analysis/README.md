# Project of Group 7

Cam Chambers, Chiwon Seuh, Jacob Stugelmeyer, Khuong Nguyen, Yalun Li

## Introduction

COVID-19 has had numerous negative impacts on a global scale. As of 26th July 2023, there have been 768.56 million confirmed cases, including 6.95 million deaths, reported to World Health Organization. Besides, it caused a severe economic downturn. As of September 2021, the International Monetary Fund estimated a global economic contraction of -4.4% in 2020. 
Though the sufferings by COVID-19 have come to an end, we should be ready for similar cases in the future. We may not be able to eliminate the spread of viruses in the era of economic globalization, but we can find those particularly vulnerable to the disease and allocate more medical resources to them to reduce the overall death rate and avoid the shortages of medical supplies. Through the analysis of the data of approximately 31000 of COVID-19 patients in US, we would predict the death rate based on multiple factors, such as the diseases they got before catching COVID-19, sex, age and race. Logistic regression, decision tree, and gradient boosting classifier models will be utilized for their diverse problem-solving approaches, evaluated based on accuracy and precision.


## Body
The data was from trinetx. We didn’t have the specific link to the data because one group member got it from Stat 443 and it wasn’t allowed to be made public. The data was a table with 31462 rows, which were 31462 of patients caught COVID-19 in the US, and 20 columns. The 19 predictor variables are sex(“M” for males and “F” for females), race(there are six races in total with one of them being “unknown”), Agecat(0 for below 50 years old, 1 for between 51 and 60 years old, 2 for between 61 and 70 years old, 3 for between 71 years old and 80 years old, 4 for beyond 81 years old), Charlson(an index that contains several diseases) and the rest are all kinds of diseases(1 for having it before catching COVID-19, and 0 for not). The outcome variable is death(0 for alive, 1 for dead). 

To eliminate multicollinearity, we dropped the variable “Charlson”. Then, we use one-hot encoding for the variable “sex” by replacing it with a new variable “F”, which stands for females(0 for males, 1 for females).

We used 3 different models: Logistic Regression to predict an event based on several variables in the dataset, Decision Tree to create thresholds for different variables and predict based on those thresholds for our event again, and Gradient Boosting to combine the predictions of many models to cover their weaknesses creating a better predictive model.


### 1.Logistic Regression:

#### Our initial model without oversampling resulted in: 



Accuracy
.0958
Precision
.0267
Recall
.00154
AUC
.504


#### As a result of the precision and recall being way too low compared to the accuracy this led us to use oversampling and those results were:

Accuracy
.787
Precision
.791
Recall
.78
AUC
.787




### 2.Gradient Boosting model:

#### Our initial model without oversampling resulted in: 


Accuracy
.943
Precision
.138
Recall
.00734
AUC
.527


#### As a result of the precision and recall being so far under the accuracy we then had to oversample the data resulting in:


Accuracy
.876
Precision
.873
Recall
.881
AUC
.876









### 3.Gradient Boosting model:


Accuracy
.957
Precision
0
Recall
0
AUC
.499






#### Which again, since the precision and recall were essentially 0 and we needed to oversample the data to yield:
 

Accuracy
.794
Precision
.787
Recall
.807
AUC
.794



## Conclusion

Based on our analysis of 31,000 COVID-19 patients in the US, we evaluated the performance of three classifiers: Decision Tree, Gradient Boosting Classifier, and Logistic Regression. Our goal was to predict the death rate based on factors such as pre-existing diseases, sex, age, and race, with the aim of allocating medical resources more effectively to vulnerable individuals and reducing the overall death rate. 

After conducting our evaluation, it has become evident that the Decision Tree is the best classifier for our data, making 994 more correct predictions than the Gradient Boosting Classifier and 1078 more correct predictions than Logistic Regression.

In conclusion, for the prediction of COVID-19 death rates based on pre-existing diseases, sex, age, and race in our dataset, the decision tree classifier proved to be the most effective model, demonstrating superior accuracy and precision compared to the Gradient Boosting Classifier and Logistic Regression.

Here are some examples for how to use our model:

Here are the predicted death rates:



