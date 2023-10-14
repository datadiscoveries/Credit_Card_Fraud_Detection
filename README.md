# Credit Card Fraud Detection

**Goal:**<br>
Create a Python model that captures the highest percentage of fraudulent credit card transactions within a data set of 30 variables, while minimizing false fraud predictions. Both "capture" and "accuracy" metrics have important meaning in this analysis. For example, a model classifying every transaction as fraudulent would successfully capture 100% of fraudulent transactions, but it would also predict almost every transaction inaccurately, resulting in every transaction being investigated as potential fraud. The goal is to assess both metrics to determine the best model.


**Findings:**<br>
The **logistic regression model** was the most effective model for this data set as **it captured the highest percentage of fraudulent transactions at 96%.** This high capture rate is valuable as it allows for automated detection of a larger number of fraud transactions before they are processed, reducing chargeback costs associated with fraud disputes. Additionally, deployment of an improved model would build trust and loyalty with customers, improve the bank's reputational advantage, reduce regulatory penalties and legal fees, deter fraudulent transaction attempts, and improve the bank's position within insurance negotiations.  

As a runner-up, the _neural network_ model also captured 96% of fraud transactions. However, the logistic regression model performed better overall because it resulted in fewer false fraud predictions. **It produced an impressive fraud precision rate of 94%**, 5 percentage points higher than that of the neural network model. An improved fraud precision performance is valuable for both the bank and customer because it reduces costly false fraud resolution cases. It also minimizes customer frustrations due to unnecessary freezes and declined transactions, strengthening customer loyalty.

The analysis explored the performance of additional models resulting in a perfect fraud precision rate of 100%. Deployment of any of these models would likely result in the most accurate classifications on new transactions data, but the highest fraud capture rate among these models was only 86%. This would leave far too many fraud transactions undetected when compared to the logistic regression model, so it should not be used. 

**Steps Taken and Model Development within Python Script:**<br>
* Preprocessing steps
  * Transformed 28 of the 30 variables in the dataset with PCA prior to the analysis for confidentiality reasons
  * Charted feature distributions to explore data transformation opportunities
  * Checked for multicollinearity 
  * Charted summary statistics to look for more data transformation opportunities
  * Rescaled two features
  * Shuffled and split the data into train, test, and validation sets
* Created and compared a few models
* Balanced and split the data
* Created and compared several models on the balanced data sets
  * Precision and recall were used to measure model performance, rather than accuracy, because the dataset was very imbalanced. Additionally, both misclassification types, false positives and false negatives, result in significant costs


