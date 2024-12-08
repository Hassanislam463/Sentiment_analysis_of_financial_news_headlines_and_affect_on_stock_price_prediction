The files start with:
1.SPacy_NER and s&p500_company_list:
In this file spacy is used for entity recognition with custom NER and it uses the s&p 500 companies dictionary to filter out the detetected organizations.
2.merge_new:
Since our dataset is in the form of large number of files for headlines for each day from 2007-2016 so we merged all th files into one file for easy analysis.
3.Timestamp_normalization:
This file normalizes the time stamp value as our data contain 3 time stamps UTC,EDT.ETC so we normalize it to UTC which is also used by Yfinance.
4.Roberta_train_fin_phrasebank:
We fine tune our RoBERTa model in this file with financial phrasebank and save the trained model as .pt.
5.final_data_sentiment:
In this file we apply the trained model on our data and generate the sentiment values.
7.Sentiment_normalization:
Since the sentiment values are 0,1 and 2 we need to normalize it as our model takes scalar input as 0-1.
8.Extracting_each_org_average_sentiemnt: Now we take the required organization from our data and check if for any day it has multiple sentiment values we take the average of all th values and assign it to a single day.

After the above files our sentiment analysis part is complete now the next part is the stock data and concatenating sentiment data with stock data for prediction which is done in these next files 

9.LSTM&GRU_1:
In this part we only take the data for where we have sentiment analysis while leaving the missing values which leaves us with a small non-continous data.
10.LSTM&GRU_2_with_neutral_sentiment:
In this part we added the neutral values for the sentiment data where the sentimnet values were missing in this way we got more continous data but with some imputations.
