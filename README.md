# **Photovoltaic Power Forecasting with LSTM and Attention Mechanisms**

This repository provides an end-to-end solution for photovoltaic power forecasting using deep learning models. The project uses Bidirectional LSTM networks enhanced with attention mechanisms to predict power generation trends based on historical data.

---

## **Table of Contents**
1. [Introduction](#introduction)  
2. [Dataset](#dataset)  
3. [Preprocessing](#preprocessing)  
4. [Model Architecture](#model-architecture)  
5. [Results](#results)  
6. [Requirements](#requirements)  
7. [How to Run](#how-to-run)  
8. [Future Work](#future-work)  
9. [License](#license)

---

## **Introduction**
Photovoltaic power forecasting is essential for energy grid optimization and planning. This project demonstrates how deep learning techniques, specifically LSTMs with attention mechanisms, can improve the accuracy of forecasting based on historical data from the 50Hertz Photovoltaic dataset.

---

## **Dataset**
The dataset is sourced from the 50Hertz API and includes historical records of photovoltaic power generation from 2010 to 2019.

- **Features**:
  - Power generation (`MW`)
  - Date attributes (`Day`, `Month`, `Year`)

- **URL**:  
  Example data source links:  
  `https://ws.50hertz.com/web02/api/PhotovoltaicActual/DownloadFile?fileName=YYYY.csv`  
  *(Replace `YYYY` with the year for specific files.)*

---

## **Preprocessing**
The data is preprocessed to:
1. Clean and reformat date fields.
2. Aggregate daily power generation values.
3. Standardize the data using `MinMaxScaler`.

**Key Functions**:
- `reg_data`: Processes raw CSV files.
- `split_data`: Splits data into training and testing sets.
- `Split_weekly`: Prepares data for LSTM input.

---

## **Model Architecture**
Two deep learning models are implemented:

### 1. **Bidirectional LSTM**
- **Layers**:
  - Bidirectional LSTM
  - Dropout
  - Dense (with `tanh` activation)

### 2. **LSTM with Attention**
- **Layers**:
  - Bidirectional LSTM
  - Dropout
  - Custom Attention Layer
  - Dense (with `linear` activation)

The attention mechanism improves interpretability by assigning weights to time steps most relevant to predictions.

---

## **Results**
- **Loss**: Achieved mean squared error (MSE) of **0.028** on the test set.
- **R² Score**: **0.6527**
- **Visualization**: Training and validation loss plotted for both models.

---

## **Requirements**
Install the following dependencies to run the project:

- Python 3.8+
- Libraries:  
tensorflow keras numpy pandas matplotlib seaborn scikit-learn
