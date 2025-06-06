# 📈 Stock Market Price Prediction using RNN

This project demonstrates how to build and train a Recurrent Neural Network (RNN) using TensorFlow to predict stock market prices. The primary goal is to showcase the implementation of RNNs rather than to achieve high prediction accuracy. You’re encouraged to use this repository as a starting point and enhance it with your own techniques for better prediction performance.

---

## 🚀 Getting Started

### ✅ Prerequisites
Ensure you have `TensorFlow` and the following Python packages installed:

Python 2.7
BeautifulSoup==3.2.1
numpy==1.13.1
pandas==0.16.2
scikit-learn==0.16.1
scipy==0.19.1
tensorflow==1.2.1
urllib3==1.8


---

### 📥 Data Preparation

1. **Download S&P 500 Historical Data**  
   Visit [Yahoo! Finance: ^GSPC](https://finance.yahoo.com/quote/%5EGSPC?p=^GSPC), navigate to the **Historical Data** tab, select the **Max** time range, and download the data as a CSV file.  
   Save the file to:  

data/SP500.csv


2. **Fetch Individual Stock Data**  
Run the script below to download individual stock data for companies in the S&P 500:

python data_fetcher.py

Each stock's data will be saved to:

data/{{stock_symbol}}.csv

⚠️ Note: The Google Finance API only returns ~4000 days of data. For older data, modify data_fetcher.py to send multiple requests per stock.
Alternatively, you can extract data from the following archive to use directly:
[stock-data-lilianweng.tar.gz]
(Replace the data folder with extracted content for test runs.)

## 🧠 Model Training
Use the following command to see available training options:
python main.py --help

To train the model, run:

python main.py

## Example Commands
Train on S&P 500 only (no embeddings):

python main.py --stock_symbol=SP500 --train --input_size=1 --lstm_size=128 --max_epoch=50

- Train using 100 stocks with embedding size of 8:

python main.py --stock_count=100 --train --input_size=1 --lstm_size=128 --max_epoch=50 --embed_size=8

## 📊 Visualizing with TensorBoard
To monitor training logs using TensorBoard:

cd stock-rnn
mkdir logs
tensorboard --logdir ./logs --port 1234 --debug

## 📌 Notes
This project is designed primarily for educational and demonstrational purposes.

For better prediction accuracy, consider experimenting with model architectures, hyperparameters, and feature engineering.
