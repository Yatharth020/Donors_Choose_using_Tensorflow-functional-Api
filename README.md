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
    <br>- __Model 1__: we used binary Countvectorizer to convert Categorical features into one hot coded vectors and for text data we used Keras text tokenizer for turning each text into a sequence of integers.An then used embedding layers for each of the categorical input while for text data we used pre trained glove vectors as our embedding layer which we kept 'non-trainable'
 The architecture we followed in the model was :
 <img src = https://github.com/yatscool007/LSTM_Donors_choose.org/blob/master/Images/mod1.PNG></br>
    <br>- __Model 2__:Using the same model as above but for 'input_seq_total_text_data' give only some words in the sentance not all the words and filtering the words as below. 
<p>
1. Training  the TF-IDF on the Train data <br>
2. Getting  the idf value for each word we have in the train data. <br>
3. Removing the low idf value and high idf value words from our data. Do some analysis on the Idf values and based on those values choose the low and high threshold value. Because very frequent words and very very rare words don't give much information. (you can plot a box plots and take only the idf scores within IQR range and corresponding words)<br>
4. Training the LSTM after removing the Low and High idf value words.</p>
</br>
    <br>- __Model 3__:
        . Using text column, and use the Embedding layer to get word vectors. <br>
        . Use given predefined glove vectors <br>
        . Using LSTM, get the LSTM output and Flatten that output. <br>
        . Converting all the Categorical values to onehot coded and then concatenating all these onehot coded vectors <br>
        . Numerical values and use <a href='https://keras.io/getting-started/sequential-model-guide/#sequence-classification-with-1d-             convolutions'>CNN1<br>
    
