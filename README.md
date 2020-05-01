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

## Problem Statement
In this project the problem which we will address is to check effectiveness of offers launched by Starbucks and analyze Customer Profiles to recommend offers for a customer.

## Method to solve problem
We will clean, transform and visualize data to understand how customers have reacted to our offers and which category of customers we need to focus upon. To recommend offers for a customer we will create user matrix and the use FunkSVD to make recommendations.

## Approach
We adopted following steps to get our insights.
1. Importing required libraries and reading json files.
2. Exploring all three files using .head() and .describe() methods.
3. Data Cleaning
- Clean_portfolio() : This function cleans Portfolio Dataframe by
- clean_profile(): This function cleans Profile Dataframe by
- clean_transcript(): This Function cleans Transcript Dataframe by
4. Exploring Cleaned Data by .head() and .describe() methods
5. Transforming Data by
6. Plotting Data
7. Creating a User Matrix
8. Making Train & Test Matrix
9. Evaluating our model by tuning latent_feature parameter.
10. Getting offers for a specific customer
11. Getting top selling offers

## Data Modeling
Our main goal for modeling data is to search for the record pattern: offer received, offer viewed, offer completed. We can achieve our goal by looping through the offers and then the users, getting all the records of that particular user and that particular offer. We loop through all the records and if there is any pattern matched, we add one to the specific location in the user-item matrix. Otherwise, we put zero to that place. If the user never received that offer, we leave it as NaN. After a long computing time, we get a spare matrix with some NaN and many zero in it. We can finally construct the information we need to further analyze.


## Algorithm
We will use FunkSVD Algorith in our model to split the matrix into the user matrix, latent feature matrix and offer matrix. We are using FunkSVD because there are missing values inside the matrix and normal SVD just doesn’t work.

## Metrics
We will evaluate our model by calculating mean square error. We will tune our parameters by using values of latent feature as 15, 20and 30 to choose which one is best. We used 150 iterations for each model and used learning rate at 0.005. For 15 latent value, we have MSE = 0.02422, for 20 latent feature, we have MSE = 0.021273, for 30 latent feature, we have MSE = 0.014342 achieving lowest MSE.

## Evaluation
We tuned our model by changing value of latent_features between 15,20 & 30. After running our models, we got following observations.
- latent_feature = 15 gives worst MSE = 0.314692 and best MSE = 0.02422.
- latent_feature =20 gives worst MSE = 0.329035 and best MSE = 0.021273.
- latent_feature =30 gives worst MSE = 0.377391 and best MSE =0.014342.

## Improvements
We used FunckSVD algorithm but this was not helpful in Cold Start Scenario ie for making recommendations for new users. Moreover, each user recieves multiple offers hence splitting between training and testing can be improved.

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