# Credit Card Fraud Detection

**Goal:**<br>
Create a Python model that effectively captures fraudulent credit card transactions within a data set of 30 variables, while minimizing false fraud predictions.


**Findings:**<br>
The **logistic regression model** was the most effective model for this data set as it **captured the highest percentage of fraudulent transactions at 96%.** This high capture rate is valuable as it allows for automated detection of a larger number of fraud transactions before they are processed, reducing chargeback costs associated with fraud disputes. Additionally, deployment of an improved model would build trust and loyalty with customers, improve the company's reputational advantage, reduce regulatory penalties and legal fees, deter fraudulent transaction attempts, and enhance company leverage within insurance negotiations.  

As an alternative model option, the _neural network_ model also captured 96% of fraud transactions. However, the logistic regression model performed better overall because it resulted in fewer false fraud predictions. It produced an impressive fraud precision rate of 94%, significantly greater than the neural network model's rate of 89%. An improved fraud precision performance is valuable because it reduces strain on resources within the investigation and resolution of costly false fraud cases for both the company and the customer. Additionally, it minimizes customer frustrations due to unnecessary declined transactions and freezes, which further improves customer loyalty and strengthens the company's reputation.

The analysis explored the performance of additional models resulting in a perfect fraud precision rate of 100%. Deployment of any of these models would likely produce the most accurate predictions within new transactions. However, the highest fraud capture rate among these models was only 86%. This would result in far too many undetected actual fraud transactions, so it cannot be used. 

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
  * Precision and recall were used to measure model performance, rather than accuracy, because the dataset was very imbalanced. Additionally, both misclassification types, false positives and false negatives, have significant business implications



