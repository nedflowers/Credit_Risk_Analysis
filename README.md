# Credit Risk Analysis
Using the credit card dataset from LendingClub, a peer-to-peer lending services company, you’ll oversample the data using the RandomOverSampler and SMOTE algorithms, and undersample the data using the ClusterCentroids algorithm. Then, you’ll use a combinatorial approach of over- and undersampling using the SMOTEENN algorithm. Next, you’ll compare two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk. Once you’re done, you’ll evaluate the performance of these models and make a written recommendation on whether they should be used to predict credit risk.

## Results

### RandomOverSampler Model
![oversamp.png](https://github.com/nedflowers/Credit_Risk_Analysis/blob/main/images/oversamp.png)
- Balanced accuracy score is 65%.
- High-Risk precision is only 1%, while the recall is 62%.
- Low-Risk precision is 100% due to the oversampling of this class, and recall is 68%.
- F1 score is 2%

### SMOTE Oversampling Model

![smote.png](https://github.com/nedflowers/Credit_Risk_Analysis/blob/main/images/smote.png)
- Balanced accuracy score is 66%.
- High-Risk precision is only 1%, while the recall is 63%.
- Again, low-risk precision is 100% due to the oversampling of this class, and recall is 66%.
- F1 score is 2%

### Undersampling with ClusterCentroids Model

![undersamp.png](https://github.com/nedflowers/Credit_Risk_Analysis/blob/main/images/undersamp.png)
- Balanced accuracy score dropped to 52%.
- High-Risk precision renmains at 1%, while the recall is around 63%.
- There is a high number of false positives, sending the low-risk sensitivity to 40%.
- F1 score is 1%

### Combination Sampling with SMOTEEN Model
![combo.png](https://github.com/nedflowers/Credit_Risk_Analysis/blob/main/images/combo.png)
- Balanced accuracy score is now 62%.
- High-Risk precision remains at 1%, while the recall is around 68%.
- There is a high number of false positives, low-risk recall is 57%.
- F1 score is 2%

### BalancedRandomForestClassifier Model

![randomforests.png](https://github.com/nedflowers/Credit_Risk_Analysis/blob/main/images/randomforests.png)
- Balanced accuracy score increased to 79%.
- High-Risk precision renmains low, at 4%, while the recall is 67%
- There is a lower number of false positives, increasing low-risk sensitivity to 91% with 100% precision.
- F1 score is 7%

### EasyEnsembleClassifier Model
![easyensemb.png](https://github.com/nedflowers/Credit_Risk_Analysis/blob/main/images/easyensemb.png)
- Balanced accuracy score is highest in this model with 93%.
- High-Risk precision crawls to 7%, while the recall is 91%.
- There is a lower number of false negatives, increasing low-risk sensitivity to 94% with 100% precision.
- F1 score is 14%

## Summary
The above models show weak precision in performing credit-risk analysis. Each of the corresponding F1 scores are relatively low, which points to a pronounced imbalance between sensitivity and precision. With the Ensemble models, we saw some improvement with sensitivity of high-risk credit. In particular, the EasyEnsemble model has an average recall score of 94%, detecting almost all high-credit risk. However, with high-risk precision rates remain low throughout the models, we can deduce there is a significant number of low-risk credits being erroneously classified as high-risk. Though our F1 score increased 100% from the RandomForest model (7) to the EasyEnsembleClassifier model, an F1 score of 14% is still low and significantly less than even 50%. These innacuracies could have a damaging effect on the bank's credit strategy and alienate potential customers, losing out on profit. Due to the reasons outlined above, I do not recommend the bank to use any of the aforementioned models.
