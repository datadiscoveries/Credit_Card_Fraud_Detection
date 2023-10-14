# Credit Card Fraud Detection

**Goal:**<br>
Create a Python model that effectively captures fraudulent credit card transactions within a data set of 30 variables, while minimizing false fraud predictions.


**Findings:**<br>
The **logistic regression model** was the most effective model for this data set as it **_captured the highest percentage of fraudulent transactions at 96%_.** This high capture rate is valuable as it allows for automated detection of a larger number of fraud transactions before they are processed, reducing chargeback costs associated with fraud disputes. Additionally, deployment of an improved model would build trust and loyalty with customers, improve the company's reputational advantage, reduce regulatory penalties and legal fees, deter fraudulent transaction attempts, and enhance company leverage within insurance negotiations.  

As an alternative competing model option, the _neural network_ model also captured 96% of fraud transactions. However, the logistic regression model performed better overall because it **_resulted in fewer false fraud predictions. It produced an impressive fraud precision rate of 94%_**, significantly greater than the neural network model's rate of 89%. An improved fraud precision performance is valuable because it improves operational efficiencies by allowing the credit card business to allocate fewer resources towards investigating and resolving costly false fraud cases. Additionally, it reduces customer frustrations from declined transactions and freezes attributed to false fraud predictions, enhancing customer loyalty, and improving the business's reputation. Other models in the analysis with a fraud precision rate of 100% would have likely predicted all, or nearly all, of their fraud predictions correctly on new real-world transactions. However, those models allowed too many actual fraud transactions to go undetected because the highest fraud capture rate among these models was only 86%. 

**Coding and Analysis Steps:**<br>
* Preprocessing
  * 28 of the 30 features in the dataset were transformed with PCA prior to this analysis for confidentiality reasons
  * Charted feature distributions to explore data transformation opportunities
  * Checked for multicollinearity 
  * Charted summary statistics to look for more data transformation opportunities
  * Rescaled two features
  * Shuffled and split the data into train, test, and validation sets
* Created and compared a few models
* Balanced and split the data
* Created and compared several models on the balanced data sets
  * Precision and recall were used over accuracy to measure performance because the data was very imbalanced, and both misclassification types (false positives and false negatives) have significant business implications



