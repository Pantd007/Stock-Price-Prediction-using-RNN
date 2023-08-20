# Predict stock market prices using RNN

Author: Deepak Pant 22M0035@iitb.ac.in

# **Problem Statement:**
Stock Price Prediction using Recurrent Neural Networks (RNN) with LSTM Architecture

Forecasting stock prices is a challenging endeavor due to the inherent volatility and complexity of financial markets. This project tackles this challenge by utilizing advanced machine learning techniques, specifically the Long Short-Term Memory (LSTM) type Recurrent Neural Network (RNN), to predict stock prices. The project aims to engineer an accurate predictive model capable of forecasting stock prices based on historical data, with a focus on achieving consistent performance.

# **Project Objectives:**

The primary objective of this project is to develop a robust stock price prediction model that leverages the power of LSTM-based Recurrent Neural Networks. Through a series of steps that involve data preprocessing, model architecture design, training, and evaluation, the project aims to achieve the following specific goals:

1. **Data Preprocessing:** Prepare historical stock price data for model training and testing. This includes cleaning, normalization, and structuring the data to make it suitable for LSTM-based RNN input.

2. **LSTM Model Development:** Engineer an LSTM-based RNN algorithm designed to analyze temporal patterns and dependencies in stock price data. Configure the model's architecture, including the number of layers, units, and activation functions.

3. **Training and Validation:** Train the LSTM model using historical stock price data, partitioning the dataset into training and validation sets. Employ appropriate training techniques, such as gradient descent optimization, to enhance convergence and prevent overfitting.

4. **Accuracy Assessment:** Evaluate the accuracy of the LSTM model's predictions on the training dataset. Measure performance using relevant evaluation metrics, including accuracy and loss functions.

5. **Forecasting Performance:** Demonstrate the predictive capability of the model by forecasting the closing stock price every third day based on the preceding two days' stock prices. Analyze the model's ability to capture price trends and patterns.

# **Importance and Implications:**

The successful completion of this project holds several significant implications:

- **Market Insight:** The developed stock price prediction model offers insights into potential future stock price trends, assisting traders, investors, and financial analysts in making informed decisions.
- **Risk Management:** Accurate stock price predictions contribute to effective risk management by enabling stakeholders to anticipate market movements and adjust their strategies accordingly.
- **Algorithm Validation:** The high accuracy achieved on the training dataset demonstrates the reliability of the LSTM-based RNN approach for stock price prediction.
- **Forecasting Tool:** The project outcome provides a practical tool for individuals and institutions interested in gaining a competitive edge in the stock market.

By leveraging the power of deep learning and LSTM-based RNNs, this project aims to elevate stock price prediction accuracy and contribute to the advancement of predictive analytics in the financial domain. The insights gained from this project can inform trading strategies, investment decisions, and risk management practices, fostering better outcomes in the dynamic landscape of stock trading.

# Instructions to run the code: 
1. Make sure `tensorflow` has been installed.
2. First download the full S&P 500 data from [Yahoo! Finance ^GSPC](https://finance.yahoo.com/quote/%5EGSPC?p=^GSPC) (click the "Historical Data" tab and select the max time period). And save the .csv file to `data/SP500.csv`.
3. Run `python data_fetcher.py` to download the prices of individual stocks in S & P 500, each saved to `data/{{stock_abbreviation}}.csv`.
(NOTE: Google Finance API returns the prices for 4000 days maximum. Here is the data archive ([stock-data-lilianweng.tar.gz](https://drive.google.com/open?id=1QKVkiwgCNJsdQMEsfoi6KpqoPgc4O6DD)) of stock prices. Please untar this file to replace the "data" folder in the repo for test runs.)
4. Run `python main.py --help` to check the available command line args.
5. Run `python main.py` to train the model.


For examples,
- Train a model only on SP500.csv; no embedding
```bash
python main.py --stock_symbol=SP500 --train --input_size=1 --lstm_size=128 --max_epoch=50
```

- Train a model on 100 stocks; with embedding of size 8
```bash
python main.py --stock_count=100 --train --input_size=1 --lstm_size=128 --max_epoch=50 --embed_size=8
```

- Start your Tensorboard
```bash
cd stock-rnn
mkdir logs
tensorboard --logdir ./logs --port 1234 --debug
```

My python environment: 
Python version == 3.5
```
BeautifulSoup==3.2.1
numpy==1.13.1
pandas==0.16.2
scikit-learn==0.16.1
scipy==0.19.1
tensorflow==1.2.1
urllib3==1.8
```
