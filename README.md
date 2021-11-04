# Cross Selling
[Cross selling](https://www.oberlo.com/ecommerce-wiki/cross-selling) the practice of selling additional products to an existing customer by analyzing the customer’s shopping patterns trends. Cross-selling is famously exemplified by Amazon’s “Customers Who Bought This Item Also Bought” feature. The idea of cross selling can be extended to any organization, irrespective of whether it is an online or offline retailer or whether it is selling its products to the end users of whole sellers.

In this notebook, we explore [Association Rules Mining](https://www.geeksforgeeks.org/association-rule/), using [FP-Growth algorithm](https://www.softwaretestinghelp.com/fp-growth-algorithm-data-mining/) implemented in the [orange3-associate package](https://pypi.org/project/Orange3-Associate/), for a [market basket analysis](https://smartbridge.com/market-basket-analysis-101/), which identified which combination of products are often purchased by customers. Then, we will apply the concepts to an `retail transactions dataset`.

**A snapshot of the result:**
<p align="center">
<img src="result_table.png" width="500"/>
</p>

The pattern that the rule states in the equation is easy to understand—people who bought `yogurt` and `tropical fruit` also tend to buy `root vegetables`. Let’s try to understand the metrics: 
- `Support` of the rule is 228, which means, all the items together appear in 228 transactions in the dataset. 
- `Confidence` of the rule is 46%, which means that 46% of the time the antecedent items occurred we also had the consequent in the transaction (i.e. 46% of times, customers who bought `yogurt` and `tropical fruit` also tend to buy `root vegetables`).
- `Lift` means that the probability of finding `root vegetables`
in the transactions which have `yogurt` and `tropical fruit` is greater than the normal probability of finding `root vegetables` in the previous transactions (2.23). Typically, a lift value of 1 indicates that the probability of occurrence of the antecedent and consequent together are independent of each other. Hence, ***the idea is to look for rules having a lift much greater than 1***. In our case, all the previously mentioned rules are good quality rules.
