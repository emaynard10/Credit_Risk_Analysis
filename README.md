# Credit_Risk_Analysis

Using supervised machine learning to predict credit risk
Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, the analysis uses oversampling with the RandomOverSampler and SMOTE algorithms, and undersampling using the ClusterCentroids algorithm. Then, using a combinatorial approach of over- and undersampling it applies the SMOTEENN algorithm. Next, it compares two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk.

#### Tools: Jupyter Notebooks, Pandas, Python, supervised machine learning algorithms
#### Resources: LendingClub credit card data LoanStats_2019Q1.csv.zip

## Overview of the analysis:
The purpose of this analysis is to use supervised machine learning to predict credit risk. Because there are so many fewer risky loans than good loans it is an unbalanced classification problem. The anlaysis will look at oversampling, undersampling, and decision tree classifiers ot try and determine the best model for this problem. In order to do so the analysis will look at the accuracy score, precision, recal, and F1 scores from 6 different modesl to determine if one is better at detecting risky loans better than the others.

## Results: Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all six machine learning models. Use screenshots of your outputs to support your results.

We cannot depend soley on accuracy score since the model could do well detecting all the low risk loans and miss the few risky loans and still get a good accuracy score. Therefore the precision and recal will also be considered and well as the F1 score. Precision divides the number of true positives detected by the total positves or how reliable are positive classifications. Recall is more of how likely the model is to detect the risky loans, calculated by true 
positive over true positvies plus false negatives. Precision will be more important for this data because predicted positives are likely true positives; but a number of other true positives may not be predicted which means that there will be some good loans that are not awarded, but there mon't be many risky loans that aren't detected. F1 score is 2(Precision * Sensitivity)/(Precision + Sensitivity), if the score is low it means there is a large imbalance between precision and recall which is true of this dataset. All models did predictably well at detecting the low risk loans. So the analysis needs to focus on how many of the high risk loans is it detecting without flagging too many good loans as high risk unecesarily. 

* Oversampling with RandomOverSampler
accurcacy score- 65%
![Screen Shot 2022-08-08 at 3 49 45 PM](https://user-images.githubusercontent.com/99676466/183520666-2dc58a6d-31ef-4d1e-89cb-63216d2ca0d5.png)
 
* Oversampling with SMOTE
accuracy acore- 64%
![Screen Shot 2022-08-08 at 3 48 20 PM](https://user-images.githubusercontent.com/99676466/183520472-8afdb60d-f9cb-49b9-bc8d-9604e1832da6.png)

* Undersampling with ClusterCentroids
accuracy score-53%
![Screen Shot 2022-08-08 at 3 50 32 PM](https://user-images.githubusercontent.com/99676466/183520760-696e6801-5549-4909-8e0d-014b86e69de4.png)

* Combination sampling with SMOTEEN
accuracy_score - 64%
![Screen Shot 2022-08-08 at 3 51 15 PM](https://user-images.githubusercontent.com/99676466/183520852-730ee8af-5594-4a13-83d3-aed1b1701cfa.png)


* Ensemble machine learning with BalancedRandomForestClassifier
accuracy score- 67%
![Screen Shot 2022-08-08 at 3 45 54 PM](https://user-images.githubusercontent.com/99676466/183520179-13cbdcaa-7380-42a1-9231-7b04da623e43.png)

* Ensemble machine learning with EasyEnsembleClassifier
![Screen Shot 2022-08-08 at 3 47 10 PM](https://user-images.githubusercontent.com/99676466/183520308-af43b8a5-84e6-4e1a-93f4-9929efd9125d.png)


## Summary:

None of the oversampling models did well with precision on the high risk loans, but they also didn't have particularily high recalls either. This is concerning in that it has trouble predicting when a high risk loan is actually high risk. The f1 scores are all low with oversampling as well because the precision was so low on all of them that the recall was much better. The recall was best for the combination sampling SMOTEEN model, at .71, which also had the high accuracy of the four sampling models, yet it was only 71% accurate. 

The ensemble decision tree classifiers did a bit better, with the Easy Ensemble Classifier having the only good accuracy score at 93%. This model also had the best recall score at .91, but this was at the sacrifice of the precision which was very low. The Balanced Random Forest was the opposite with the best precision score and a terrible recall. Because recall is more important where Overlooked Cases (False Negatives) are more costly than False Alarms (False Positive), the Easy Ensemble model is the only one I would recommend so tooo many risky loans are not approved. 

The analysis would benefit from some more constraints, perhaps if the loan is over a certain amount of money zero risk tolerance would be appropriate, but under a certain amount of money there is an acceptable amount of risk. Additionally, focusing on the features that contibute the most could help the model. 

