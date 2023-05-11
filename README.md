# Credit Card Fraud Detection

**Analysis:**<br>
The goal of this analysis is to find the best model for capturing fraudulent transactions on a data set of 30 features, while maintaing a very low allowance of false fraud predictions.


**Findings:**<br>
The logistic regression model was selected as the final model as it captured the highest percentage of fraudulent transactions at 96%. This high capture rate is valuable as it can help reduce financial losses by automating the detection of a larger number of fraud transactions before they are processed, reduce chargeback costs, build trust and loyalty with customers, increase the business's competative edge, help avoid regulatory penalties and legal fees, deter fraudsters, and help lower insurance costs.  

This analysis found that the neural network also captured 96% of fraudulent transactions, but and logistic regression models were same, the logistic regression model was determined to be more effective because it produces a lower rate of false fraud predictions. Its fraud precision rate is 94%, while the neural network's rate is only 89%. This improved fraud precision performance is valuable in that it can help the business allocate less resources towards investigating and resolving false fraud cases, reduce complications due to false fraud declined transactions and freezes, and improve customer satisfaction and loyalty.

Process:<br>
* Preprocessing
  * 28 of the 30 features have already been transformed with PCA for confidentiality reasons
  * Charted feature distributions to look for more data transformation opportunities
  * Checked for multicollinearity 
  * Charted summary statistics to look for more data transformation opportunities
  * Rescaled two features
* Shuffled and split the data into train, test, and validation sets
* Created and compared a few models
* Balanced and split the data
* Created and compared several models on the balanced the data sets
  * Precision and recall were used as performance metrics rather than accuracy because the data is very imbalanced, and both false positive and false negative implications significantly impact the business



