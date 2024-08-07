## Project Overview
This project analyzes the Irish housing market using ten years of monthly average housing prices and sales volume data by county from the Irish Property Services Regulatory Authority (PSRA). Key steps include:
- Data Management: Saving and retrieving data from a database.
- Data Wrangling: Cleaning and preparing the data for analysis.
- Exploratory Data Analysis and Visualization: Creating various visualizations, including pie charts and integrated line and bar charts.
- Forecasting: Predicting Dublin housing prices for the next month using time series analysis and deep neural networks. The model employs LSTM, Dense, Dropout, and LayerNormalization layers, achieving a MAPE of 7.8% on the test dataset.
- Finally, the project compares the actual and forecasted values in a multi-line graph.

## Irish Property Dataset

The Property Services Regulatory Authority (PSRA) is an Irish property regulating body. Their official website (https://www.propertypriceregister.ie/website/npsra/pprweb.nsf/PPR?OpenForm) provides access to the Residential Property Price Register data to the public.  Daily transaction data has been available since January 2010 to the present date (last updated in May 2024), with columns including Address, County, Eircode, Price, Description of Property and others. 

Yearly datasets were downloaded, merged into a CSV file with over 65 000 rows, and uploaded into the relational database MySQL. Subsequently, the dataset was retrieved from the database and preprocessed using techniques such as adjusting data types, renaming columns and standardising formats. After cleaning up, a new dataset was saved in the database available for data analysis

## Forecast Model and Evaluation

The analysis applies MinMax Scaler to preprocess monthly prices. The data in a fixed moving window is used as features to predict the subsequent value. 85 percent of the data is used for training, which is sliced before a timestamp, and the data afterwards is for validation. Forecasting series starts at the timestamp minus the window size and ends at the second last datapoint.
The top performing model’s architecture combines LSTM, Dropout, LayerNormalization and Dense layers, achieves a av- erage Mean Absolute Percentage Error of 7.8, which indicates a high accurate forecasting.

## Paper
A summary article, 'Irish Housing Market Assessment', which includes visualizations and basic analysis is attached in the repository.
