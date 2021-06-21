# Disaster Tweets Classification
* Created a comparison project which is able to classify tweets as disaster or non-disaster
* Dataset was taken from kaggle. 
* Link for dataset: https://www.kaggle.com/vstepanenko/disaster-tweets
* Did a comparison of Multinomial Naive Bayes, Logistic Regression, Custom LSTM model and Custom GRU model.

## Code and Resources Used 
**Python Version:** 3.7  
**Packages:** pandas, numpy, sklearn, matplotlib, seaborn, selenium, flask, json, pickle, tensorflow, keras, emoji

## Overview Of The Dataset
* The dataset has 4 columns: keyword, location, text and target
* The "text" column contains all the tweets
* The target column is a binary column ( 0 and 1), representing disaster and non-disaster tweets

## Exploratory Data Analysis
* The dataset has 11370 tweets
* The dataset is highly imbalanced. There are 9256 non-disaster tweets and 2114 disaster tweets.
* A bar-plot of the number of tweets is given below:
* ![image](https://user-images.githubusercontent.com/56645508/122762198-b0639b80-d2ba-11eb-9bd8-3340724252a2.png)
* The comparison of counts of all the key words was done. It is shown below:
* ![image](https://user-images.githubusercontent.com/56645508/122762336-d8eb9580-d2ba-11eb-9448-dbb80e14106a.png)

## Data Cleaning
In order to clean my data, I did the following steps:
* Made the text lowercase.
* Removed all the text in square brackets.
* Removed all the hyperlinks.
* Removed all the punctuations.
* Removed the words containing numbers.
* Removed Stopwords.
* Changed all the emojis to real text using the emoji library in python.
* Lemmatized the corpus using WordNetLemmatizer

## Model Building 

I took two different approaches. First was a machine learning approach and the other was a deep learning approach.

### Machine learning approach
* Firstly I vectorized my data using 2 different ways. I used countvectorizer and tf-idf vectorizer. 
* The models I used were Logistic Regression and Multinomial Naive Bayes.
* I compared the performance of both these models( after hyperparameter tuning) on the countvectorized data as well as the tf-idf vectorized data.
* The accuracies achieved by them is as follows:


| Model      | Countvectorizer- Testing Accuracy | Tf-idf vectorizer - Testing Accuracy   |
| :---        |    :----:   |          ---: |
| Logistic Regression      | 0.8773087071240105      | 0.8777484608619174   |
| Multinomial Naive Bayes   | 0.8773087071240105        | 0.8777484608619174      |

### Deep Learning approach
* In this I created a custom LSTM as well as a custom GRU model.
* I trained each model for 10 epochs.
* The training accuracies and training loss are shown below:

![image](https://user-images.githubusercontent.com/56645508/122764634-4d273880-d2bd-11eb-80b2-86910adcb8e4.png)

![image](https://user-images.githubusercontent.com/56645508/122764660-54e6dd00-d2bd-11eb-98cc-b05582e643c5.png)


