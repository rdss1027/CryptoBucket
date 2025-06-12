# Cryptocurrency Price Prediction using AI

This repository contains the code and model for predicting cryptocurrency prices using historical data and an AI-driven approach. The model uses Long Short-Term Memory (LSTM) networks to improve performance over traditional Artificial Neural Networks (ANN). The solution integrates real-time cryptocurrency data via the CoinGecko API (refer to the CoinGecko API repository) to predict the opening price of a cryptocurrency for the next day.
Project Overview

The goal of this project is to forecast the opening price of a selected cryptocurrency for the next day. The model is based on LSTM networks, which are specialized for time series prediction tasks and are better at capturing sequential dependencies in the price data. The predictions are made using historical data, and the system can provide real-time predictions through a simple API built using Flask.
Tech Stack

    Programming Language: Python

    Machine Learning Libraries: TensorFlow, Keras, scikit-learn

    API: Flask

    Data Source: CoinGecko API (for real-time cryptocurrency data)

    Model Architecture: LSTM (Long Short-Term Memory), ANN (Artificial Neural Network)

File Structure

/crypto-price-prediction
│
├── app.py                   # Flask API for making predictions
├── data_handler.py           # Functions to handle data preprocessing
├── model_utils.py            # Utility functions for model training and evaluation
├── train.py                  # Script to retrain the LSTM model
├── requirements.txt          # Required dependencies
├── logs/                     # Logs for model training and predictions
├── models/                   # Directory containing trained model files
├── static/                   # Static files for frontend (if any)
├── templates/                # HTML templates for frontend (if any)
├── data/                     # Folder containing raw and processed data
├── __pycache__/              # Compiled Python files
├── B14.pdf                   # Document related to the project (if any)
└── README.md                 # Project documentation

Installation and Setup
1. Clone the Repository

git clone https://github.com/your-username/crypto-price-prediction.git
cd crypto-price-prediction

2. Install Dependencies

Ensure that you have Python 3.7 or higher installed, then create and activate a virtual environment:

python3 -m venv venv
source venv/bin/activate   # On Windows, use `venv\Scripts\activate`

Install the required packages:

pip install -r requirements.txt

3. Set up the CoinGecko API Integration

This project relies on another repository to handle the CoinGecko API integration. Please follow the instructions in the CoinGecko API repository to set it up. You’ll need to generate an API key and link it to this project for real-time cryptocurrency data.

Once you’ve set up the CoinGecko API repository, refer to it for the api_key and API handling functions.
Running the Application

To start the Flask application and begin receiving predictions:

python app.py

The server will run on http://localhost:5000. You can access the prediction API endpoint to get the next day’s predicted opening price for a cryptocurrency.
API Endpoints
1. Get Prediction

URL: /predict

Method: GET

Description: Get the predicted opening price of a selected cryptocurrency for the next day.

Parameters:

    currency (string): The cryptocurrency symbol (e.g., 'bitcoin', 'ethereum').

Example Request:

GET http://localhost:5000/predict?currency=bitcoin

Response:

{
  "currency": "bitcoin",
  "predicted_opening_price": 35000.23
}

Training the Model
1. Training Data

The model uses historical price data of cryptocurrencies (e.g., daily open, close, high, low prices) fetched from the CoinGecko API. This data is stored in the data/ folder.
2. Retraining the Model

To retrain the LSTM model with new data, run the training script:

python train.py

This script will:

    Fetch historical data using the CoinGecko API (from the CoinGecko API repository).

    Preprocess and clean the data.

    Train the LSTM and ANN models.

    Save the trained models in the models/ directory.

Contributing

We welcome contributions to improve this project! Feel free to fork the repository, create a new branch, and submit a pull request with your changes.
License

This project is licensed under the MIT License – see the LICENSE file for details.
Acknowledgments

    CoinGecko API: For providing real-time cryptocurrency data (check out the CoinGecko API repository).

    TensorFlow/Keras: For the machine learning models and LSTM implementation.

    Flask: For serving the predictions via a simple API.
