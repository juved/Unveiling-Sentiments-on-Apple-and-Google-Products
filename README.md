# Unveiling-Sentiments-on-Apple-and-Google-Products



## Business Understanding
As Data Scientists at Apple, we are attempting to leverage sentiment of tweets, particularly tweets related to Apple and Google at a SXSW (South By Southwest) event, to enhance our social media engagement, as well as our general marketing and advertising strategies. SXSW is is an annual festival/conference event held in Austin, Texas. We aim to assess our product marketing effectiveness to inform future strategies, ensuring our approach is both data-driven and responsive to consumer trends. This analysis will help us identify areas of improvement in our products and services, as well as opportunities for innovation.

By proactively addressing these concerns, we can demonstrate our commitment to customer satisfaction and product improvement. Additionally, we will be able to spot emerging trends and topics in real-time, allowing us to engage with our audience more effectively and participate in relevant conversations

<img width="557" alt="Sentiments distributions" src="https://github.com/juved/Unveiling-Sentiments-on-Apple-and-Google-Products/assets/34844790/0f69b45d-b7ca-4851-970f-d6179e0c184e">

## Data
The data we are using was taken from data.world. It contains 9,093 tweets that mention SXSW and mention different companies and/or its products. Each row represents a tweet, and there are three columns: one dispaying the tweet text itself, one that labels the product or company the sentiment in the tweet is directed at, and one that tells us whether the tweet showed a positive emotion, negative emotion, neutral emotion, or undetermined. These emotion labels were crowdsourced.


### Preparation

NLP and Tweet-specific preprocessing
Because we are working with text, specifically tweets, we need to do some additional cleaning and preprocessing. Particularly, we will get rid of stopwords (words that will appear frequently in our text but provide no semantic value). We also need to lemmatize our words to normalize them, get rid of any punctuation, lowercase our words, and tokenize them so that our data is divided by the individual words. We will also need to vectorize our text data, converting it to numerical vectors.
<img width="554" alt="Data processing" src="https://github.com/juved/Unveiling-Sentiments-on-Apple-and-Google-Products/assets/34844790/366ea556-5bd9-4c95-862b-a345692c139e">


## Modeling & Evaluation

We will now create predictive models with our data, using the words in the tweet texts to predict sentiment. We will create predictive models with our binomial classification (positive and negative emotion) as well as with our multi-class target (positive, negative, and neutral). The binomial classification modeling was done in the [notebook](https://github.com/juved/Unveiling-Sentiments-on-Apple-and-Google-Products/blob/main/Notebooks/juvensone_working_notebook.ipynb). Before doing so, we will train_test_split our data and create pipelines for some of our models. We will focus on Multinomial Naive Bayes and Random Forest for our modeling. Once we find our best-performing model on cross-validation, we will run further analysis on its most important features.

Features Importance Analysis
After determining our best model and evaluating it on the test set, we looked at its feature importance and compared this the td-idf frequencies for each words by sentiment. This way, we can attempt to draw some conclusions and recommendations based on which words are most preditictive of sentiment in our model, and if they are associated with positive sentiment in tweets or negative sentiment in tweets.
Some of the words that stand out in terms of feature importance are Apple and Google, as Apple is more predictive of sentiment than google. Store and pop also appear in the top 15, which makes sense considering Apple opened a temporary pop-up store at SXSW. However, the feature importances do not tell which target the words are more predictive for, whether it is positive, neutral, or negative. To find out which of the words that are important features are associated with positive, neutral, or negative sentiment tweets, we will find the TD-IDF scores for each word by tweet sentiment. This will help us determine conclusions and recommendations for our marketing strategy at Apple.<img width="953" alt="top 15 Features by importance" src="https://github.com/juved/Unveiling-Sentiments-on-Apple-and-Google-Products/assets/34844790/ff9697c4-e11a-4569-9fcc-e526ff1e5238">



## Conclusions and Recommendations

Based on the the most important features in our model and their association to positive or negative tweets, we have made some conclusions and recommendations for our marketing strategy going forward.

1. Continue overall marketing strategy, as we are outperforming Google, our competitor, in terms of tweets with positive sentiment. Apple should consider continuing to have a presence with speakers and presentations, as well as with social media interaction with the event.

2. The temporary pop-up store was a success based on the overall positive sentiment on twitter. Therefore, Apple should continuing implementing the pop-up store at SXSW and similar types of events.

3. Because 'Launch' was particularly associated with positive tweets at SXSW, Apple should continue heavily marketing its new and forthcoming products by marketing and showing its launches both at events and on social media.

4. Address the negative sentiment around iPhone. Apple specifically could look at the tweets with negative sentiment directed at iPhone, and try to address the issues that people have had with the product. For example, iPhone battery seems to have been a common topic among negative tweets about the iPhone. Apple could use information like this to improve its marketing strategy for improved battery technology and performance in the future.





## Repo Structure 
```
├── Images
├── Notebooks
├── data
├── .gitignore
├── Final.ipynb
├── LICENSE
├── README.md
```
