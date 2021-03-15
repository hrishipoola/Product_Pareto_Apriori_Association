# Product Pareto, Apriori, & Association

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

