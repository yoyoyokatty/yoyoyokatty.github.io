---
layout: post
title: "Project 5 (Diaster Relief) - Predicting Survival Rates"
comments: false
description: "Project 5 from GA"
keywords: "data science, student, analysis"
---

The goal of this analysis was to show how well the survival of a person could be predicted, given specific qualities of an individual. 

To show off these capabilities, a dataset from the 1912 Titanic data set was used, to predict whether or not someone survived the disaster. 

---

## The Data Source and Methodology

The target that was predicted a binary variable for 0 (did not survive) and 1 (did survive).

Features included in the original dataset included:

- Age
- Passenger Class
- Name
- Sex
- Age
- Number of Siblings/Spouses
- Number of Parents/Children
- Ticket Number
- Fare
- Cabin
- Port of Embarkation

Although the total data set included 891 individual points, there were various data points that had missing values (as standard for a data set tha came from 1912).

The Age and Cabin features were missing the most, with only 714 Age values (80% of total) and 204 Cabin values (23% of total). 

When deciding the final features to develop the model, the following were chosen:

- Fare
- Passenger Class
- Gender

All other features were not chosen because of lack of correlation to surivival. Age would have been an ideal factor to add but given that there was a relatively large amount of data missing, and the mean and median between those who survived and those who didn't was relatively the same, it was left out of the final analysis. 

---

## The Model

Various methods were used to create the model including Logistic Regression, and K Nearest Neighbors. Grid Search (with variations on penalities and volume of nearest neighbors) were also tested. 

It is worth noting though that there were was only a slight variation in the use of each of these models. Therefore, the final model was only marginally better than the others. Since there were only a 3 features that were chosen, and less than 1,000 total values, it is likely that this was too small of a sample to have created a massive difference between the different variations of models.

The final model that was chosen was using a Logistic Regression with no penalities, resulting in a cross-validated R^2 score of .76. 

The result had a relatively high average precision score of .75, and an average recall of .75:

![confusion_matrix](http://yoyoyokatty.github.io/images_kl/project5-disasters/confusion_matrix.png)

Furthermore, the AUC of the ROC was a .80:

![roc_auc_curve](http://yoyoyokatty.github.io/images_kl/project5-disasters/roc_auc_curve.png)

Overall, the model was relatively good at predicting the survival rate of those on the Titanic giving the Class, Gender and Fare of passengers! 
