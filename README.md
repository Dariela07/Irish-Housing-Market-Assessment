## INTRODUCTION
This analysis provides an overview of Irish housing market by assessing the average housing price and sales volume by county. Housing prices indicate the living cost in a region; and for property investment purpose, a high transaction volume is favoured due to the ease of resale. Furthermore, the average monthly price for Dublin, the most popular immigrant city in Ireland, is forecasted, offering insights for the property investment decisions.

## Irish Property Dataset

The Property Services Regulatory Authority (PSRA) is an Irish property regulating body. Their official website (https://www.propertypriceregister.ie/website/npsra/pprweb.nsf/PPR?OpenForm) provides access to the Residential Property Price Register data to the public.  Daily transaction data has been available since January 2010 to the present date (last updated in May 2024), with columns including Address, County, Eircode, Price, Description of Property and others. 

Yearly datasets were downloaded, merged into a CSV file with over 65 000 rows, and uploaded into the relational database MySQL. Subsequently, the dataset was retrieved from the database and preprocessed using techniques such as adjusting data types, renaming columns and standardising formats. After cleaning up, a new dataset was saved in the database available for data analysis

## Forecast Model and Evaluation

The analysis applies MinMax Scaler to preprocess monthly prices. The data in a fixed moving window is used as features to predict the subsequent value. 85 percent of the data is used for training, which is sliced before a timestamp, and the data afterwards is for validation. Forecasting series starts at the timestamp minus the window size and ends at the second last datapoint.
The top performing model’s architecture combines LSTM, Dropout, LayerNormalization and Dense layers, achieves a av- erage Mean Absolute Percentage Error of 7.8, which indicates a high accurate forecasting.

## Paper
A summary article, 'Irish Housing Market Assessment', which includes visualizations and basic analysis is attached in the repository.