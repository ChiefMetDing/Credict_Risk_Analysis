# Credict_Risk_Analysis
M17

# Overview of the analysis
The purpose of the analysis is to evaluate multiple resampling algorithms and modeling algorithms to find out a suitable method to be used on credit card risk evaluation.

# Results
## Resampling

Four resampling methods have been evaluated in this analysis.

- Oversampling -- RandomOverSampler and SMOTE
- Under sampling -- ClusterCentroids
- Combination (Over and Under) sampling -- SMOTEENN

The data set is preprocessed by using get_dummies function, which transformed object data into integer data. The data is split into features group (X) and target (y). Then, the data is split into training and testing data sets for further model fitting and testing.

From Balanced Accuracy Score perspective, clearly, SMOTE has the highest score while ClusterCentroids has the lowest. Since the main objective is to successfully identify high risk cases, evaluating f1 and sensitivity (recall) should weigh more.

RandomOverSampler and SWOTEENN have the highest rec value on high risk cases and both of them have high f1 value, which means they have a better balance between precision and sensitivity. Looking closer on these two methods, SWOTEENN has more false positives than the RandomOverSampler does. In practice, SWOTEENN is more likely generating more human hours on screening process. In this specific case, RandomOverSampler is recommended, because it has higher sensitivity (recall) and f1 score on high risk cases, and it has lower FP.

## Modeling

Two classification models are evaluated:

- Balanced Random Forest Classifier (BRFC)
- Easy Ensemble Classifier (EEC)

Similar to the resampling algorithms evaluation, the data is preprocessed and split into features group and target, then further split into training set and testing set. Different than resampling algorithms evaluation, the testing data is scaled by StandardScaler function before being used to fit the models.

The results show that Easy Ensemble Classifier handles this case better than Balanced Random Forest Classifier does. More specifically, EEC’s balanced accuracy score is higher than BRFC’s. The sensitivity score of EEC is 0.92 while BRFC is 0.70. EEC’s f1 score on high risk case is higher than BRFC’s too.

# Summary

The analysis analyzed four resampling algorithms and two modeling algorithms on credit card risk evaluation data set. The evaluation results are presented in Appendix and discussed in Results section.

In terms of resampling, Random Over Sampler is recommended. In terms of modeling, Easy Ensemble Classifier is recommended.

# Appendix

![RandomOverSampler](https://user-images.githubusercontent.com/78275082/123569012-8e26bd80-d793-11eb-95b2-b6b83c80055e.png)

_Figure 1: Random Over Sampler_

![SMOTE](https://user-images.githubusercontent.com/78275082/123569060-9f6fca00-d793-11eb-8267-1486b947d0d5.png)

_Figure 2: SMOTE_

![ClusterCentroids](https://user-images.githubusercontent.com/78275082/123569076-a8f93200-d793-11eb-9da9-c4451cdd4b73.png)

_Figure 3: Cluster Centroids_

![SMOTTEENN](https://user-images.githubusercontent.com/78275082/123569105-b4e4f400-d793-11eb-9cda-f3b912900e95.png)

_Figure 4: SMOTEENN_

![BalancedRandomForestClassifier](https://user-images.githubusercontent.com/78275082/123569176-d1812c00-d793-11eb-8bbc-7def501e2fc2.png)

_Figure 5: Balanced Random Forest Classifier

![EasyEnsembleClassifier](https://user-images.githubusercontent.com/78275082/123569210-e6f65600-d793-11eb-8f90-a68f6c82690a.png)

_Figure 6: Easy Ensemble Classifier_



