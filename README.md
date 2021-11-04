# Cross Selling
[Cross selling](https://www.oberlo.com/ecommerce-wiki/cross-selling) is the ability to sell more products to a customer by analyzing the customer’s shopping trends as well as general shopping trends and patterns which are in common with the customer’s shopping patterns. The idea of cross selling can be extended to any organization, irrespective of whether it is an online or offline retailer or whether it is selling its products to the end users of whole sellers.

In this notebook, we explore [association rule-mining](https://www.geeksforgeeks.org/association-rule/) with [FP-Growth algorithm](https://www.softwaretestinghelp.com/fp-growth-algorithm-data-mining/) implemented in the [orange3-associate package](https://pypi.org/project/Orange3-Associate/). Then, we wiil illustrate the concept of [market basket analysis](https://smartbridge.com/market-basket-analysis-101/) for a `toy dataset`, and finally we apply the same concepts to our retail transactions dataset.

**A snapshot of the result:**
<p align="center">
<img src="result_table.png" width="500"/>
</p>

The pattern that the rule states in the equation is easy to understand—people who bought yogurt, whole milk, and tropical fruit also tend to buy root vegetables. Let’s try to understand the metrics: 
- Support of the rule is 228, which means, all the items together appear in 228 transactions in the dataset. 
- Confidence of the rule is 46%, which means that 46% of the time the antecedent items occurred we also had the consequent in the transaction (i.e. 46% of times, customers who bought the left side items also bought root vegetables).
- Lift means that the probability of finding root vegetables
in the transactions which have yogurt, whole milk, and tropical fruit is greater than the normal probability of finding root vegetables in the previous transactions (2.23). Typically, a lift value of 1 indicates that the probability of occurrence of the antecedent and consequent together are independent of each other. Hence, the idea is to look for rules having a lift much greater than 1. In our case, all the previously mentioned rules are good quality rules.
