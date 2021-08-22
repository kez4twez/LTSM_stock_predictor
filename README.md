# LTSM stock predictor
----
This notebook takes advantage of Recurring Neural Networks (RNN) to use approximately 18 months of Bitcoin price data to train a RNN model, use a rolling window of 10 periods to predict 5 days of Bitcoins closing price, unknown to the training model. Similarly the same is done using the Bitcoin Fear and Greed index values over the same time frame.

In the resources folder are two CSV files, one of Bitcoin price action, and the other of the fear and greed index values over the same time period.

1. First the data is cleaned and put into a dataframe
2. Data is parsed through a function to give a rolling window of the users choosing (I experimented with windows from 7 to 16)
3. The data is then split into a 70/30 training/testing set
4. The data is scaled using MinMaxScaler
5. Data is reshaped into a suitable format for the RNN
6. The RNN model is built using 3 LTSM layers, 3 dropout layers and a Dense output layer
7. The model is compiled and run using 10 epochs and a batch size of 1
8. The real and predicted prices are put into a dataframe and plotted


The above steps are completed with both the closing price data and the fear and greed index data.

----

## Conclusion
The model that used the closing prices produced more accurate predictions.

A window of 10 for the price data model worked best.
A window of 13 for the FNG data model worked best.