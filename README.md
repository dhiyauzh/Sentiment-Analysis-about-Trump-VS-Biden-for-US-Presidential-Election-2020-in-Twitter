# Sentiment-Analysis-about-Trump-VS-Biden-on-US-Presidential-Election-2020-in-Twitter
Sentiment analysis from Twitter users on Trump VS Biden presidential election in 2020.

## Introduction
This project is done to complete the final exam of my machine learning course. Social media such as Twitter has become a place that is often used by people to express themselves in everyday life, including political affairs. Social media can be the right place for politicians to capture aspirations, campaigns, and lead opinions. This project aims to identify Twitter users' opinions on each presidential candidate, Trump and Biden, on the Twitter platform. I also want to see how much support through the positive sentiment of one candidate is in line with the candidate's victory in the 2020 United States Election.
I utilized a US Election 2020 Tweets dataset (https://www.kaggle.com/datasets/manchunhui/us-election-2020-tweets) from Kaggle. Tweets collected using the Twitter API with the timeframe started from 15th October 2020 until 8th November 2020. In total, the dataset contains roughly 1.7 million rows of data. The data was analyzed using LSTM Model to build the predictor. 

## Data Cleaning
I began by combining two tables that contained tweets related to Trump and Biden into a single table. Next, I focused on cleaning the data, which involved various steps such as case folding the tweets, removing non-ASCII characters, mentions, hashtags, links, and URLs. Additionally, I removed any numbers that were mentioned in the tweets. To further clean the data, I created two functions that removed both whitespace and punctuation. Finally, I extended contraction words such as "i'd like" to "I would like" in order to ensure that the model could accurately understand the meaning of the text. By taking these steps, I was able to prepare the data for analysis and modeling.

## Exploratory Data Analysis
Number of Tweets             |  Number of Likes
:-------------------------:|:-------------------------:
![image](https://user-images.githubusercontent.com/82467138/232244693-2d483039-4891-44c9-b53c-28faabd63f88.png)  |  ![image](https://user-images.githubusercontent.com/82467138/232245394-18ec7b38-dc47-44a2-a7a4-3d79e7ee9725.png)

During the exploratory data analysis phase, I found that Trump had more tweets (971k) talking about him compared to Biden, who had 775k tweets. However, despite the difference in the number of tweets, Biden-related tweets had more likes than those related to Trump. 

![image](https://user-images.githubusercontent.com/82467138/232245498-8ac55755-fe72-4f76-b194-785d911e91f2.png)

A vast majority of the tweets were created by users from the United States with 394k number of tweets, followed by the United Kingdom (58k), India (40k), and Germany (35k). From the graph below we can see the comparison of the origin countries of users that tweet about Trump and Biden. Additionaly, we can also see both candidates' popularity in the US States represented by the number of tweets of candidates.
Top 10 tweets about each candidates in various countries            |  Top 10 tweets about each candidates in the US States 
:-------------------------:|:-------------------------:
![image](https://user-images.githubusercontent.com/82467138/232245997-d02a661d-258f-4f61-9523-3856e818a889.png)  |  ![image](https://user-images.githubusercontent.com/82467138/232246027-e83b8afa-de3b-4e69-a1d6-ba014b7eb680.png)

## Model Creation
As a part of the data preprocessing step, I created three new columns in the dataset, which include the polarity score, tweet length, and word count. The polarity score was based on the criteria of negative (0), neutral (1), and positive (2). Following this, I used the PorterStemmer package to stem the data and Tokenizer from TensorFlow Keras to tokenize the data. The Tokenizer converts words into numerical data, which is then fed into the neural network. This preprocessed data is then used for model training and evaluation. 80% of the data is used as training dataset while the rest is for the test dataset. The performance of the model was evaluated using a confusion matrix, which provided insights into the accuracy of the model's predictions. The final model has an accuracy of 86,74%.

![image](https://user-images.githubusercontent.com/82467138/232247686-b9838507-f992-4629-bdaa-451b9e8db369.png)

## Discussion
Trump-related tweets sentiment           |  Biden-related tweets sentiment 
:-------------------------:|:-------------------------:
![image](https://user-images.githubusercontent.com/82467138/232248826-e3f72bcb-8d20-4483-9044-52caa5481718.png)  |  ![image](https://user-images.githubusercontent.com/82467138/232248854-97273544-eb38-47f7-870b-5516578b218a.png)

During the sentiment analysis phase of this project, it was observed that 38.8% of the tweets related to Biden were positive, while 14.6% were negative. The remaining tweets were categorized as neutral. In comparison, tweets related to Trump had a 35.7% positive sentiment and 19.6% negative sentiment, with the remainder being neutral. These results provide insights into the overall sentiment of tweets related to both candidates during the timeframe of the analysis. It is important to note that sentiment analysis can be subjective, as the criteria for positive, negative, and neutral tweets can vary based on the sentiment analysis model being used. Nonetheless, these findings can help in understanding the public's perception of political candidates on social media platforms. Here are the commonly used words generated by users regarding each candidates.

Trump-related tweets wordcloud           |  Biden-related tweets wordcloud 
:-------------------------:|:-------------------------:
![image](https://user-images.githubusercontent.com/82467138/232249230-eec939fe-b8ed-4c8b-b755-116416ff920a.png)  |  ![image](https://user-images.githubusercontent.com/82467138/232249248-a6e92201-86fe-4389-9acd-b8d1a3684316.png)
