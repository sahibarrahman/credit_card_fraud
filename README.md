**Background**
Credit card fraud happens when consumers give their credit card number to unfamiliar individuals, when cards are lost or stolen, when mail is diverted from the intended recipient and taken by criminals, or when employees of a business copy the cards or card numbers of a cardholder. In this notebook we will develop a  ML model using anonymized credit card transaction data. The challenge behind fraud detection is that frauds are far less common as compared to legal transactions.

**Introduction to Dataset**
The datasets contains transactions made by credit cards in September 2013 by european cardholders. This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.

Due to confidentiality issue, original features V1, V2,... V28 have been transformed with PCA, however, we may guess that these features might be originally credit card number, expiry date, CVV, cardholder name, transaction location, transaction date-time, etc.

The only features which have not been transformed with PCA are 'Time' and 'Amount'. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature 'Amount' is the transaction Amount, this feature can be used for example-dependant cost-sensitive learning.

Feature 'Class' is the response variable and it takes value 1 in case of fraud and 0 otherwise.

**Observation to Dataset**
* No missing values found
* Most the transaction amount falls between 0 and about 3000 and we have some outliers for really big amount transactions.
* Fraudulent transactions are occurring randomly over the two days analyzed. No clear indication that frauds occur more at late night or early morning.
* 50% of fraud transactions are below amount 10 EUR.




**Evaluation Metrics**
As our dataset is highly imbalanced, so we shouldn't use accuracy score as a metric because it will be usually high and misleading, instead use we will use f1-score, precision/recall score

