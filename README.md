# LSTM_Donors_choose.org
<p>
DonorsChoose.org receives hundreds of thousands of project proposals each year for classroom projects in need of funding. Right now, a large number of volunteers is needed to manually screen each submission before it's approved to be posted on the DonorsChoose.org website.
</p>
<p>
    Next year, DonorsChoose.org expects to receive close to 500,000 project proposals. As a result, there are three main problems they need to solve:
<ul>
<li>
    How to scale current manual processes and resources to screen 500,000 projects so that they can be posted as quickly and as efficiently as possible</li>
    <li>How to increase the consistency of project vetting across different volunteers to improve the experience for teachers</li>
    <li>How to focus volunteer time on the applications that need the most assistance</li>
    </ul>
</p>    
<p>
The goal of this project is to predict whether or not a DonorsChoose.org project proposal submitted by a teacher will be approved, using the text of project descriptions as well as additional metadata about the project, teacher, and school. DonorsChoose.org can then use this information to identify projects most likely to need further review before approval.
</p>

# Methodology:

<br>__Data acquisition__:
We acquired data from Kaggle <ul>
<li> https://www.kaggle.com/donorschoose/io</li>
</ul>

<br>__Data Cleaning and EDA__:
Checking the missing values,data imbalance and repetitive values and removing or imputing them,performing exploratory data analysis to get some initial insights of the data and for clear understanding of how to go about solving the problem.
<img src = https://github.com/yatscool007/LSTM_Donors_choose.org/blob/master/Images/newplot.png>

<br>__Feature engineering__:
We performed initial feature engineering on the data and curated features like __is digit__ in text data

<br>__Data Preprocessing and Modelling__:
for text data,removing stopwords,url tags ,lowercase and performing porter stemming and Lemmetization and we performed different data preprocessing techniques for all three models implemented (with diffrent architecture-
    <br>- __Model 1__: As we needed an embedding layer for multiple inputs,we used binary Countvectorizer to convert Categorical features into one hot coded vectors and for text data we used Keras text tokenizer for turning each text into a sequence of integers.
