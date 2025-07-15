SMS Spam Detection
The file we are going to use contains a collection of more than 5 thousand SMS phone messages. Using labeled ham and spam examples, we'll train a machine learning model to learn to discriminate between ham/spam automatically. Then, with a trained model, we'll be able to classify arbitrary unlabeled messages as ham or spam.

Here I am going to develop an SMS spam detector using SciKit Learn's. However before feeding data to Machine Learning NB algorithim, we need to process each SMS with the help of Natural Language libraries.
Summary of building the model
Let me give you a brief idea that I am going to follow in this notebook to create the model:

First try to understand the data and its distribution with basic EDA with the help of Pandas and Matplotlib libraries. Also, check for any outliers by analysing the distribution graphs.

Now with the help of NLP library "NLTK", first remove the punctuation and special symbols from all the SMS and then lower case them. You can even tokenize each SMS into sentences and words after removing punctuation & special symbols. Here I am just splitting each SMS into words with white spaces. However, tokenization and parsing may be the best idea to split the texts. Please note that converting all the data to lower case helps in the process of preprocessing and in later stages in the NLP application.

Then remove the Stopswords from all the SMS.

After processing each SMS, we will create the WordCloud for Spam and Ham messages for the visual representation of widely used words in both Spam and Ham messages.

Now we can normalize the text by NLTK lemmatization or stemming or distinguishing by part of speech (POC). However, sometimes these methods don't work well especially for text-messages due to the way a lot of people tend to use abbreviations or shorthand in SMS. E.g. "IDK" for "I don't know" or "wut" for "what". So we will not process the text by these methods.

For now, we will have the messages as lists of tokens and now we need to convert each of these messages into a vector so that SciKit Learn's algorithm models can work with.
Natural Language Processing (NLP)
Here the messages are in the human-readable language which computer can't understand, so we have to use the NLP to make it possible for computers to read human (natural) language SMS and determine which parts are important.

So, Natural language processing (NLP) is a branch of artificial intelligence that helps computers understand, interpret and manipulate human language.

NLP makes it possible for computers to read the text, hear speech, interpret it, measure sentiment and determine which parts are important.
Load the Data
Lets import the Python libraries first and then the file through pandas to get a list of all the lines of text messages:
