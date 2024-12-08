# Sentiment Analysis of Financial News Headlines and Their Impact on Stock Price Prediction

This repository houses the codebase and resources for the project **"Sentiment Analysis of Financial News Headlines and Their Impact on Stock Price Prediction"**. This endeavor combines state-of-the-art natural language processing (NLP) techniques with machine learning to explore the intricate relationship between news sentiment and stock price movements.

## Project Overview

The project unfolds in two key phases:

1. **Sentiment Analysis of Financial News Headlines**  
   Financial news headlines from 2007 to 2016 are analyzed using advanced NLP tools, custom entity recognition, and a fine-tuned RoBERTa model. This phase extracts sentiment scores and organizes the data for downstream analysis.

2. **Stock Price Prediction Using Sentiment Data**  
   Stock market data is integrated with sentiment scores, and advanced machine learning models like LSTM and GRU are employed to predict stock price movements. Missing data handling and sentiment imputation strategies ensure robustness.

---

## File Descriptions

### Sentiment Analysis
- **SPacy_NER_and_s&p500_company_list.py**  
  Implements custom Named Entity Recognition (NER) using SpaCy to detect and filter organizations from financial news headlines, leveraging the S&P 500 companies list.

- **merge_new.py**  
  Merges daily financial news headline files into a consolidated dataset, spanning years of data for streamlined analysis.

- **Timestamp_normalization.py**  
  Normalizes multiple timestamp formats (e.g., UTC, EDT) into UTC, aligning headline data with stock data retrieved from YFinance.

- **Roberta_train_fin_phrasebank.py**  
  Fine-tunes a RoBERTa model using the Financial PhraseBank dataset, training it to generate sentiment values relevant to financial contexts. The trained model is saved as `.pt`.

- **final_data_sentiment.py**  
  Applies the fine-tuned RoBERTa model to the news headlines dataset, assigning sentiment values (0: Negative, 1: Neutral, 2: Positive).

- **Sentiment_normalization.py**  
  Converts sentiment scores from categorical values ([0, 1, 2]) into a normalized scalar range ([0, 1]) suitable for prediction models.

- **Extracting_each_org_average_sentiment.py**  
  Aggregates multiple daily sentiment scores for each organization by calculating an average, ensuring a single sentiment value per day per organization.

---

### Stock Price Prediction
- **LSTM&GRU_1.py**  
  Integrates stock price data with sentiment data while excluding records with missing sentiment values. This results in a smaller but consistent dataset.

- **LSTM&GRU_2_with_neutral_sentiment.py**  
  Addresses missing sentiment values by imputing neutral sentiment, resulting in a larger, continuous dataset for stock price prediction.

---

## Getting Started

### Prerequisites
To run the scripts, ensure you have the following dependencies installed:
- Python 3.8+
- SpaCy
- PyTorch
- Hugging Face Transformers
- pandas
- numpy
- matplotlib
- yfinance


