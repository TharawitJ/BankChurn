﻿**Bank Churn project** to probability prediction.
https://www.kaggle.com/code/tharawitj/bankchurn-xgb-lgbm-cat-voting
---
Data was collected by https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud
### CRISP-DM processes for data mining.
1. Business Understanding
    * Bank is the company that give the financial service to customers in many ways such as saving for interest rate, loaning, and credit card. 
    * To keep customer satisfation, bank need to create new financial product, keep high quanlity of service.

2. Data Understanding
    * Imbalance dataset with 78.8% and 21.2% (Stay and Exited) with 165,034 in totals.
    * Dataset have 3 features that maybe not useful (id, CustomerId, Surname).
    * No missing and null or duplicate value.

3. Data Preparation
    * Drop features name id, CustomerId and Surname.
    * Use one hot encoder for categorical features.

4. Modeling
    * Train test split by stratify y.
    * Train 3 models and voting ensemble.
        * XGB Classifier
        * LightGBM Classifier
        * CatBoost Classifier

5. Evaluate Model
    * Hyperparamater tuning by GridSearchCV with every models.
    * Focusing on ROC-AUC probability score.
        * XGB Classifier : 88.97%
        * LightGBM Classifier : 88.92%
        * CatBoost Classifier : 88.92%
        * Voting Ensemble : 88.97%
    * Evaluate trained models on submission dataset.
        * XGB Classifier and Voting ensemble both have closely the same results testing by difference in average probability between both models and result is only 8.4% higher on XGB Classifier.
    * In conclusion XGB Classifier model get better in result. Easy to modify because it's only one model but voting ensemble is conclude 3 models.

6. Deployment
    * The created model can be use for exited probability prediction that can be help bank to know who might be exit.

---
**References :** 
https://www.kaggle.com/code/akhiljethwa/playground-s4e1-eda-modeling-xgboost#5.-Visualizations-
https://www.kaggle.com/code/iqbalsyahakbar/ps4e1-3rd-place-solution
