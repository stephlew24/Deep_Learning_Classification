## **BTC Ransomware Transaction Classification - MVP**

As Bitcoin has increased in growth and popularity over the years, several high profile ransomware attacks have been conducted requiring ransoms paid in Bitcoin. For example, on May 8th, 2021 the hacking group known as DarkSide targeted the Colonial Pipeline resulting in critical oil and gas infrastructure being taken out of operation which required $2.3M in Bitcoin be paid to DarkSide as ransom. With that in mind, I wanted to train a model on addresses that have been involved in known ransomware transactions from 2011 to 2018 to help identify these addresses and their transaction behavior.

I trained a Logistic Regression, Random Forest, and a Neural Network to see which performed the best at classifying these transactions:

With an emphasis on Recall, I have obtained the follow initial results:


|      Model Name     | Accuracy | F1-Score | F2-Score | Precision | Recall | Log-loss | ROC_AUC |
| ----------- | ----------- | ----------- | ----------- | ----------- | ----------- |
| Logistic Regression |  0.687   |   0.102  |   0.212   |  0.054 |   0.773  |  10.799  |  0.763  |
| Random Forest |  0.975   |  0.520   |   0.560   |  0.464 |   0.591  |  0.862  |  0.934  |
| Neural Net |  0.982   |  0.416   |   0.320   | 0.833  |   0.278  |  0.594  |  0.917  |
| Weighted Neural Net |  0.778   |  0.144   |   0.285   | 0.079  |   0.816  |  0.840  |  0.890  |
| Random Model |   0.505  |   0.047  |   0.104   |  0.025 |  0.536  |  17.097  |  0.500  |


I plan to continue tuning the Neural Net to improve the results since it has not been parameter tuned liked the others. Additionally, I have sourced historical bitcoin price data to examine if these transactions typically happen around a certain price level.