# Credit Card Fraud Detection

**Analysis:**<br>
The goal of this analysis is to find the best model for capturing fraudulent transactions on a data set of 30 features, while maintaing a very low level of false fraud predictions.


**Findings:**<br>
The logistic regression model was selected as the final model as it captured the highest percentage of fraudulent transactions at 96%. Deploying a model with the highest fraud recall performance would likely save time and money for the business and its customers by increasing the opportunity to take action on a larger volume of transactions that are truly fraudulent. It would also help create and strengthen a reputation for the company as one that cares for the security of its customers and takes effective action in managing cases of fraud.  

While the fraud recall performance for both the neural network and logistic regression models were same, the logistic regression model was chosen because it returned a better fraud precision performance, by 5% percentage points. Its rate is 94%, while the neural network model’s rate is only 89%. This improved fraud precision performance would help reduce the number of false fraud cases reviewed by personnel and unneeded  customer account locks.


