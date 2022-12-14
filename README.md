# Sentiment Analysis on Amazon Kindle Reviews
A Machine Learning Project focusing on the products reviews from Amazon Kindle Store category.

## Table of Contents

* [Background](#background)
* [Motivations](#motivations)
* [Project Problems](#project-problems)
* [Data Collection](#data-collection)
* [Data Preprocessing](#data-preprocessing)
* [Data Modeling](#data-modeling)
* [Data Visualization](#data-visualization)
* [Results](#results)
* [Challenges and Future Work](#challenges-and-futurework)
* [Conclusion](#conclusion)
* [References](#references)

<hr>

## Background
Amazon Kindle is a type of e-readers designed by Amazon that enables users to browse, buy, download, and read e-books, newspapers, magazines, and other digital media via wireless networking to the Kindle Store.
<hr>

## Motivations
With more people publishing data onto the internet in the form of texts, it becomes increasingly important to be able to quantify or visualize their opinions as they are often the earliest indicator of new trends. It is important to keep track of what your customer is saying about your products, in this case the Amazon Kindle products, to evaluate the emotions behind the texts and to identify any negative review before it impacts on the sales, for example. Also, to identify different audiences and how to target each of them.
<hr>

## Project Problems
<li> For this project, our team in trying to solve the problem of user review using sentiment analysis and topic modeling by using algorithms to discover patterns patterns between reviews and discerning common themes among them.
<li> Efficiently parsing and interpreting text has been a persistent obstacle for organizations. Particularly as consumers gain more opportunities to publish their opinions on the internet. Identifying the details within a review requires some level of NLP.
<li> Modeling and visualizing the attributes of the review data allows organizations to quickly gain insight into how consumers view their products.
  
<hr>

## Data Collection
The dataset used for this project is from Kaggle Website.
<li> Reviews from May 1996 - July 2014
<li> Each reviewer has at least 5 reviews and each product has at least 5 reviews in this dataset
<li> Contains a total of 98261910 entries with 10 different columns
  
<table style="width:100%">
  <tr>
    <th>Column Name</th>
    <th>Description</th>
    <th>Example</th>
  </tr>
  <tr>
    <td>asin</td>
    <td>ID of the product</td>
    <td>B000FA64PK</td>
  </tr>
  <tr>
     <td>helpful</td>
     <td>Helpfulness rating of the review</td>
     <td>2/3</td>
  </tr>
  <tr>
     <td>overall</td>
     <td>Rating of the product</td>
     <td>5</td>
  </tr>
  <tr>
     <td>reviewText</td>
     <td>Text of the review</td>
     <td>Text heading</td>
   </tr>
  <tr>
     <td>reviewTime</td>
     <td>Time of the review</td>
     <td>05,05,2014 (raw)</td>
   </tr>
  <tr>
     <td>reviewerID</td>
     <td>ID of the reviewer</td>
     <td>A3SPTOKDG7WBLN</td>
   </tr>
  <tr>
     <td>reviewerName</td>
     <td>Name of the reviewer</td>
     <td>Text entry</td>
   </tr>
  <tr>
     <td>summary</td>
     <td>Summary of the review</td>
     <td>Text description</td>
   </tr>
  <tr>
     <td>unixReviewTime</td>
     <td>unix timestamp</td>
     <td>Time</td>
  </tr>   
<table>
  
<hr>

## Data Preprocessing
<li> Converted reviewTime column type to date
<li> Removed punctuation
<li> Removed stopwords 
<li> Lowercase the text
<li> Text Tokenization
<li> Apply Lemmatization
<li> Balance Data (number of negative reviews equal to number of positive reviews)
<hr>

## Data Modeling
### Bernoulli Naive Bayes
  <li> This algorithm works well and faster to predict the class of the dataset
    
Unbalanced Data:
<li> Accuracy was 88%
<li> Precision of 62% with the negative sentiments and 92% with the positive sentiments 
<li> ROC, the area under the curve, is 75%, and a higher area means the model is better at classifying

Balanced Data:
<li> Accuracy was 86%
<li> Precision of 86% with the negative sentiments and 85% with the positive sentiments 
<li> ROC, the area under the curve, is 86%, and a higher area means the model is better at classifying
  
### Support Vector Machine (SVC)
  <li> Predicts a binary outcome based on a set of independent variables
    
Unbalanced Data:
<li> Accuracy was 92%
<li> Precision of 80% with the negative sentiments and 94% with the positive sentiments 
<li> ROC, the area under the curve, is 80%
  
Balanced Data:
<li> Accuracy was 85%
<li> Precision of 86% with the negative sentiments and 85% with the positive sentiments 
<li> ROC, the area under the curve, is 85%
  
### Logistic Regression
  <li> An algorithm used for both classification and regression analysis
    
Unbalanced Data:
<li> Accuracy was 92%
<li> Precision of 83% with the negative sentiments and 93% with the positive sentiments 
<li> ROC, the area under the curve, is 79%
  
Balanced Data:
<li> Accuracy was 86%
<li> Precision of 86% with the negative sentiments and 86% with the positive sentiments 
<li> ROC, the area under the curve, is 86%

## Data Visualization
<h4> Amazon Reviews <h4>
  <img src="Visualizations/Amazon Review Overtime.png" style="width:500px;height:300px;">
 
  
  <img src="Visualizations/Distribution of Reviews per Score.png" style="width:500px;height:300px;">
<hr>
<h4> Word Cloud and Distribution of Reviews <h4>
 <img src ="Visualizations/Wordcloud of Most Frequent Terms.jpeg" style="width:500px;height:300px;">
  
<img src ="Visualizations/Distribution of Reviews.png" style="width:500px;height:300px;">
<hr>
<h4> Sentiment of Consumer Reviews in 2012 and 2013 <h4> 
  <img src ="Visualizations/Consumer Reviews 2012.jpg" style="width:500px;height:300px;">
  

  <img src ="Visualizations/Consumer Reviews 2013.jpg" style="width:500px;height:300px;">
<hr>

## Conclusion
Overall, the three classification models perform well, but the SVM Linear SVC model had the best performance for the sentiment analysis of the Amazon Kindle Store review dataset. SVM and Logistic Regression had the best accuracy, but F1 score would be a better accuracy measure since it takes recall and precision into its calculation and ideally a good classifier has a good recall and precision measure. So, the F1 score for classifying negatives was highest for SVM, and for classifying positives SVM and Logistic Regression both had the best. Regarding the area under the curve (ROC), SVM model also had the best measure. 
<hr>
  
## Experiments
<li> Topic Modeling and LDA
<li> Sentiment Analysis on balanced data where the total number of positive reviews is the same as the total number of negative reviews  
  
<hr>
  
## Challenges and Future Work
From our limited experience with NLP and data preprocessing in Python, something we could do in the future is to improve our data to have a balance between the amount of positive and negative reviews. Two other topics that could be added to our analysis would be topic modeling to find topics with similar terms, and fake reviews to train the model to detect text might be fake since we have too many positive reviews.
  
<hr>

## Tools 
<li> Jupyter Notebook
<li> R
<li> Tableau

<br><br>

This project was developed with the collaboration of <a href="https://github.com/lvieirao">Leti Vieira Odorici</a> and
<a href="https://github.com/SamL153">Samuel Louissaint</a>.
