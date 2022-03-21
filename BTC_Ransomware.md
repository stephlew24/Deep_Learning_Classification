## **Use Deep Learning to Classify BTC Ransomware Addresses**

### **Abstract**
This analysis attempts to classify Bitcoin addresses that participate in Ransomware transactions and cyber attacks. On May 8th, 2021 the hacking group known as DarkSide targeted the Colonial Pipeline resulting in critical oil and gas infrastructure being taken out of operation which required $2.3M in Bitcoin be paid to DarkSide as ransom. With that in mind, I wanted to train a model on wallet addresses that have been involved in known ransomware transactions from 2011 to 2018 to help identify these addresses and analyze their transaction behavior. 

### **Design**
I classified these addresses based on the characteristics of their transactions using a Deep Learning model. I modelled a sample of 100K observations in the initial dataset and compared that against a dataset with engineered features. I then contrasted those results with a Logistic Regression and Random Forest to see which performed better. I optimized these models for F2 to maximize the amount of correct classifications.


### **Data**
I have downloaded a curated dataset from [UCI](https://archive.ics.uci.edu/ml/datasets/BitcoinHeistRansomwareAddressDataset) that takes the original [Elliptic](https://www.kaggle.com/ellipticco/elliptic-data-set) dataset of Bitcoin transactions from 2009 to 2018 and labels known ransomware attacks based on prior research. The dataset contains a time-series of around 3M observations and 10 features.

### **Algorithms/Models**
Feature Engineering

- Use EDA to identify the features most suitable for modeling.
- Transform non-normally distributed features for better performance.
- Added additional feature showing the number of times an address appeared in the dataset and day of the week.

I tested a Logistic Regression, Random Forest, and MLP. The Random Forrest was the best performer.

Model Evaluation

Weighted MLP NN
Accuracy: 0.831
F1: 0.191
F2: 0.359
Precision: 0.107
Recall: 0.865
Log-loss: 2.811
ROC_AUC: 0.935

MLP NN
Accuracy: 0.983
F1: 0.454
F2: 0.356
Precision: 0.838
Recall: 0.312
Log-loss: 0.587
ROC_AUC: 0.939

Random Forest
Accuracy: 0.977
F1: 0.545
F2: 0.575
Precision: 0.500
Recall: 0.598
Log-loss: 0.790
ROC_AUC: 0.931

Logistic Regression
Accuracy: 0.696
F1: 0.095
F2: 0.198
Precision: 0.051
Recall: 0.700
Log-loss: 10.517
ROC_AUC: 0.773

### **Tools**
SQL for data storage and sampling
Numpy and Pandas for data manipulation
Scikit-learn and Keras for modeling
Seaborn for plotting
