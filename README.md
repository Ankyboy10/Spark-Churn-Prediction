Distributed Computing in Spark
Project: Analysing Customer Churn with PySpark
Table of Contents
Definition
Project Overview
Problem Statement
Metrics
Analysis
Data Exploration
Data Visualisation
Methodology
Data Preprocessing
Implementation
Refinement
Conclusion
Reflection
Challenges
Files
Software Requirements
References
Acknowledgement
I. Definition

Project Overview
You might have heard of the two music streaming giants: Apple Music and Spotify. Which is better than the other? Well, that depends on multiple factors, like the UI/UX of their app, the frequency of new content, user-curated playlists and subscribers count. The factor which we are studying is called the churn rate. Churn rate has a direct impact on the subscribers' count and also the long term growth of the business.

So what is this churn rate anyway?

For a business, the churn rate is a measure of the number of customers leaving the service or downgrading their subscription plan within a given period of time.


Problem Statement
Imagine you are working on the data team for a popular digital music service similar to Spotify or Pandora. Millions of users stream their favourite songs to your service every day either using the free tier that plays advertisements between the songs or using the premium subscription model where they stream music at free but pay a monthly flat rate. Users can upgrade, downgrade or cancel their service at any time so it is crucial to make sure your users love the service.

In this project, our aim is to identify the customer churn for Sparkify (a Spotify-like fictional music streaming service). This does not include the variety (like the genre, curated playlists, top regional charts) of music that the service provides. It mainly explores user behaviour and how we can identify the possibility that a user will churn. Such customers are those who decide to downgrade their service, i.e. going from paid subscription to free, or entirely leaving the service.

Our target variable is isChurn. It cannot be interpreted directly from the JSON file, but we will use feature engineering to create it. isChurn column is 1 for users who visited the Cancellation Confirmation page and 0 otherwise.


Metrics
Out of 225 unique users, only 52 churned (23.5%). So, accuracy will not be a good metric to handle this imbalance. We will instead use F1-Score to evaluate our model.

F1-Score is the harmonic mean of precision and recall.

Precision = True Positive / (True Positive + False Positive)

Recall = True Positive / (True Positive + False Negative)


II. Analysis

Data Exploration
Name of the input data file is mini_sparkify_event_data.json in data directory. The shape of our feature space is 286500 rows and 18 columns. data/metadata.xlsx contains information about the features.

A preview of data:

