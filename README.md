# Cryptocurrency Price Prediction using AI

This repository contains a machine learning model for predicting cryptocurrency prices based on historical data using Long Short-Term Memory (LSTM) networks. The solution leverages real-time cryptocurrency data from the CoinGecko API (refer to the CoinGecko API Repository) to predict the opening price of a cryptocurrency for the next day.
Table of Contents

    Project Overview

    Tech Stack

    File Structure

    Installation and Setup

    API Endpoints

    Training the Model

    Contributing

    License

    Acknowledgments

# Project Overview

The Cryptocurrency Price Prediction system uses an LSTM model for forecasting the opening price of a selected cryptocurrency for the next day. The model is trained on historical price data, and real-time data is fetched using the CoinGecko API.

Key features:

    Real-time data integration from CoinGecko API.

    Predicts next day's opening price for selected cryptocurrencies.

    LSTM network architecture for accurate time-series predictions.

    Flask API for serving predictions.

# Tech Stack

    Programming Language: Python 3.7+

    Machine Learning: TensorFlow, Keras, scikit-learn

    Web Framework: Flask

    Real-time Data: CoinGecko API (CoinGecko API Repo)

    Model Architecture: LSTM (Long Short-Term Memory), ANN (Artificial Neural Network)

# File Structure

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

# Installation and Setup
Step 1: Clone the Repository

git clone https://github.com/your-username/crypto-price-prediction.git
cd crypto-price-prediction

Step 2: Install Dependencies

Ensure that Python 3.7 or higher is installed, then create and activate a virtual environment:

python3 -m venv venv
source venv/bin/activate   # On Windows, use `venv\Scripts\activate`

Now, install the required dependencies:

pip install -r requirements.txt

Step 3: Set up the CoinGecko API Integration

This project relies on the CoinGecko API integration from another repository. Please follow the instructions in the CoinGecko API repository to set it up. You will need to generate an API key and link it to this project for real-time data fetching.

Once you have set up the CoinGecko API, ensure the API key is configured correctly.
Running the Application

To start the Flask app and receive predictions, run:

python app.py

The server will start on http://localhost:5000. You can now make API requests to get the predicted opening price for a cryptocurrency.
API Endpoints
1. Get Prediction

URL: /predict

Method: GET

Description: Get the predicted opening price of a selected cryptocurrency for the next day.

Query Parameters:

    currency (string): The cryptocurrency symbol (e.g., 'bitcoin', 'ethereum').

Example Request:

GET http://localhost:5000/predict?currency=bitcoin

Example Response:

{
  "currency": "bitcoin",
  "predicted_opening_price": 35000.23
}

# Training the Model
1. Training Data

The model uses historical price data of cryptocurrencies (such as daily open, close, high, low prices) which is fetched from the CoinGecko API. This data is stored in the data/ folder.
2. Retraining the Model

To retrain the model with new data, run the following command:

python train.py

This script will:

    Fetch historical data using the CoinGecko API.

    Preprocess and clean the data.

    Train both the LSTM and ANN models.

    Save the trained models to the models/ directory.

# Contributing

We welcome contributions to improve this project! If you want to contribute, follow these steps:

    Fork the repository.

    Create a new branch for your changes.

    Submit a pull request with a description of your changes.

# License

This project is licensed under the MIT License – see the LICENSE file for details.
Acknowledgments

    CoinGecko API: For providing real-time cryptocurrency data. Visit the CoinGecko API repository.

    TensorFlow/Keras: For providing the tools to build and train the LSTM model.

    Flask: For serving the predictions via a simple API.
