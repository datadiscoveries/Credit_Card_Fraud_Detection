# Credit Card Fraud Detection

**Goal:**<br>
The goal of this analysis is to find the best model for capturing fraudulent transactions using a data set of 30 features, while minimizing false fraud predictions.


**Findings:**<br>
The logistic regression model was selected as the final model as it captured the highest percentage of fraudulent transactions at 96%. This high capture rate is valuable as it allows for automated detection of a larger number of fraud transactions before they are processed, reducing chargeback costs associated with fraud disputes. Additionally, it builds trust and loyalty with customers, increases the business's competative edge, minimizes regulatory penalties and legal fees, deters fraudsters, and offers a strengthened position for fraud insurance negotiations.  

This analysis found that the neural network also captured 96% of fraudulent transactions, however the logistic regression model was selected because it produces a lower rate of false fraud predictions. Its fraud precision rate is 94%, while the neural network's rate is only 89%. This improved fraud precision performance is valuable because it improves operational efficiencies by allowing the business to allocate fewer resources towards investigating and resolving false fraud cases. Additionally, it reduces customer frustrations from declined transactions and freezes attributed to false fraud predictions, enhancing customer loyalty and improving the business's reputation. 

**Process:**<br>
* Preprocessing
  * 28 of the 30 features have already been transformed with PCA for confidentiality reasons
  * Charted feature distributions to look for more data transformation opportunities
  * Checked for multicollinearity 
  * Charted summary statistics to look for more data transformation opportunities
  * Rescaled two features
* Shuffled and split the data into train, test, and validation sets
* Created and compared a few models
* Balanced and split the data
* Created and compared several models on the balanced data sets
  * Precision and recall were used as performance metrics rather than accuracy because the data is very imbalanced, and both misclassification types (false positives and false negatives) have significant business implications



