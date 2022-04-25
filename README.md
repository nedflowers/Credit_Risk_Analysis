# Credit Risk Analysis
Using the credit card dataset from LendingClub, a peer-to-peer lending services company, you’ll oversample the data using the RandomOverSampler and SMOTE algorithms, and undersample the data using the ClusterCentroids algorithm. Then, you’ll use a combinatorial approach of over- and undersampling using the SMOTEENN algorithm. Next, you’ll compare two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk. Once you’re done, you’ll evaluate the performance of these models and make a written recommendation on whether they should be used to predict credit risk.

## Results

### RandomOverSampler Model
![oversamp](https://github.com/nedflowers/Credit_Risk_Anlysis/blob/main/images/oversamp.png)
- Our balanced accuracy score is 65%.
- High-Risk precision is only 1%, while the recall is 62%.
- Low-Risk precision is 100% due to the oversampling of this class, and recall is 68%.
- F1 score is 2%

### SMOTE Oversampling Model

![smote](https://github.com/nedflowers/Credit_Risk_Anlysis/blob/main/images/smote.png)
- Our balanced accuracy score is 66%.
- High-Risk precision is only 1%, while the recall is 63%.
- Again, low-risk precision is 100% due to the oversampling of this class, and recall is 66%.
- F1 score is 2%

### Undersampling with ClusterCentroids Model

![undersamp](https://github.com/nedflowers/Credit_Risk_Anlysis/blob/main/images/undersamp.png)
- Our balanced accuracy score dropped to 52%.
- High-Risk precision renmains at 1%, while the recall is around 63%.
- There is a high number of false positives, sending the low-risk sensitivity to 40%.
- F1 score is 1%

### Combination Sampling with SMOTEEN Model
![combo](https://github.com/nedflowers/Credit_Risk_Anlysis/blob/main/images/combo.png)
- Our balanced accuracy score is now 62%.
- High-Risk precision remains at 1%, while the recall is around 68%.
- There is a high number of false positives, low-risk recall is 57%.
- F1 score is 2%

### BalancedRandomForestClassifier Model

![randomforests](https://github.com/nedflowers/Credit_Risk_Anlysis/blob/main/images/randomforests.png)
- Our balanced accuracy score increased to 79%.
- High-Risk precision renmains low, at 4%, while the recall is 67%
- There is a lower number of false positives, increasing low-risk sensitivity to 91% with 100% precision.
- F1 score is 7%

### EasyEnsembleClassifier Model
![easyensemb](https://github.com/nedflowers/Credit_Risk_Anlysis/blob/main/images/easyensemb.png)
- Our balanced accuracy score is highest in this model with 93%.
- High-Risk precision renmains low, at 7%, while the recall is 91%.
- There is a lower number of false positives, increasing low-risk sensitivity to 94% with 100% precision.
- F1 score is 14%

## Summary
The above models show weak precision in performing credit-risk analysis. Each of the corrsponding F1 scores are relatively low, which points to a pronounced imbalance between sensitivity and precision. With the Ensemble models, we saw some improvement with sensitivity of high-risk credit. In particular, the EasyEnsemble model has an average recall score of 94%, detecting almost all high-credit risk. However, with precision remaining consistently low throughout the models, we can deduce there is a high number of low-risk credits being erroneously classified as high-risk. This could have a damaging effect on the bank's credit strategy and alienate potential customers, losing out on that profit. Due to the reasons outlined above, I do not recommend the bank to use any of the aforementioned models.