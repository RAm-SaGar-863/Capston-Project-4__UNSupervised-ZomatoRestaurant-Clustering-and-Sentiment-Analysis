# Capston-Project-4__UNSupervised-ZomatoRestaurant-Clustering-and-Sentiment-Analysis
UNSupervised Machine Learning Project

![cp4 final project image](https://github.com/RAm-SaGar-863/Capston-Project-4__UNSupervised-ZomatoRestaurant-Clustering-and-Sentiment-Analysis/assets/128234583/363dd45e-942e-40b5-9663-466605fea0b9)


## Abstract
India is quite famous for its diverse multi cuisine available in a large number of restaurants and hotel resorts, which is reminiscent of unity in diversity. Zomato is an Indian restaurant aggregator and food delivery start-up which provides information, menus and user-reviews of restaurants, and also has food delivery options from partner restaurants in select cities. The Project focuses on Customers and Company, you have to analyze the sentiments of the reviews given by the customer in the data and made some useful conclusion in the form of Visualizations. Also, cluster the zomato restaurants into different segments. This could help in clustering the restaurants into segments.

## Introduction
Online food-delivery platforms are expanding choice and convenience, allowing customers to order from a wide array of restaurants with a single tap of their mobile phone. The online food delivery market is no longer the underdog but has evolved into a champion. Having a food ordering marketplace platform was considered a state-of-the-art innovation in the early 2000s but today the segment has expanded to different demographics across the globe. Thanks to the increasing number of online users and vendors, the delivery providers have a sustainable business model. These businesses have immense opportunities to expand their services to a new geographical area and cater to new demographics.
## Problem Statement
The Project focuses on Customers and Company, you have to analyze the sentiments of the reviews given by the customer in the data and make some useful conclusions in the form of Visualizations. Also, cluster the zomato restaurants into different segments. The data is visualized as it becomes easy to analyze data at instant. The Analysis also solve some of the business cases that can directly help the customers finding the best restaurant in their locality and for the company to grow up and work on the fields they are currently lagging in.
This could help in clustering the restaurants into segments. Also, the data has valuable information around cuisine and costing which can be used in cost vs. benefit analysis

## Data Summary

### Attribute Information

**Zomato Restaurant names and Metadata**

Name : Name of Restaurants

Links : URL Links of Restaurants

Cost : Per person estimated Cost of dining

Collection : Tagging of Restaurants w.r.t. Zomato categories

Cuisines : Cuisines served by Restaurants

Timings : Restaurant Timings


**Zomato Restaurant reviews**

Restaurant : Name of the Restaurant

Reviewer : Name of the Reviewer

Review : Review Text

Rating : Rating Provided by Reviewer

MetaData : Reviewer Metadata - No. of Reviews and followers

Time: Date and Time of Review

Pictures : No. of pictures posted with review

## Data Cleaning and Pre-Processing

The raw data received in the data set might not be directly suitable for analysis due to presence of unwanted data like, duplicate values, null values, outliers etc. We need to handle them first before we proceed with further analysis.

**Removing Duplicates**: The “Zomato Restaurant names and Metadata” dataset provided for this analysis consists of almost 105 records. None of them are duplicated and all of them are unique. Similarly, the “Zomato Restaurant Reviews” dataset provided consists of 10000 records and none of the are duplicated and all are unique. It is better to check for duplicate values before modeling.

**Handling null/missing values**: It is also possible that the given data set can contain missing information for some or all features in some records, we need to either remove them or find alternatives to fill up the null values. In the “Zomato Restaurant names and metadata” dataset, more than half of the collections column are null values. So, we are not using that column for the analysis. Also, in “Zomato Restaurant Reviews” dataset, there are few null values in few columns. As the number of null values are low, we have dropped them. After splitting the meta data into two different columns namely, “Reviews” and “Followers” we found some more null values. As now the number is more, we have replaced null values with 0.

**Feature Handling**: We can manipulate some of the features according to our requirements to draw required information from the data. For example, we have divided the “Time” column from “Zomato Restaurant Reviews” dataset to extract three more new features called, “year”, “month” and “hour” columns. Also, we have split the “MetaData” column into “Reviews” and “Followers”

##  EDA Summary:

• College Hyatt Gachibowli is most expensive restaurant with cost more than 2500. rupees

• Mohammedia Shawarma is the cheapest restaurant with average cost of 150 rupees.

• Indian cuisine is the most served cuisine in the restaurants followed by Chinese and South Indian

• Most of the rating given by the customers are above 3

• Maximum review and orders are coming between the time (12pm - 3pm) and (8pm - 11pm)

## Text Preprocessing 

Data Preprocessing is the most essential step for any Machine Learning model. How well the raw data has been cleaned and preprocessed plays a major role in the performance of the model. Likewise in the case of NLP, the very first step is Text Processing.

The various preprocessing steps that are involved are:

• Lower Casing

• Tokenization

• Punctuation Mark Removal

• Stop Word Removal

• Stemming

• Lemmatization


● **Lower Casing**: Converting a word to lowercase (NLP -> nlp). Words like Book and book mean the same but when not converted to the lower case those two are represented as two different words in the vector space model (resulting in more dimensions).

● **Tokenization**: It is the process of tokenizing or splitting a string, text into a list of tokens. One can think of a token as parts like a word is a token in a sentence, and a sentence is a token in a paragraph.

● **Punctuation Mark Removal**: The punctuation removal process will help to treat each text equally. For example, the word data and data! are treated equally after the process of removal of punctuations.

● **Stop Word Removal**:  The idea is simply removing the words that occur commonly across all the documents in the corpus. Typically, articles and pronouns are generally classified as stop words.

● **Stemming**: This is the process of reducing a word to its word stem that affixes to suffixes and prefixes.

● **Lemmatization**: This is the process of the grouping together of different forms of the same word and converting words into base or root form.

## Sentiment Analysis

Sentiment analysis (or opinion mining) is a natural language processing (NLP) technique used to determine whether data is positive, negative or neutral. Sentiment analysis is often performed on textual data to help businesses monitor brand and product sentiment in customer feedback, and understand customer needs. In this project we will try to see the sentiment of the review given by the customers.

**Subjectivity**: Subjectivity quantifies the amount of personal opinion and factual information contained in the text. Subjectivity lies between [0,1]. The higher subjectivity means that the text contains personal opinion rather than factual information. 

**Polarity**: Polarity score tells us how positive or negative the text is, it ranges between (- 1 to +1) if the score is negative it means sentiment is negative, if score is positive, it means sentiment is positive. If the Polarity score is 0, it means the text is neither positive nor negative but neutral.

**Summary**

Out of 9,954 reviews:

•	7,478 reviews are Positive (i.e., 75% of total review are Positive)

•	1,887 reviews are Negative (i.e., 19% of total reviews are Negative)

•	589 reviews are Neutral (i.e., 6% total reviews are Neutral)




## Applying ML Models for Sentiment Prediction

**Models used**:

• Random Forest Classifier 

• XGBoost Classifier

• SVM

**Summary**

• Random Forest has test accuracy of 0.813 and train accuracy of 0.811

• XGBoost has test accuracy of 0.995 and train accuracy of 0.939

• SVM has test accuracy of 0.997 and train accuracy of 0.929

## Clustering

**K- Means Clustering**:

•	The optimal number of clusters were built after visualizing the elbow curve i.e., 5

•	Cluster were segmented in terms of the cost

Summary
	
    Top 3 cuisine in 

        •	In Cluster 0 North Indian, Chinese, and Fast food

        •	In cluster 1 North Indian, Continental, and Asian

        •	In Cluster 2 North Indian, Continental and Biryani

        •	In Cluster 3 Asian, Italian, and Continental
        
        •	In Cluster 4 North Indian, Chinese, and Italian

## Conclusions 

• The most popular cuisines are the cuisines which most of the restaurants are willing to provide. 

• The most popular cuisines in Hyderabad are North Indian, Chinese, Continental, and Hyderabadi.

• The cheapest is the food joint called Mohammedia Shawarma and the costliest restaurant is Collage – Hyatt Hyderabad Gachibowli. 

• Sentiment Analysis was done on the reviews and a model was trained to identify negative and positive sentiments. 

• SVM and XGB both performed well, and we can choose any one of them. 

• SVM and XGB are having 0.88 and 0.89 of testing accuracy, respectively. 

• We got best cluster as 5 in K-Means and Principal Component Analysis (PCA).
