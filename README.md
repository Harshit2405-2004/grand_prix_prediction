# Formula 1 Grand Prix Winner Prediction

## 🏁 Introduction

This project uses machine learning to predict the winner of a Formula 1 Grand Prix. By analyzing a variety of data points from past and current seasons, this Jupyter Notebook builds a predictive model to forecast the race outcome. It leverages the `fastf1` library to fetch detailed race data, and `scikit-learn` for the machine learning models.

## ✨ Features

The prediction is based on a combination of the following features:

* **Clean Air Race Pace:** The average lap time of a driver when they are not in traffic, providing a true measure of their speed. This is calculated from the previous year's race at the same circuit.
* **Qualifying Performance:** The driver's fastest lap time during the qualifying session of a recent race in the current season.
* **Team Performance Score:** A score calculated based on the current constructor's championship points, normalized against the leading team.
* **Driver's Recent Form:** The average finishing position of a driver over the last few races.
* **Team Reliability Score:** A score based on the number of "Did Not Finish" (DNF) results for each team in the current season.
* **Weather Conditions:** The probability of rain and the temperature at the circuit on race day, fetched from the OpenWeatherMap API.
* **Average Position Change:** Historical data on whether a driver tends to gain or lose positions at a specific track.

## 🛠️ Setup and Installation

To run this notebook, you'll need to have Python 3 installed, along with a few libraries.

1.  **Install Libraries:**
    Open your terminal or command prompt and run the following command to install the necessary packages:

    ```bash
    pip install fastf1 pandas numpy scikit-learn xgboost
    ```

2.  **Enable Cache:**
    The `fastf1` library can cache downloaded data to speed up subsequent runs. The notebook includes a cell to create a cache directory named `f1_cache`. Make sure you have permissions to create directories in the location where you run the notebook.

3.  **Get a Weather API Key:**
    You will need a free API key from [OpenWeatherMap](https://openweathermap.org/api) to fetch weather data. Once you have the key, you will need to add it to the notebook.

## 🚀 How to Use

1.  **Open the Notebook:**
    Launch Jupyter Notebook and open the `Grand_Prix_Prediction_Accurate.ipynb` file.

2.  **Set Prediction Parameters:**
    In the second code cell, you need to configure the parameters for the race you want to predict:
    * `SEASON_YEAR`: The year of the season you are predicting (e.g., `2025`).
    * `PREDICTION_RACE_ROUND`: The round number of the race you want to predict (e.g., `13`).
    * `LAT` and `LON`: The latitude and longitude of the circuit.
    * `forecast_time`: The date and time of the race for the weather forecast.
    * `API_KEY`: Replace the placeholder with your actual OpenWeatherMap API key.

3.  **Update Constructor's Points:**
    In the third code cell, update the `team_points` dictionary with the current constructor's championship points before the race you are predicting.

4.  **Set Previous Year's Race Data:**
    In the fourth code cell, set the `PREVIOUS_RACE_ROUND` to the round number of the same race from the previous year. This is used to calculate the clean air race pace.

5.  **Run the Notebook:**
    Execute the cells in the notebook sequentially. The notebook will fetch the required data, process it, train the models, and then output the prediction.

## 🤖 Model

This project uses the following regression models to predict the race outcome:

* **Gradient Boosting Regressor**
* **XGBoost Regressor**
* **Random Forest Regressor**

The performance of the models is evaluated using the following metrics:

* **Mean Absolute Error (MAE)**
* **Mean Squared Error (MSE)**
* **Root Mean Squared Error (RMSE)**
* **R-squared (R²)**

The notebook also generates a feature importance plot to visualize which features have the most significant impact on the prediction.

## 🏆 Results

After running all the cells, the notebook will output the predicted podium finishers for the selected Grand Prix. 🥇🥈🥉
