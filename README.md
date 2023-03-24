# Python-Predictive-Patterns-for-forcasting-Bitcoin-Price
The code retrieves Bitcoin price data from the Huobi API, preprocesses it, trains a SARIMAX model on the training data, and makes predictions for the testing set. The model's performance is then evaluated using the mean squared error, and the predicted prices are visualized against the actual prices using Matplotlib.
SARIMAX (Seasonal AutoRegressive Integrated Moving Average with eXogenous regressors) is a statistical model commonly used in time series analysis to make predictions based on historical data. SARIMAX can be considered a type of machine learning model since it uses data to learn patterns and relationships in the data, and uses this knowledge to make predictions. SARIMAX is often used in combination with other machine learning techniques, such as feature engineering or ensemble methods, to improve its accuracy and effectiveness in forecasting.

The code first imports necessary libraries such as requests, pandas, numpy, matplotlib.pyplot, SARIMAX and mean_squared_error from statsmodels.tsa.statespace.sarimax and sklearn.metrics respectively. Then, it sets the API endpoint and parameters to retrieve 1000 data points of Bitcoin price in USDT from the last 1000 days (1day period).

The retrieved data is converted to a pandas dataframe, sorted by timestamp, and the timestamp column is set as the index with daily frequency. The column "close" is renamed as "price" for readability. The endog variable is set as the "price" column of the dataframe.
The data is split into training and testing sets, with 80% of the data used for training and the remaining 20% for testing. A SARIMAX model is then fitted to the training data with order=(1, 1, 1) and seasonal_order=(1, 1, 1, 12) parameters. The model is then used to predict the prices for the testing set, and an index is created for the predicted prices.

The mean squared error is then calculated by comparing the predicted prices to the actual prices in the testing set. Finally, the predicted prices along with the training and testing data are plotted on a graph using matplotlib.pyplot. The graph also shows the mean squared error. The code used for this Analysis is found [Here] (https://github.com/Joyce696/Python-Predictive-Patterns-for-forcasting-Bitcoin-Price/blob/247d28444114eec8e931f2e54174b7e5f9ec8c50/Bitcoin%20Historical%20Price%20Predictions.ipynb).
