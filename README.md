# Deep Learning

Due to the volatility of cryptocurrency speculation, investors will often try to incorporate sentiment from social media and news articles to help guide their trading strategies. One such indicator is the Crypto Fear and Greed Index (FNG) which attempts to use a variety of data sources to produce a daily FNG value for cryptocurrency. In this mini project, I built and evaluated deep learning models using both the FNG values and simple closing prices to determine if the FNG indicator provides a better signal for cryptocurrencies than the normal closing price data.

I used deep learning recurrent neural networks to model bitcoin closing prices. One model will use the FNG indicators to predict the closing price while the second model will use a window of closing prices to predict the nth closing price.

My task were to:

1.  Prepare the data for training and testing
2.  Build and train custom LSTM RNNs
3.  Evaluate the performance of each model

# Prepare the data for training and testing

For the Fear and Greed model, I used the FNG values to try and predict the closing price. A function is provided in the notebook to help with this.

For the closing price model, I used previous closing prices to try and predict the next closing price.

Each model will need to use 70% of the data for training and 30% of the data for testing.

Apply a MinMaxScaler to the X and y values to scale the data for the model.

Finally, reshape the X_train and X_test values to fit the model's requirement of samples, time steps, and features. (example: X_train = X_train.reshape((X_train.shape[0], X_train.shape[1], 1)))


Using 30% of the data for testing, I have found the following:

The Closing model had a lower loss of 0.0627, compared to the FNG model that had a loss of 0.1242.

The Closing model tracks the actual values better over time compared to the FNG model.



![image](https://user-images.githubusercontent.com/80648280/134361125-8826e788-e7f7-488a-a282-edf10910e35c.png)


![image](https://user-images.githubusercontent.com/80648280/134361280-78a42795-2798-4529-90bf-571ceaa3e394.png)
