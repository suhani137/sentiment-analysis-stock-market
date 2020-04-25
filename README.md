# sentiment-analysis-stock-market
Sentiment analysis of tweets for predicting change in stock values day-on-day

1. Time Series
i. Since the one of the objectives of the study is to study the impact of the economic slowdown on auto stocks, NIFTY Auto index was chosen to predict stock prices. Opening and closing values of the index were collected for a one-year period from 1st Nov, 2018 upto 31
st Oct, 2019 (365 days).
ii. Also includes tests for conditions of stationarity like ADF, Durbin-watson,  normality test and ARCH LM test.
iii. But there were many missing values. This is because stock markets remain closed on weekends, national holidays and festivals. So, these missing values have to be estimated for further analysis.The following formula was used to replace missing values:
Price on day t = (Closing Price on previous day + Opening Price on next day)/2

2. Sentiment Analysis
i. For sentiment analysis, 10 tweets per day (3,650 in total) were collected for a period of 365 days. Tweets were collected with hashtags of those companies that are included in NIFTY Auto index. These include: #bajajauto, #tatamotors, #heromotoco, #bharatforge, #eichermotors, #exideind, #mrftyre, #ashokleyland, #boschltd, #apollotyre, #tvsmotor, #mothersumi, #amarajabat, #mahindra, #maruti, #niftyauto, #autosector, #autoslowdown.
ii. For determining the compound score and sentiment for each day, average of the 10 tweets captured for each day is taken to get a final score to be put into the model. 
iii. Compound score >= 0.05:Positive,
Coumpound score <=-0.05: Negative
Compound csore between -0.05 ans 0.05: Neutral

3. Granger Causality
Granger causality test was used to test whether there exists a cause and effect relationship between sentiment and stock prices. If only such a relationship exists, prediction of stock prices can be done on the basis of sentiment scores.

4. Prediction
Finally, after establishing relationships between sentiment and stock price movement, prediction of stock price was done with two artificial neural networks, namely Long Short-Term Memory (LSTM) and Gated Recurrent Unit (GRU). Model performance was determined on the basis of Mean Squared Error (MSE).
