# Sentiment-Analysis-about-Trump-VS-Biden-on-US-Presidential-Election-2020-in-Twitter
Sentiment analysis from Twitter users on Trump VS Biden presidential election in 2020.

## Introduction
This project is done to complete the final exam of my machine learning course. Social media such as Twitter has become a place that is often used by people to express themselves in everyday life, including political affairs. Social media can be the right place for politicians to capture aspirations, campaigns, and lead opinions. This project aims to identify Twitter users' opinions on each presidential candidate, Trump and Biden, on the Twitter platform. I also want to see how much support through the positive sentiment of one candidate is in line with the candidate's victory in the 2020 United States Election.
I utilized a US Election 2020 Tweets dataset (https://www.kaggle.com/datasets/manchunhui/us-election-2020-tweets) from Kaggle. Tweets collected using the Twitter API with the timeframe started from 15th October 2020 until 8th November 2020. In total, the dataset contains roughly 1.7 million rows of data. The data was analyzed using LSTM Model to build the predictor. 

## Data Pre-processing
I began by combining two tables that contained tweets related to Trump and Biden into a single table. Next, I focused on cleaning the data, which involved various steps such as case folding the tweets, removing non-ASCII characters, mentions, hashtags, links, and URLs. Additionally, I removed any numbers that were mentioned in the tweets. To further clean the data, I created two functions that removed both whitespace and punctuation. Finally, I extended contraction words such as "i'd like" to "I would like" in order to ensure that the model could accurately understand the meaning of the text. By taking these steps, I was able to prepare the data for analysis and modeling.

## Exploratory Data Analysis
![image](https://user-images.githubusercontent.com/82467138/232244693-2d483039-4891-44c9-b53c-28faabd63f88.png)
![image](https://user-images.githubusercontent.com/82467138/232245394-18ec7b38-dc47-44a2-a7a4-3d79e7ee9725.png)
During the exploratory data analysis phase, I found that Trump had more tweets (971k) talking about him compared to Biden, who had 775k tweets. However, despite the difference in the number of tweets, Biden-related tweets had more likes than those related to Trump. 

![image](https://user-images.githubusercontent.com/82467138/232245498-8ac55755-fe72-4f76-b194-785d911e91f2.png)
A vast majority of the tweets were created by users from the United States with 394k number of tweets, followed by the United Kingdom (58k), India (40k), and Germany (35k).



## Result
