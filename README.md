# Electricity usage prediction using PG&E load data
### Team: T07
### Members: Serena Xue (qingxue@andrew.cmu.edu); Kaia Hu (kaiqihu@andrew.cmu.edu)

## Task
### Goal: 
1. Predict electricity usage of next month by different PG&E service areas. 
2. PG&E Electricity Rate Payer Profile Segmentation
### Type of learning: 
1. Prediction part: supervised learning
2. Classification part: unsupervised learning

## Experience
Domain: electricity load forecasting 
Most traditional models for predicting energy usage often rely on time series analysis techniques and regression models, which focus on historical data. However, due to the climate change and recent paradigm shifts in energy consumption (AI, data centers, EV charging, renewable energy…), those traditional models may not be able to capture those changes. Therefore, we are proposing the addition of different datasets and machine learning tools to further boost prediction accuracy. 


## Motivation
In recent years, California’s energy market has become increasingly volatile due to the growing impacts of drought, wildfires, and rapid population growth. These factors have placed immense pressure on utilities like PG&E to maintain a stable and reliable energy supply amid rising and fluctuating demand. Motivated by this challenge, we decided to build a machine learning model to predict next month’s electricity usage for PG&E. The goal was to move beyond traditional forecasting approaches and develop a more rigorous, data-driven model that accounts for time series trends, climate/weather variation, demographic shifts, infrastructure capacity, and historical energy usage patterns. By incorporating these multidimensional factors, we aim to create a model that can provide more accurate demand load predictions, enabling PG&E to better prepare for demand surges, optimize resource allocation, and enhance grid resilience.

## Data
### Source
Electricity usage data from PG&E public datasets: https://pge-energydatarequest.com/public_datasets/
Weather data scraping from Weather Underground: https://www.wunderground.com/history/monthly/us/ca
### Structure
Electricity usage data: <br>
Fields: <br>
Zip Code, Month, Year, Customer Class, Total Customers, Total KWH, Average KWH <br>
Time range: <br>
From 2020 to 2024, monthly.<br>
Length: <br>
About 9000~10,000 rows per year, 45,000 rows in total <br>
Weather data: <br>
Fields:  <br>
Weather Station, Temperature, Dew Point, Precipitation, Wind, Sea Level Pressure <br>
Time range:<br>
From 2020 to 2024, monthly.<br>
Length:<br>
About 150 weather stations. About 9,000 rows in total.<br>
### Data preparation
Map weather station location to its zip code. <br>
Merge datasets by zip code and date
### Related work
https://github.com/nikithareddyb/electricity-forecasting <br>
This project predicts monthly electricity usage from history usage data. Our project will explore more models and include more features like weather, population and income level. <br>
https://www.sciencedirect.com/science/article/pii/S092041051930600X <br>
This paper reviews the pros and cons of conventional models and AI-based models for energy consumption forecasting.  <br>

## Proposed Models
### To predict power usage:	
Performance Metric: MSE
### Model
1. ARIMA 
2. LSTM
3. Regression
4. Temperature
5. Serviced population
6. Severe heat / cold events (if data available)
7. Income level (if data available) 
### To segment customer profiles:
Clustering (Classification): Cluster energy usage patterns by postal code/census tract
