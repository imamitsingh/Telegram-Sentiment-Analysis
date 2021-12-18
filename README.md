# Telegram Sentiment Analysis

### Objective
Perform sentiment analysis on telegram chat messages.

### Data Collection
- Exported chat messages from the official telegram group of Crypto.com (https://t.me/CryptoComOfficial) from May 1, 2021 to May 15, 2021.
- The chat message data is in JSON format.
- [result.json](https://github.com/imamitsingh/Telegram-Sentiment-Analysis/blob/main/result.json) contains the chat data. File size is 11.3 MB.

### Data Preprocessing 
- Load json data into a dataframe.
- Only 2 features are relevant here to fulfil our objective. Hence, filter Date and Text features from the dataframe.
- Perform some basic text preprocessing steps on the text data:
	- Convert the words to lowercase.
	- Decontraction of some english words (won't -> will not, can't to cannot).
- Remove non-english messages from the text data.
- Only keep message that contain either "SHIB" or "DOGE".


### Sentiment Analysis
- Compute sentiment of each text message using a pre-trained NLP model from [Flair library](https://github.com/flairNLP/flair).
- The pre-trained model outputs a sentiment score and a sentiment value corresponding to each text message. For instance, for the following sentence 'The food was great!', it outputs [POSITIVE (0.9961)].

### Choice of Sentiment Analysis Approach

- Flair is a powerful NLP library with a pre-trained embedding-based model. Words with vector representations most similar to another word are often used in the same context. This allows us, to, therefore, determine the sentiment of any given vector, and therefore, any given sentence. 

- Flair uses a pre-trained NLP model instead of a rule-based model to predict the sentiment (positive, negative) of a given sentence.

- Flair tends to be much slower than its rule-based counterparts like NLTK(VADER) and TextBlob.

### Visualization
- Plot #1: [Number of messages per day](https://github.com/imamitsingh/Telegram-Sentiment-Analysis/blob/main/Plot_1_Messages_per_day.png)
- Plot #2: [Average sentiment per day](https://github.com/imamitsingh/Telegram-Sentiment-Analysis/blob/main/Plot_2_Avg_sentiment_per_day.png)




