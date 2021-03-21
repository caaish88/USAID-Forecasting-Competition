# USAID's Intelligent Forecasting: A Competition to Model Future Contraceptive Use
USAID works with local health care authorities and partners to support voluntary family planning and reproductive health programs in nearly 40 countries across the globe, which includes ensuring that contraceptives are available and accessible to people who need them.

The goal of the Intelligent Forecasting Competition is to predict consumption (stock_distributed in the Primary Data Dictionary) for 11 contraceptives across 156 health service delivery sites in the public sector health system in Côte d’Ivoire. The predictions should be made monthly for three months: October 2019, November 2019, and December 2019, using the dataset provided.

## Datasets
There are 5 input data sets shared for the competition:

a.	Contraceptive logistics data (Primary dataset - Monthly)
b.	Contraceptive case data (Monthly and Annual)
c.	Product data
d.	Service delivery site data

Contraceptive logistics dataset has month wise quantity received, dispensed, on hand etc., product and site wise for 45 months from January 2016 through September 2019. 

Service delivery site file is a geo spatial dataset which provided additional information for the health services delivery sites in the primary dataset such as the location information (longitude and latitude), region and district. The product file provided additional information for contraceptive products in the primary dataset. 

Finally, the contraceptive case data (monthly and annual) captures data pertaining to contraceptive use aggregated at a district level. 

## Exploratory Data Analysis
The historical data of response variable stock distributed follows a tweedie distribution – which has lot of data points at zero and then
followed by non-negative data points. 

![Image description](https://github.com/caaish88/USAID-Forecasting-Competition/blob/main/Exploratory%20Data%20Analysis%20-%20Images/Tweedie_distribution.png)
 
As data has lot of zero demand, SKUs were categorized based on % of records with zero demand:

![Image description](https://github.com/caaish88/USAID-Forecasting-Competition/blob/main/Exploratory%20Data%20Analysis%20-%20Images/Zero_demand.png)

## Models Tested:

On SKUs were less than 80% of the records have zero demand, Traditional and Machine Learning Algorithms (Global Models) were implemented

On SKUs were more than 80% of the records have zero demand, Traditional algorithms (Naïve Forecasting – Local Model) were implemented.  

## Evaluation Metric
The metric that will be used to evaluate the models is the mean absolute scaled error (MASE) of the predictions. The error will be calculated for each prediction in the submission and then averaged across all site level predictions for each contraceptive.

## Best Model Selection
Models with lowest MASE on the test data was selected as the best model and used to predict the 3 months of stock distribution

