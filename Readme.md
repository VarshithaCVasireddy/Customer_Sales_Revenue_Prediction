# **Customer Sales Revenue Prediction**
## Author: Varshitha Choudary Vasireddy
## Description of the project:
In many businesses, identifying which customers will make a purchase (and when) and how much will they spend, is a critical exercise. This is true for both brick-and-mortar outlets and online stores. The data provided in this challenge is website traffic data acquired from an online retailer.

## **The challenge: Predict total sales**
The data provides information on customer's website site visit behavior. Customers may visit the store multiple times, on multiple days, with or without making a purchase. Your goal is to predict how much sales revenue can be expected from each customer. The variable 𝑟𝑒𝑣𝑒𝑛𝑢𝑒 lists the amount of money that a customer spends on a given visit. Your goal is to predict how much money a customer will spend, in total, across all visits to the site, during the allotted one-year time frame (August 2016 to August 2017).

## **Prediction target**
More specifically, you will need to predict a transformation of the aggregrate customer-level sales value based on the natural log. That is, if a customer has multiple revenue transactions, then you should compute the sum of all the revenue generated across all of the transactions, i.e.,:
$\\ 𝑐𝑢𝑠𝑡𝑅𝑒𝑣𝑒𝑛𝑢𝑒_𝑖  =  \Sigma_{j=1}^{k_i} revenue_{ij} \quad $  $\forall i \in customers \\$
where $k_i$ denotes the number of revenue transactions for customer i
And then transform this variable as follows:
$\\ target𝑅𝑒𝑣𝑒𝑛𝑢𝑒_𝑖  =  ln(custRevenue_i + 1) \quad $  $\forall i \in customers \\$

## **Approach Followed**
- To aggregate features of customers across their online visits, mean and median were used for numerical features.
- Factor collapsing and mode were used for categorical features for data preprocessing.
- Response variable revenue was added up by each customer ID across all their visits and log transformation is applied.
- Model stacking is used to predict customer sales revenue.
- LDA (Linear Discriminant Analysis) was used for classifying the customer if he/she bought something, and used this results into MARS (Multivariate Adaptive Regression Splines) model to predict the logarithmic revenue that customer might spend.
