# SMS Spam Classification with NLP

This repository contains a Natural Language Processing (NLP) project for classifying SMS messages as spam or ham (not spam). The project includes data preprocessing, exploratory data analysis (EDA), feature engineering, model building, and evaluation. It leverages NLP techniques to process and analyze SMS text messages.

## Data

The dataset used in this project contains 5572 SMS messages categorized as spam or ham. It is loaded into a Pandas DataFrame for analysis.

## Exploratory Data Analysis (EDA)

- The dataset contains 5572 SMS messages with two columns: 'label' (spam or ham) and 'message' (text content).
- The dataset has no missing values.
- The messages have varying word counts, with spam messages typically containing more words.
- Several new features are created, such as 'word_count,' 'contains_currency_symbol,' and 'contains_number.'

## Data Preprocessing

- Text messages are cleaned by removing special characters and converting text to lowercase.
- Tokenization is applied to the text, followed by the removal of stop words and lemmatization.
- The resulting clean text is used to create a Bag of Words model using TF-IDF vectorization.

## Model Building and Evaluation

Three classification models are used in this project:

1. Multinomial Naive Bayes
2. Decision Tree
3. Random Forest

Model performance is evaluated using F1-Score, with the Random Forest model achieving the highest F1-Score of 0.994. Additionally, a Voting Classifier combining Decision Tree and Multinomial Naive Bayes is applied.

## Making Predictions

A function is provided to make predictions on new SMS messages. It takes a text message as input and predicts whether it is spam or ham based on the trained Random Forest model.

## Usage

To predict whether a text message is spam or ham, you can use the provided `predict_spam()` function in Python. Provide your text message as input, and it will return the prediction.

```python
predicted_label = predict_spam("Your text message here")
if predicted_label:
    print("This is a SPAM message.")
else:
    print("This is a HAM (normal) message.")
