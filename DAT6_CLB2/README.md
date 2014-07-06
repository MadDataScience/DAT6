Full Project Proposal

#### Title
Predicting Repeat Buyers

#### Project Summary
My project will be to predict which shoppers will become repeat buyers, using shopping history, demographic and business information.  Shoppers were offered a coupon for a particular item, and the question is which shoppers who use the coupon will return to purchase the same item again.

#### Objective
The objective is to create a model that predicts which shoppers will become repeat buyers.  Success will be measured in terms of precision, recall and predictive power. 

==================
#### Analysis plan

* Retrieve data — done
* Visualize dimensions — in progress
* Load transactions data (23 GB CSV file) into a database in order to access it
* Identify correlations between dimensions
* Build model to predict repeat buying (binary outcome)
* — How to test all of the different dimensions?  Anything other than “try them all”?
* — Look at second-order dimensions?  (Derived variables:  things like purchase frequency could be calculated for each customer from their transaction history.)
* — Evaluate precision, accuracy and predictive power of model

==================


#### Methods
##### Model.
* Logistic regression.  The model will assign each user a probability of becoming a repeat buyer.  Initially, the model will be used to categorize each user as a target (bought product at least once) or non-target (did not buy product).  Depending on the data and the results, additional modeling to distinguish high versus low repeat buyers may be done. 

##### Performance metrics.
* Precision:  The fraction of all predicted targets that are actual targets.  This is a measure of accuracy.
* Recall:  The fraction of all actual targets that predicted by the model.  This is a measure of completeness.
* Predictive power:  There are many ways to measure predictive power.  Unless I come up with a better idea, I’ll use ROC, which measures how well the model distinguishes targets from non-targets.  An ROC of 0.5 indicates chance performance (for a binary outcome), while an ROC of 1.0 indicates perfect performance.  ROC has the advantage of evaluating model performance across the full range of thresholds one might use in converting the model output (a continuous probability) to a binary result (target and non-target categories).

##### Tasks.
There are several things I’ll need to do.
* Characterize dataset:  Measure and visualize the range and distribution of each dimension in the dataset.  Determine if any data preparation needs to be done.
* Dimension reduction:  Determine which metrics to use in the model.  (Could use input on this one.  I could just try out a bunch of different variables, a couple at a time, and weed out ones that don’t do well, but there may be better ways to do this.  PCA?  Something else?  This is an area I don’t have experience in.)
* Build and test the model.  This will no doubt be iteratively.  I expect a baseline level of performance will be established, and then I will work to find ways I can make the model do better.  (There may also be types of models to test besides logistic regression.  I welcome any input on this.)
* Summarize results, quantitatively and graphically.  Build 12-minute presentation.

#### Dataset
This project is taken directly from Kaggle, where it's listed as the Acquire Valued Shoppers Challenge. The dataset has about 350 million rows, 300k shoppers, and about 20 dimensions. 

#### Links
* The data has already been curated and is available on Kaggle.  CSVs and meta info about the data here:  https://www.kaggle.com/c/acquire-valued-shoppers-challenge/data

———————
#### Data description (for reference)

##### Relational files
* transactions.csv - contains transaction history for all customers for a period of at least 1 year prior to their offered incentive
* trainHistory.csv - contains the incentive offered to each customer and information about the behavioral response to the offer
* offers.csv - contains information about the offers

##### Fields

HISTORY

1. id - A unique id representing a customer
2. chain - An integer representing a store chain
3. offer - An id representing a certain offer
4. market - An id representing a geographical region
5. repeattrips - The number of times the customer made a repeat purchase
6. repeater - A boolean, equal to repeattrips > 0
7. offerdate - The date a customer received the offer

TRANSACTIONS

1. id - see above
2. chain - see above
3. dept - An aggregate grouping of the Category (e.g. water)
4. category - The product category (e.g. sparkling water)
5. company - An id of the company that sells the item
6. brand - An id of the brand to which the item belongs
7. date - The date of purchase
8. productsize - The amount of the product purchase (e.g. 16 oz of water)
9. productmeasure - The units of the product purchase (e.g. ounces)
10. purchasequantity - The number of units purchased
11. purchaseamount - The dollar amount of the purchase

OFFERS

1. offer - see above
2. category - see above
3. quantity - The number of units one must purchase to get the discount
4. company - see above
5. offervalue - The dollar value of the offer
6. brand - see above

The transactions file can be joined to the history file by (id,chain). The history file can be joined to the offers file by (offer). The transactions file can be joined to the offers file by (category, brand, company). A negative value in productquantity and purchaseamount indicates a return.
