# Product Focus & Recs Using Pareto, Apriori, & Association

## Processing Data

Let's clean and process the [UCI Machine Learning Online Retail data set](https://archive.ics.uci.edu/ml/machine-learning-databases/00352/Online%20Retail.xlsx) so it's ready to use later for analysis and modeling (e.g., CLTV, market basket). I've mixed, matched, and amended the cleaning logic from [here](https://github.com/koshika15/Predict-sales-of-an-online-retail-store/blob/master/A.%20Data%20Aquisition%20%26%20Wrangling.ipynb) and [here](https://github.com/amir-hojjati/Data-Analysis-Online-Retail-Transactions/blob/master/Data-Preprocessing/Preprocessing-and-Cleaning.ipynb). 

The data set includes >500,000 transactions for a UK-based online retailer that specializes in gift items with a strong wholesaler customer base. Let's process it so it's clean and  Variable definitions:  

**InvoiceNo**: 6-digit number unique to each transaction. Starting with C indicates cancellation
<br>**StockCode**: 5-digit number unique to each product
<br>**Description**: product name
<br>**Quantity**: number of each item per transaction
<br>**InvoiceDate**: date and time of transaction
<br>**UnitPrice**: price per unit in British pounds
<br>**CustomerID**: 5-digit number unique to each customer
<br>**Country**: where customer lives 

We'll walk through the logic of addressing inconsistencies in each of the variables. We'll also create additional useful features. At the end we'll have a clean, workable transactions data set to use. 

## Pareto, Apriori, & Associations

Let's work with the retail transactions data we [cleaned and processed](https://github.com/hrishipoola/Product_Pareto_Apriori_Association), focusing on customers from Germany. We'll explore Top 10 products and apply Pareto, or the 80/20 rule, in which roughly 80% of effects come from 20% of the causes (e.g., 20% of products generate 80% of sales). This can help us focus on the core group of customers and products that generate the overwhelming majority of sales. In the future, we'll expore time series trends with this data set in more depth. 

Next, we'll uncover products that are more likely to be purchased together in order to develop recommendations and bundles. As a large set of unique items creates an unmanageable number of combinations and association rules, we'll first apply the Apriori algorithm to prune item sets. Apriori is based on the principle that subsets of frequent sets are also frequent and prunes large numbers of item sets by only focusing on items that have a minimum level of support (purchase frequency). We'll also visualize how different levels of minimum support affect the number of item sets created. 

Even a pruned frequent item set can generate an unruly number of association rules. Let's prune our association rules to a more manageable handful. For the pruning metric, let's choose lift, a measure of likelihood for items to co-occur. Lift is >1 for items that co-occur more than we'd expect if they were independently distributed across transactions. We'll also visualize how the number of association rules changes with increasing levels of lift criteria. We'll uncover products more likely to be purchased together that we can use to develop recommendations or bundle. Lastly, we'll visualize these associations through a heatmap and a parallel plot.  


