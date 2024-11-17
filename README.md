# EVCS Energy Forecasting

This repository contains the code of my Bachelor's Dissertation, titled "**_Machine Learning Applications in Electric Vehicles_**" at University of Piraeus, as part of my BSc in Computer Science. This work was supervised by professor Yannis Theodoridis, submitted on September 2024 and was eventually graded 10/10.



## Background & Context

Electric Vehicle Charging Station (EVCS) energy forecasting is a critical aspect of modern energy management and urban planning. With the rapid adoption of electric vehicles (EVs), accurate energy demand forecasting at EVCSs ensures that charging infrastructure can meet growing needs without overburdening the grid. Effective forecasting helps prevent energy shortages, minimizes peak load stress, and supports efficient energy distribution, thereby enhancing grid stability. Additionally, it facilitates better integration of renewable energy sources, optimizing the use of sustainable power and reducing carbon emissions. Reliable forecasting empowers stakeholders, including utility companies and city planners, to make informed decisions, improve service reliability, and contribute to sustainable transportation systems.
## Goals
The main goals of this project are:

- To provide accurate energy predictions for an EVCS network over both short-term and long-term forecasting horizons. This will help optimize energy management, ensure sufficient power supply, and enhance grid stability.

- To implement and validate the algorithm presented in this [research paper](https://arxiv.org/pdf/2106.10940), using it as the foundation for building the predictive model. This will ensure that the project aligns with established methodologies and achieves reliable performance benchmarks in EVCS energy forecasting.

## Data Structure

This project utilizes three distinct deep learning models:
- Convolutional Neural Network - CNN
- Convolutional Neural Network with LSTM - ConvLSTM
- Temporal-Graph Convolutional Network - T-GCN

These models are used to forecast energy usage at EV charging stations. The CNN and ConvLSTM models preprocess data using a raster map approach, while the T-GCN model leverages a graph structure to incorporate spatial relationships. The dataset employed is an open-source collection specific to the city of Palo Alto, featuring 47 stations and a total of 33 variables, of which only 5 are selected for model training. The models are trained on historical data spanning from 2012 to 2020 for 100 epochs. Testing for 1-day and 7-day forecasts is performed using the last 30 days of data, whereas testing for the 30-day forecast uses the final 120 days of data. This multi-model approach, combined with diverse data preprocessing methods, enables comprehensive and accurate energy forecasting across different time horizons.
## Executive Summary

The findings of this research highlight that the T-GCN model consistently outperforms the CNN and ConvLSTM models, delivering the most accurate energy predictions across all forecasting horizons. This indicates that the T-GCN's ability to integrate both spatial and temporal information through its graph-based structure offers a significant advantage in modeling the complex relationships inherent in EVCS energy data. The superior performance of the T-GCN model underscores its potential as an effective tool for reliable short-term and long-term energy forecasting in EV networks.

Evaluation scores using RMSE:
| Model     | 1 day   | 7 days  | 30 days |
|-----------|---------|---------|---------|
| CNN       |  122    |   145   |   205   |
| ConvLSTM  |  120    |   140   |   180   |
| T-GCN     |  **116**    |   **136**   |   **108**   |
