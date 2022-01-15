# Credit Risk Analysis
### Comparing Machine Learning Modules to Find the Best Predictor of Credit Risk

Our company has tasked me with implementing machine learning to identify high-risk and low-risk borrowers to expedite the lending process and make more accurate predictions. To do so, I tested several different machine learning models. Both sensitivity (catching all the high-risk borrowers) and precision (not flagging low-risk borrowers as high-risk) are important in choosing to whom we should lend. We do not want to lend to clients who default, nor do we want to lose out on business by flagging low-risk borrowers as high risk. In light of that, I generated a complete set of summary statistics for each machine learning model in order to compare their strengths and weaknesses. Because low-risk clients by far outnumber high risked clients, the models I used resample the data so that high-risk and low-risk clients would be equally represented. The results are listed below.

## Results

### Naive Random Oversampling

The first model I attempted was naive random oversampling. The balanced accuracy score and the classification report are below.

![naive random oversampling ba score](https://github.com/LiShanDa2021/credit_risk_analysis/blob/main/images/ba%20oversampling.png?raw=true)

![naive random oversampling classification report](https://github.com/LiShanDa2021/credit_risk_analysis/blob/main/images/naive%20random%20oversampling.png?raw=true)

The balanced accuracy score is an unimpressive .61. As you can see, this model is much more accurate for predicting low-risk clients than it is high-risk meaning it is prone to false negatives with a recall of only .6. The precision is also very poor for identifying high-risk clients.


### SMOTE Oversampling

Below are the stats for the SMOTE oversampling model.

![smote oversampling ba score](https://github.com/LiShanDa2021/credit_risk_analysis/blob/main/images/ba%20smote.png?raw=true)

![smote oversampling classification report](https://github.com/LiShanDa2021/credit_risk_analysis/blob/main/images/smote%20oversampling.png?raw=true)

This model performs only slightly better with a ba score of .62. It’s recall is .60 for predicting high-risk borrowers indicating that it is just as prone to false negatives as the previous model.

### Undersampling

![undersampling ba score](https://github.com/LiShanDa2021/credit_risk_analysis/blob/main/images/ba%20undersampling.png?raw=true)

![undersampling classification report](https://github.com/LiShanDa2021/credit_risk_analysis/blob/main/images/undersampling.png?raw=true)

This model comes in with an underwhelming ba score of .62 rounded up and a poor recall for high risk clients at .59 along with characteristic poor precision.


### SMOTEENN (Combination over-under sampling)

![smoteenn ba score](https://github.com/LiShanDa2021/credit_risk_analysis/blob/main/images/ba%20smoteenn.png?raw=true)

![smoteenn classification report](https://github.com/LiShanDa2021/credit_risk_analysis/blob/main/images/smoteenn.png?raw=true)

This model’s ba score is par for the course and its precision is just as poor as the other models. One advantage it does have is it is less likely to give high-risk lenders a pass. Its recall of .72 indicates that it results in fewer false negatives.

### Ensemble Sampling

![ensemble ba score and classification report](https://github.com/LiShanDa2021/credit_risk_analysis/blob/main/images/ba%20and%20classification%20report%20ensemble.png?raw=true)

Though this model has a higher ba score, its precision and recall for high-risk borrowers is low and is therefor not recommended.
### Easy Ensemble AdaBoost Classifier
I could not get the code for this to work. “¯\_(ツ)_/¯“

Actually, I did. Here are the BA scores and classification report.

![adaboost](https://github.com/LiShanDa2021/credit_risk_analysis/blob/main/images/Screen%20Shot%202022-01-15%20at%2011.01.00%20AM.png?raw=true)

Again, although the ba score is higher, it is prone to false negatives with a low recall for high-risk borrowers. I would not recommend this model.

## Summary
While the performance of the above models is underwhelming, we should consider their effectiveness in relation to the effectiveness of previous methods and their labor intensiveness in relation to that of the previous methods before we decide whether or not to implement them. If we are to use a model it should be the SMOTEENN method because that method generates far fewer false negatives with little trade-off with precision.


