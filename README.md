# HDFC Bank Opening Stock Price Prediction

## Overview:
This project aims to predict the **`Opening Stock Prices`** of HDFC Bank using time series analysis and a **`Long Short-Term Memory(LSTM)`** neural network.

## Technical Overview
### Dataset Info: 
- The dataset includes historical stock data with **5305** data points and **15** features such as **Date, Prev-Close, Open, High, Low, Last, Close, VWAP, Volume, Turnover, Trades, Deliverable Volume, %Deliverble.**
- 
### Model Architecture 
#### Data Overview and Preprocessing:
- HDFC Bank stock price prediction dataset with **`5306 entries and 15 columns.`**
- Data exploration reveals missing values in **'Trades', 'Deliverable Volume', and '%Deliverble'.**
- **`Trades'** column dropped due to extensive missing data; cleaned dataset ready for analysis.
- Imputed missing values in **'Deliverable Volume'** and **'%Deliverble'** columns with their respective **`means`**; verified and displayed the updated dataset.

  #### Time Series Analysis and Visualization:
  - Plotted closing prices over time using Matplotlib and Plotly Express.
  - Also visualized trading volume over time.

  #### Statistical Analysis:
- Presented summary statistics for key features.
- Conducted correlation analysis, including correlation matrix and scatter plot matrix.
- Interpreted correlations with the 'Close' feature.

  #### Correlation Matrix Insights:
- Analyzed correlations among price-related features, volume, turnover, deliverable volume, and % deliverable.
- Highlighted insights such as strong positive correlations among price-related features, weak correlation of volume with prices, and the relationship between deliverable volume and total volume.

  #### Lag Analysis:
- Conducted lag analysis by creating lag features for closing prices.
- Visualized autocorrelation of closing prices with different lag periods using Plotly Express.

  #### Feature Scaling and Normalization:
- Used StandardScaler for feature scaling and normalization.
- Implemented a concise data_prep function for lookback, future, and scaler-based data preparation, returning input sequences (X), targets (y), original training data (df_train), and date index (date_train).

  #### LSTM MOdel and Hyperparameters:
- **Parameters:** Lookback window = 30, Future time steps = 1
- **Architecture:** 3-layer LSTM (50 units), Dropout (0.2), Final LSTM (50 units), Dropout (0.2), Dense (1 unit)
- **Training:** Adam optimizer, Mean Squared Error loss, 100 epochs, Batch size 64, Early stopping (patience=15)

##### Training History:

- Successfully trained the model with loss reduction over 100 epochs.

#####  Prediction and Output:

- Applied the model for opening value predictions.
- Inverse scaling for descaled predictions.
- Output DataFrame with dates and predicted descaled opening values.

  #### Loss Visualization:
- Plotly (px.line) shows training (solid, blue) and validation (dashed, red) losses.
- Circular markers for training, 'x' markers for validation.



