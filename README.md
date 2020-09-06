# Overview

This project evaluates several machine learning models to assess credit risk, using data from LendingClub (a peer-to-peer lending services company). The precision, recall, and balanced accuracy rates, for the data sampling learning models, are compared.


# Analysis

## Naïve Random Oversampling
* Precision score: .01 for high_risk / 1 for low_risk
* Recall score: .74 for high_risk /  .56 for low_risk
* Balanced accuracy score: 65.1%

The precision rate for high_risk is extremely low (1%) and the recall score for low_risk loans is also low at 56%. The balanced accuracy score for random oversampling is only 65%. Based on these factors alone, Naïve Random Oversampling is not an effective model for prediction in this situation.

## SMOTE Oversampling
* Precision score: .01 for high_risk / 1 for low_risk 
* Recall score: .62 for high_risk / .69 for low_risk
* Balanced accuracy score: 65.4%

SMOTE Oversampling has very little impact on changing the prediction rates. The balanced accuracy score is still 65% when compared to random over sampling. The precision score did not change at all (.01 for high_risk / 1 for low_risk). The high_risk recall score for SMOTE oversampling deceased (.62) when compared to the high_risk recall score of random oversampling (.74). The low_risk recall score for SMOTE oversampling increased (.69) when compared to the low_risk recall score of random oversampling (.56). Due to the negligible change in accuracy, recall, and precision, SMOTE Oversampling is also not recommended as a model for prediction.

## Cluster Centroid Undersampling
* Precision score: .01 for high_risk / 1 for low_risk
* Recall score: .67 for high_risk / .42 for low_risk
* Balanced accuracy score: 54.4%

Cluster Centroid Undersampling has performed worse than Random Oversampling. The balanced accuracy score for Cluster Centroid Undersampling has dropped to 54% when compared to the Random Oversampling balanced accuracy score of 65.1%. Once again, The precision score did not change at all (.01 for high_risk / 1 for low_risk). The recall score for both high_risk and low_risk also dropped (.67 for high_risk / .42 for low_risk) when compared to the Random Oversampling recall scores (.74 for high_risk /  .56 for low_risk). Considering that Cluster Centroid Undersampling performed worse than Random Oversampling, it is also not recommended not to be used as a model for prediction.

## Combination (Over and Under) SMOTEENN Sampling
* Precision score: .01 for high_risk / 1 for low_risk
* Recall score: .80 for high_risk /  .56 for low_risk
* Balanced accuracy score: 68%

The SMOTEENN Sampling method has the highest balanced accuracy score of 68% when compared to the other methods. It’s precision score also remained unchanged at .01 for high_risk / 1 for low_risk. SMOTEENN Sampling also had the highest recall score of .80 for high risk loans. It’s recall score for low risk loans was .56, which was lower then the SMOTE Oversampling score of .69, but it was higher than the sampling methods.

# Conlusion & Model Recommendation:

In this situation, the precision score means if someone is labeled as being high risk for defaulting on their loan, will they actually default? When looking at the precision score across different sampling methods, they all preformed horribly, with a precision rate of 1%. With the data and sampling models provided, there is no way to really know who will actually default on their loan. Our precision scores tell us that large amounts of people are labeled as being high risk, but do not actually default on their loans.

In this situation, the recall (sensitivity) score means that among people who are actually high risk for defaulting on their loan, how many will be correctly labeled? The Combination (Over and Under) SMOTEENN Sampling method has the highest score of 80%. This means that 80% of people who will default on their loan, can be identified, but only because a large number of people, who will not default on their loan, are also labeled as high risk. This is also why the recall score for low risk individuals is lower at 56%.

Out of the sampling methods used, the Combination (Over and Under) SMOTEENN Sampling method would be recommended because it has the highest balanced accuracy score of 68% and had the highest recall score for high risk individuals. However, the Combination (Over and Under) SMOTEENN Sampling method values are still not that great. It would be recommended to continue to work with different data sets and other sampling methods, in the hopes of finding an even more accurate learning model to predict credit risk.
