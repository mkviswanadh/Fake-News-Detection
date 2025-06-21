# Fake-News-Detection
With the massive volume of news articles published daily, it’s becoming harder to distinguish between credible and misleading information. This creates a need for systems that can automatically classify news articles as true or fake, helping to reduce misinformation and protect public trust.

<img src="fake-news-detector.jpg" style="display:block; margin-left:auto; margin-right:auto;"/>

<h2> Pipelines that needs to be performed </h2>

You need to perform the following tasks to complete the assignment:

<ol type="1">

  <li> Data Preparation
  <li> Text Preprocessing
  <li> Train Validation Split
  <li> EDA on Training Data
  <li> EDA on Validation Data [Optional]
  <li> Feature Extraction
  <li> Model Training and Evaluation

</ol>

### Input data observations:

#### Input Stats 

**True News:**
  . 21417 rows
  . 3 columns

**Fake News:**
  . 23423 rows
  . 3 columns

#### Derived columns
1) **news_label** : 1 for true news and 0 for fake news
2) **news_text** : title + " "+ text
3) **cleaned_text** : cleaned the text & remove all the unnecessary elements
4) **lemmatized_text** : derived text with POS tagging and lemmatization,by filtering stopwords and keeping only NN and NNS tags


### Train Test Split:
1) **70%** of input data used for training
2) **30%** of input data used for validation
3) **stratify** option to used to handle class imbalance if any
4) **random_state** option used for maintaining the reproducibility and consistency across experiments

### Exploratory Data Analysis:

1) word cloud used to determine top 40 words by frequency among true news & fake news in the training data after processing the text

   a) The word **"trump"** in true news has high frequency - **19495**

   b) The word **"trump"** in fake news has high frequency - **34741**

2) word cloud used to determine top 40 words by frequency among true news & fake news in the validation data after processing the text

   a) The word **"trump"** in true news has high frequency - **8144**

   b) The word **"trump"** in fake news has high frequency - **14021**

3) observation **"trump"** is common word with high frequency irrespective of whether its true news or fake news or training data or validation data

4) **Top 10 unigrams, bigrams & trigrams** in both true news & fake news based on the frequency and plotted bar graphs for training data

5) **Top 10 unigrams, bigrams & trigrams** in both true news & fake news based on the frequency and plotted bar graphs for validation data



### Feature extraction:
1) **Word2Vec** model from genism package used for feature extraction

2) Extracted the vectors for lemmatized_text using Word2Vec model

3) **LabelEncoder** used to encode target variable


### Model Training & Evaluation:

#### Logistic Regression:
1) Accuracy of the Logistic Regression Model is : **90.38%**
2) Precision of the Logistic Regression Model is : **89.53%**
3) Recall of the Logistic Regression Model is : **90.4%**
4) F1 Score of the Logistic Regression Model is : **89.96%**

#### Decision Tree Classifier
1) Accuracy of the Decision Tree Model is : **82.64%**
2) Precision of the Decision Tree Model Model is : **83.04%**
3) Recall of the Decision Tree Model Model is : **79.92%**
4) F1 Score of the Decision Tree Model Model is : **81.45%**

#### Random Forest Model
1) Accuracy of the Random Forest Model is : **90.9%**
2) Precision of the Random Forest Model Model is : **91.06%**
3) Recall of the Random Forest Model Model is : **89.73%**
4) F1 Score of the Random Forest Model Model is : **90.39%**

**Random Forest Model** given highest accuracy **90.9%** compared to other models