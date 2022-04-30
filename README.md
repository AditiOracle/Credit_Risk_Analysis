# Credit_Risk_Analysis
ML_Supervised
**Module 17**

**Challenge**

**Credit Risk Analysis**

**OVERVIEW:**

In this challenge, we tried to apply machine learning to solve a real-world challenge: credit card risk. Credit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans. We employed different techniques to train and evaluate models with unbalanced classes.

We have used  imbalanced-learn and scikit-learn libraries to build and evaluate models using resampling.

Using the credit card credit dataset from _LendingClub_, a peer-to-peer lending services company,

- Firstly, we **oversample** the data using the RandomOverSampler and SMOTE algorithms, and **undersample** the data using the ClusterCentroids algorithm.
- Then, we used a **combinatorial approach of over- and undersampling** using the SMOTEENN algorithm.
- Next, we compared **two new machine learning models** that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk.
- Once we&#39;re done, we evaluated the performance of these models.

**RESULTS:**

**We have high number of True Negative and False Positive:**

**True Negatives (TN)** - These are the correctly predicted negative values which means that the value of actual class is no and value of predicted class is also no. E.g. if actual class says this person will not do Fraud and predicted class tells you the same thing.

**False Positives (FP)** – When actual class is no and predicted class is yes. E.g. if actual class says this user will do Fraud but predicted class tells you that this user will not do the same.

**Accuracy:** The Accuracy is a great measure but only when you have symmetric datasets where values of false positive and false negatives are almost same. But in below models we have big gap between two and we have accuracy very low. Therefore, we have to look at other parameters to evaluate the performance of our model.

**Precision**  - Precision is the ratio of correctly predicted positive observations to the total predicted positive observations. The question that this metric answer is of all users that labeled as Low risk/High risk, how many actually are Low Risk/High risk? High precision relates to the low false positive rate.

**Recall ** (Sensitivity) - Recall is the ratio of correctly predicted positive observations to the all observations in actual class - yes. The question recall answers is: Of all the users that are High Risk/Low Risk, how many did we label as High Risk/Low Risk respectively?

**F1 score**  - F1 Score is the weighted average of Precision and Recall. Therefore, this score takes both false positives and false negatives into account. Intuitively it is not as easy to understand as accuracy, but F1 is usually more useful than accuracy, especially if you have an uneven class distribution. Accuracy works best if false positives and false negatives have similar cost. If the cost of false positives and false negatives are very different, it&#39;s better to look at both Precision and Recall.

**Random OverSampling Model:**

Accuracy Score 62%

Markup : 1. High Risk:

            1. Precision is 1%
            2. Recall is 60%
            3. F1 is 2%

      2. Low Risk
            1. Precision is 100%
            2. Recall is 65%
            3. F1 is 79%

**SMOTE Algorithm:**

Accuracy Score 65%

1. High Risk:

  1. Precision is 1%
  2. Recall is 64%
  3. F1 is 2%

2. Low Risk
  1. Precision is 100%
  2. Recall is 66%
  3. F1 is 79%

**ClusterCentroids Undersampling Algorithm:**

Accuracy Score 51%

1. High Risk:

  1. Precision is 1%
  2. Recall is 59%
  3. F1 is 1%

2. Low Risk

  1. Precision is 100%
  2. Recall is 43%
  3. F1 is 60%

**SMOTEEN Algorithm:**

Accuracy Score 64%

1. High Risk:

  1. Precision is 1%
  2. Recall is 70%
  3. F1 is 2%

2. Low Risk
  1. Precision is 100%
  2. Recall is 57%
  3. F1 is 73%

**Balanced Random Forest Classifier Model:**

Accuracy Score 65%

1. High Risk:

  1. Precision is 1%
  2. Recall is 64%
  3. F1 is 2%

2. Low Risk
  1. Precision is 100%
  2. Recall is 66%
  3. F1 is 79%

**Easy Ensemble Classifier Model:**

Accuracy Score 80%

1. High Risk:

  1. Precision is 4%
  2. Recall is 68%
  3. F1 is 7%

2. Low Risk
  1. Precision is 100%
  2. Recall is 91%
  3. F1 is 95%

**SUMMARY:**

In above Models, Accuracy is very low except the Easy Ensemble Classifier Model. In this business use case, where we are analyzing the Credit Risk – Recall is very important factor. It is okay to classify a legit transaction as fraudulent — it can always be reverified by passing through additional checks. But it is definitely not okay to classify a fraudulent transaction as legit (false negative).

Recall more than 68% is considered as fair but I think we can use better models or algorithms to improve the Recall in High Risk scenarios.
