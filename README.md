# Starbucks-Capstone-Project

## Introduction
Data Science is driving today’s Business’s strategic planning. Advent of Artificial Intelligence and Data Science is being widely used by multi-national companies to get insights about business intelligence. In this article we will use data provided by Starbucks to analyze how customers have behaved over the years to different offers and other such details.

## Project Overview
Provided sample data set contains simulated data that mimics customer behavior on the Starbucks rewards mobile app. Once every few days, Starbucks sends out an offer to users of the mobile app. An offer can be merely an advertisement for a drink or an actual offer such as a discount or BOGO (buy one get one free). Some users might not receive any offer during certain weeks. Not all users receive the same offer, and that is the challenge to solve with this data set. Our task is to combine transaction, demographic and offer data to determine which demographic groups respond best to which offer type. Every offer has a validity period before the offer expires. As an example, a BOGO offer might be valid for only 5 days. We’ll see in the data set that informational offers have a validity period even though these ads are merely providing information about a product; for example, if an informational offer has 7 days of validity, you can assume the customer is feeling the influence of the offer for 7 days after receiving the advertisement. We are also given transactional data showing user purchases made on the app including the timestamp of purchase and the amount of money spent on a purchase. This transactional data also has a record for each offer that a user receives as well as a record for when a user actually views the offer. There are also records for when a user completes an offer.

## Dataset Overview
The data is contained in three files:
- portfolio.json — containing offer ids and meta data about each offer (duration, type, etc.)
- profile.json — demographic data for each customer
- transcript.json — records for transactions, offers received, offers viewed, and offers completed

## Approach
We adopted following steps to get our insights.
- Importing required libraries and reading json files.
- Exploring all three files using .head() and .describe() methods.
- Data Cleaning
- Exploring Cleaned Data by .head() and .describe() methods
- Transforming Data by
- Plotting Data

## Results
We got following results from this data
- We have seen that most customers of Starbucks are aged between 50–70 years.
- Most members have got membership 3 years ago.
- Most members have their income between 50,000–70,000 dollars
- We have witnessed huge increase in customers in 2017 but in 2018 the number of customers has fallen.
- There was an increased activity on events (i.e. offer viewed, offer received, offer completed) in 2017 but this activity has fallen considerably in 2018.
- Almost all people that receive an offer of difficulty 7, they view them and most of viewers complete their offers.
- More people complete offer of difficulty level 20 than its viewers.
- All offers of other difficulty have seen gradual decline in offer received, viewed and completed graph.

## Conclusion
We can draw following conclusions from above results.
1. Most of our customers are of old age and have respectable income. It means that we need to increase our young customers which are more attracted by our products.
2. 2017 has seen huge progress but we couldn’t keep up this progress in 2018. This means that we should improve our offers campaign and increase customer engagement.
3. Offers of difficulty 7 are more likely to attract people and hence these types of offers should be offered more.