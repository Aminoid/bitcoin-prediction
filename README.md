## Predicting Bitcoin Price Variations using Bayesian Regression
[1]: https://github.com/Aminoid/bitcoin-prediction/blob/master/Bayesian%20Regression%20and%20Bitcoin%20.pdf
[2]: http://api.bitcoincharts.com/v1/csv/

In this project, you will be tasked with predicting the price variations of bitcoin, a virtual cryptographic currency, based on this [paper][1]. These predictions could be used as the foundation of a bitcoin trading strategy. To make these predictions, you will have to familiarize yourself with a machine learning technique, Bayesian Regression, and implement this technique in Python.

## Project Setup
The Python packages that you will need for this project are **numpy**, **pandas**, **sklearn**, and **statsmodels**. To install these, simply use the pip installer `sudo pip install X` or, if you are using Anaconda, `conda install X`, where X is the package name.

## Datasets
We have provided the datasets you are to use in the data folder. For your convenience, we have already done some cleaning of the data. The original raw data can be found [here][2]. The datasets from this site have three attributes: (1) time in epoch, (2) price in USD per bitcoin, and (3) bitcoin amount in a transaction (buy/sell). However, only the first two attributes are relevant to this project.
To make the data to have evenly space records, we took all the records within a 20 second window and replaced it by a single record as the average of all the transaction prices in that window. Not every 20 second window had a record; therefore those missing entries were filled using the prices of the previous 20 observations and assuming a Gaussian distribution. The raw data that has been cleaned is given in the file `dataset.csv`.
Finally, as discussed in the [paper][1], the data was divided into a total of 9 different datasets. The whole dataset is partitioned into three equally sized (50 price variations in each) subsets: train1, train2, and test. The train sets are used for training a linear model, while the test set is for evaluation of the model. There are three csv files associated with each subset of data: `*_90.csv`, `*_180.csv`, and `*_360.csv`. In `*_90.csv`, for example, each line represents a vector of length 90 where the elements are 30 minute worth of bitcoin price variations (since we have 20 second intervals) and a price variation in the 91st column. Similarly, the `*_180.csv` represents 60 minutes of prices and `*_360.csv` represents 120 minutes of prices.

## Datasets
You are provided with a small dataset called `bidder_dataset.csv`. This dataset contains
information about the advertisers. There are four columns: advertiser Id, query that they bid on,
bid value for that query, and their total budget (for all the queries). The total budget is only listed
once at the beginning of each advertiser’s list.
In addition, the file queries.txt contains the sequence of arrivals of the keywords that the
advertisers will bid on. These queries will arrive online and a fresh auctioning would be made for
each keyword in this list.

## Project Requirements
Implement the Bayesian Regression model to predict the future price variation of bitcoin as described in the reference paper.

## How to run
`python bitcoin.py data/` 
