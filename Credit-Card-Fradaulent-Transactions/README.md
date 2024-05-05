Problem Statement:

A credit card is one of the most used financial products to make online purchases and payments. Though the Credit cards can be a convenient way to manage your finances, they can also be risky. Credit card fraud is the unauthorized use of someone else's credit card or credit card information to make purchases or withdraw cash.
It is important that credit card companies are able to recognize fraudulent credit card transactions so that customers are not charged for items that they did not purchase. 

We have to build a classification model to predict whether a transaction is fraudulent or not.

Data Source:
The dataset contains transactions made by credit cards in September 2013 by European cardholders. This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.


Purpose:
We will be creating a model to predict if a transaction is fraudulent or not. In real time this would help the bank to reject any transaction which seems unauthorised and ultimately save the customer from a potential fraud.


Methodology:

The approach followed is segmented into the subsequent phases: 
1.Initial dataset input <br />
2.Exploratory Data Analysis <br />
3.Feature Engineering i.e. transforming the categorical attributes of dataset

4.Scaling the dataset <br />
5.Splitting the dataset into training and test datasets <br />
6.Using SMOTE Data sampling for achieving data consistency <br />
7.Training of classification model <br />
8.Prediction of fraudulent transactions.

Data Sampling:

The dataset comprises 284,807 credit card transactions , among which there are 492 instances of fraud. Due to the limited number of fraudulent transactions, they are categorized as the minority class, while non-fraudulent transactions represent the majority class. 
Hence, the dataset shows a class imbalance.

Why to avoid generic random oversampling and undersampling?
Because with random oversampling ,we add random set of copies of minority class examples to the data.
This may increase the likelihood of overfitting.

Using random undersampling method,we delete data from the majority class.
This can be highly problematic, as the loss of such data can make the decision boundary 
between minority and majority instances harder to learn, resulting in a loss in classification performance.

SMOTE (Synthetic Minority Over-sampling Technique) is an oversampling method specifically designed for addressing imbalances in the minority class . It operates by generating new samples within the minority class through a process of synthesizing existing samples. The underlying principle involves delineating a line between data points within the minority class and subsequently creating new samples along this line.
By focusing on data points in close proximity within the minority class, SMOTE aims to tackle the overfitting issues associated with random oversampling technique.

Model Training:
Since this is a classification problem, we have decided to go with Random Forest Algorithm to create our prediction model.

The Random Forest algorithm is a robust tree-based learning technique widely employed in Machine Learning.
It operates by constructing multiple Decision Trees during the training phase. Each tree is built using a random subset of the dataset and evaluates a random subset of features within each partition. 
This inherent randomness introduces diversity among individual trees, tackling the risk of overfitting and enhancing overall prediction accuracy.
 During prediction, the algorithm aggregates the outcomes of all trees through either voting (for classification tasks) or averaging (for regression tasks). 

Random Forests are extensively utilized for classification and regression tasks due to their capability to handle intricate datasets, alleviate overfitting, and deliver dependable forecasts across different scenarios.

Model Prediction Metrics and Visualization: <br />

Confusion Matrix:<br />
A confusion matrix provides valuable insights into the accuracy of our predictions and their alignment with the actual values.

Precision-Recall Curve:<br />
As implied by its name, this curve directly illustrates precision (on the y-axis) against recall (on the x-axis).
This is especially valuable in scenarios which are highly imbalanced, where the number of negatives are significantly greater than the positives (such as when the number of fraudulent transactions are  far less than legitimate transactions).
In such cases, our primary focus is on accurately identifying potential fraud transactions.

Precision:<br />
It represents the ratio of True Positives to all Positive predictions. In our context, it signifies the proportion of transactions correctly identified as fraudulent  out of all transactions.

Recall:<br />
It measures our model's ability to correctly identify True Positives. Therefore, concerning fraud transactions, recall indicates how many we accurately identified out of all those the true fraud transactions .








