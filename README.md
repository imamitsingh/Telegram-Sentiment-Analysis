# Telegram Sentiment Analysis

### Objective
Perform sentiment analysis on telegram chat data.

### Data Collection
1. Exported chat messages from the official telegram group of Crypto.com (https://t.me/CryptoComOfficial) from May 1, 2021 to May 15, 2021.
2. The chat message data is in JSON format.
3. result.json contains the chat data. File size is 11.3 MB.

### Data Preprocessing 
1. Loading data into a dataframe.
2. Only 2 features are relevant here to solve our problem in hand. Hence, filter Date and Text features from the dataframe.
3. Remove non-english messages from the text data.
4. Only keeping message that contain either "SHIB" or "DOGE".
4. Performing some text preprocessing steps on the text data:
	1. Remove any punctuations or limited set of special characters like , or . or # etc.
	2. Convert the words to lowercase.
	3. Remove Stopwords.
	4. Decontraction (won't -> will not, can't to cannot).

### Sentiment Analysis
1. Compute sentiment of each text message using Flair library.
2. Flair library provides a sentiment score and sentiment value corresponding to each text message.
For instance, for the following sentence 'The food was great!'. Flair library outputs [POSITIVE (0.9961)].

### Sentiment Analysis Approach

1. Flair is a pre-trained embedding-based model. Words with vector representations most similar to another word are often used in the same context. This allows us, to, therefore, determine the sentiment of any given vector, and therefore, any given sentence. 

2. Flair uses a pre-trained NLP model instead of a rule-based model to predict the sentiment (positive, negative) of a given sentence.

3. Flair tends to be much slower than its rule-based counterparts like NLTK(VADER) and TextBlob.

### Visualization
1. Plot #1: Number of messages per day
2. Plot #2: Average sentiment per day




