# Credit Card Fraud Detection

**Goal:**<br>
Create a Python model that captures the highest percentage of fraudulent credit card transactions within a data set of 30 variables, while minimizing false fraud predictions. Both the capture rate and accuracy rate of models created in the analysis serve as important metrics. A model that is very liberal in classifying transactions as "fraudulent" would likely capture a high percentage of actual fraudulent transactions, though potentially at the cost of erroneously labeling legitimate transactions as "fraudulent." The goal of the analysis is to create a model with optimal performance within both capture and accuracy, striking the best balance between the two.


**Findings:**<br>
The **logistic regression model** was the most effective model for this data set as **it captured the highest percentage of fraudulent transactions at 96%.** This high capture rate is valuable as it allows for automated detection of a larger number of fraud transactions before they are processed, reducing chargeback costs associated with fraud disputes. Additionally, deployment of an improved model would build trust and loyalty with customers, improve the bank's reputational advantage, reduce regulatory penalties and legal fees, deter fraudulent transaction attempts, and offer the bank greater leverage in insurance negotiations.  

As a runner-up, the _neural network_ model also captured 96% of fraud transactions. However, the logistic regression model performed better overall because it resulted in fewer false fraud predictions. **It produced an impressive fraud precision rate of 94%**, 5 percentage points higher than that of the neural network model. An improved fraud precision performance is valuable for both the bank and customer because it reduces costly false fraud resolution cases. It also minimizes customer frustrations due to unnecessary freezes and declined transactions, strengthening customer loyalty.

The analysis assessed additional models with a perfect fraud precision rate of 100%, but the highest fraud capture rate among them was only 86%. This would leave far too many fraud transactions undetected when compared to the logistic regression model, so it should not be used. 

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


