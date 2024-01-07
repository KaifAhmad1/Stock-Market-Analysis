# HDFC Bank Opening Stock Price Prediction

## Overview
This project focuses on predicting the **`Opening Stock Prices`** of HDFC Bank, employing time series analysis and a **`Long Short-Term Memory (LSTM)`** neural network.

## Technical Overview
### Dataset Info
- The dataset comprises historical stock data with **`5305`** data points and **`15`** features, including **`Date, Prev-Close, Open, High, Low, Last, Close, VWAP, Volume, Turnover, Trades, Deliverable Volume, %Deliverble.`**

### Model Architecture
#### Data Overview and Preprocessing
- HDFC Bank stock price prediction dataset with **`5306 entries and 15 columns.`**
- Addressed missing values in **`Trades, Deliverable Volume, and %Deliverble.`**
- **`Trades`** column dropped due to extensive missing data, resulting in a cleaned dataset ready for analysis.
- Imputed missing values in **`Deliverable Volume`** and **`%Deliverble`** columns using their respective **`means`**; the updated dataset is displayed.

#### Time Series Analysis and Visualization
- Plotted closing prices over time using Matplotlib and Plotly Express.
- Visualized trading volume trends over time.

#### Statistical Analysis
- Provided summary statistics for key features.
- Conducted correlation analysis, presenting a correlation matrix and scatter plot matrix.
- Interpreted correlations, with a focus on the 'Close' feature.

#### Correlation Matrix Insights
- Analyzed correlations among price-related features, volume, turnover, deliverable volume, and % deliverable.
- Notable insights include strong positive correlations among price-related features, weak correlation of volume with prices, and the relationship between deliverable volume and total volume.

#### Lag Analysis
- Conducted lag analysis by creating lag features for closing prices.
- Visualized autocorrelation of closing prices with different lag periods using Plotly Express.

#### Feature Scaling and Normalization
- Implemented StandardScaler for feature scaling and normalization.
- Developed a concise data_prep function for lookback, future, and scaler-based data preparation, returning input sequences (X), targets (y), original training data (df_train), and date index.

#### LSTM Model and Hyperparameters
- **Parameters:** `Lookback window = 30, Future time steps = 1`
- **Architecture:** `3-layer LSTM (50 units), Dropout (0.2), Final LSTM (50 units), Dropout (0.2), Dense (1 unit)`
- **Training:** `Adam optimizer, Mean Squared Error loss, 100 epochs, Batch size 64, Early stopping (patience=15)`

##### Training History
- Successfully trained the model with decreasing loss over `100` epochs.

##### Prediction and Output
- Applied the model for opening value predictions.
- Utilized inverse scaling for descaled predictions.
- Generated an output DataFrame with dates and predicted descaled opening values.

#### Loss Visualization
- Leveraged Plotly `(px.line)` to visualize training (solid, blue) and validation (dashed, red) losses.
- Incorporated circular markers for training and `x` markers for validation.
