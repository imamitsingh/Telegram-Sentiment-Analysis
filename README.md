# Telegram Sentiment Analysis

### Objective
Perform sentiment analysis on telegram chat messages.

### Data Collection
- Exported chat messages from the official telegram group of Crypto.com (https://t.me/CryptoComOfficial) from May 1, 2021 to May 15, 2021.
- The chat message data is in JSON format.
- [result.json](https://github.com/imamitsingh/Telegram-Sentiment-Analysis/blob/main/result.json) contains the chat data. File size is 11.3 MB.

### Data Preprocessing 
- Load json data into a dataframe.
- Only 2 features are relevant here to fulfill our objective. Hence, filter Date and Text features from the dataframe.
- Perform some basic text preprocessing steps on the text data:
	- Convert the words to lowercase.
	- Decontraction of some english words (won't -> will not, can't to cannot).
- Remove non-english messages from the text data.
- Only keep message that contain either "SHIB" or "DOGE".


### Sentiment Analysis
- Compute sentiment of each text message using a pre-trained NLP model from [Flair](https://github.com/flairNLP/flair).
- The pre-trained model outputs a sentiment score and a sentiment value corresponding to each text message. For instance, for the following sentence 'The food was great!', it outputs [POSITIVE (0.9961)].

### Choice of Sentiment Analysis Approach
- Flair is a pre-trained embedding-based model. This means that each word is represented inside a vector space. Words with vector representations most similar to another word are often used in the same context. This allows us, to, therefore, determine the sentiment of any given vector, and therefore, any given sentence. 

- Flair uses a pre-trained NLP model instead of its rule-based counterparts like NLTK(Vader) and TextBlob. It predict the sentiment (positive or negative) and provides a number(sentiment score) in brackets behind the label which is a prediction confidence of a given sentence.

- Flair performs better than many rule-based models. However, it tends to be much slower.

### Visualization
- Plot #1: [Number of messages per day](https://github.com/imamitsingh/Telegram-Sentiment-Analysis/blob/main/Plot_1_Messages_per_day.png)
- Plot #2: [Average sentiment per day](https://github.com/imamitsingh/Telegram-Sentiment-Analysis/blob/main/Plot_2_Avg_sentiment_per_day.png)

### Instructions to run the code in order to reproduce the results
- Download and install [Jupyter notebook](https://jupyter.org/install).
- [Python 3.6+](https://www.python.org/downloads/) required.
- Install all the packages mentioned in the [requirements.txt](https://github.com/imamitsingh/Telegram-Sentiment-Analysis/blob/main/requirements.txt) file using the pip3 command.
```
    pip3 install "package-name"
```
- Download the [ipython notebook](https://github.com/imamitsingh/Telegram-Sentiment-Analysis/blob/main/MindsChallenge.ipynb) and run each cell to get reproduce results.


### References
- https://github.com/flairNLP/flair
- https://christineeeeee.com/posts/nlp_sentiment_tool/
- https://medium.com/analytics-vidhya/sentiment-analysis-with-nltk-textblob-and-flair-a321d1460867
- https://neptune.ai/blog/sentiment-analysis-python-textblob-vs-vader-vs-flair
- https://towardsdatascience.com/the-best-python-sentiment-analysis-package-1-huge-common-mistake-d6da9ad6cdeb




