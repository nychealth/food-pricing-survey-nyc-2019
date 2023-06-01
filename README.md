# Food Pricing Survey, NYC (2019)
[![DOI](https://zenodo.org/badge/634944429.svg)](https://zenodo.org/badge/latestdoi/634944429)


This repository contains two datasets that were described in the manuscript titled "Data on location and retail price of a standard food basket in supermarkets across New York City" in the journal Data In Brief available at [here]([https://zenodo.org/badge/latestdoi/634944429](https://www.sciencedirect.com/science/article/pii/S2352340923003414)). The data sets contain price data for 10 perishable food items, collected via in-person visits to 163 supermarkets across New York City. 

Finally, portions of the data have been visualized in the Food Environment Equity Dashboard created by the Urban Food Policy Institute at CUNY (can be seen here: https://sites.google.com/view/feed-nyc/food-affordability)


# Files

| File | Type | Description |
| ---- | ---- | ----------- |
| **Raw_Pricing_data_final.csv** |	Dataset	| Dataset with raw pricing data and additional information collected about each item. More details of the dataset are provided below |
| **Data dictionary for Raw_Pricing_data_final.csv** | Data Dictionary | Data Dictionary for the dataset containing the raw pricing data |
| **Cleaned_Pricing_data_imputed_final.csv** |	Dataset	| Analytic dataset of the food prices.|
| **Data dictionary for Cleaned_Pricing_data_imputed_final.csv** | Data Dictionary | Data Dictionary for the analytic dataset of pricing data |
| **Pulling ZCTA-level ACS data.Rmd**	| R Markdown script | This code pulls 2014-2019 ACS data from the Census API. Generates a dataset with indicators for ZCTAs in NYC. The results are exported to to the dataset called  *Neighborhood indicators_final.csv* (see below)|
| **Neighborhood indicators_final.csv**	| Dataset | This dataset includes the calculated indicators for each ZIP code |
| **Data dictionary for Neighborhood indicators_final.csv**	| Data Dictionary | Data Dictionary for the dataset of ZIP code level indicators |



# Datasets

The two datasets provided here contain pricing data recoded for the 10 food items focused on for this survey. Once the data collection was completed in the stores by personnel from the NYC Department of Health and Mental Hygiene, the data were downloaded and processed to make an analytic dataset. 

| Data set | Description |
| -------- | ----------- |
|**Raw_Pricing_data_final**| This dataset contains raw data collected on each of the 10 pre-selected food items and contains additional information related to data collection including  whether a preferred or alternative version (e.g., presentation, packaging) of each food item was identified in the store; item brand name; whether the item was on sale; a flag indicating whether the item was organic. |
| **Cleaned_Pricing_data_imputed_final** | Analytic data includes consolidated price values (of the preferred and alternate options) into a single variable and imputed missing values for each food items. In addition, it includes to the cost of the "food basket" made from summing the cost of the ten pre-selected items.|
| **Neighborhood indicators_final.csv**	| This dataset contains the ZIP level indicators, calculated using ACS data pulled from the Census API. The R code used to generate these estimates is available in the *Pulling ZCTA-level ACS data.Rmd* file |


# Sampling and Statistical Considerations

Individual supermarkets were chosen through purposeful sampling based on accessibility by public transport. The Health Department prioritized sampling in gentrifying neighborhoods that may be experiencing rapid changes in the food environment. The supermarkets sampled included global brand grocery stores as well as local store brands that are independently managed.

In some cases, one of the items of interest could not be found in the supermarket. Missing price data for each item was imputed via multiple imputation, using the observed neighborhood and item price to generate imputed values. All imputation was done using the mice package in R. 

# Contact

Aldo Crossa: acrossa@health.nyc.gov
