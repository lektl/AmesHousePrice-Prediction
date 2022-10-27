# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 2 - Ames Housing Data and Kaggle Challenge

### Overview

Using the Ames housing data, the goal of this project is to create a regression model that is able to accurately predict the sale price of each house in Ames, given a set of features. The evaluation of this project will be done through a Kaggle submission, with leaderboard standings determined by the root mean squared error (RMSE) of your predicted house sale price vs. the actual house sale price. 

### Problem Statement

For our business model as a start-up, we are aiming to set up a Sale Price recommendation tool where users can use to get a recommended Sale Price with just a few details about their property for sale. This webpage would have specific fields for users to fill property details and submit. Using the underlying regression model, the web application will generate a quote estimate for their property Sale Price. The webpage url can be found below.

Ames Housing Sale Price recommendation tool([*source*](https://yxmauw-general-assembly-pub-project-2cloud-appapp-rr21s2.streamlitapp.com/)) - done by Maybelle

### Datasets

This project analysis is based on the following data sets: 

* [`train.csv`](./datasets/train.csv): This data contains all of the training data for my model
* [`test.csv`](./datasets/test.csv): This data contains the test data for my model

### Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|ms_subclass|int64|TRAIN DATA|The building class|
|ms_zoning|int64|TRAIN DATA|Identifies the general zoning classification of the sale|
|lot_frontage|float64|TRAIN DATA|Linear feet of street connected to property|
|lot_area|int64|TRAIN DATA|Lot size in square feet|
|lot_shape|int64|TRAIN DATA|General shape of property|
|lot_config|int64|TRAIN DATA|Lot configuration|
|neighborhood|int64|TRAIN DATA|Physical locations within Ames city limits|
|house_style|int64|TRAIN DATA|Style of dwelling|
|overall_qual|int64|TRAIN DATA|Overall material and finish quality|
|overall_cond|int64|TRAIN DATA|Overall condition rating|
|year_built|int64|TRAIN DATA|Original construction date|
|year_remod/add|int64|TRAIN DATA|Remodel date (same as construction date if no remodeling or additions)|
|roof_style|int64|TRAIN DATA|Type of roof|
|exterior_1st|int64|TRAIN DATA|Exterior covering on house|
|exterior_2nd|int64|TRAIN DATA|Exterior covering on house (if more than one material)|
|mas_vnr_type|float64|TRAIN DATA|Masonry veneer type|
|mas_vnr_area|float64|TRAIN DATA|Masonry veneer area in square feet|
|exter_qual|int64|TRAIN DATA|Exterior material quality|
|foundation|int64|TRAIN DATA|Type of foundation|
|bsmt_qual|object|TRAIN DATA|Height of the basement|
|bsmt_exposure|object|TRAIN DATA|Walkout or garden level basement walls|
|bsmtfin_type_1|object|TRAIN DATA|Quality of basement finished area|
|bsmtfin_sf_1|float64|TRAIN DATA|Type 1 finished square feet|
|bsmt_unf_sf|float64|TRAIN DATA|Unfinished square feet of basement area|
|total_bsmt_sf|float64|TRAIN DATA|Total square feet of basement area|
|heating_qc|object|TRAIN DATA|Heating quality and condition|
|1st_flr_sf|int64|TRAIN DATA|First Floor square feet|
|2nd_flr_sf|int64|TRAIN DATA|Second floor square feet|
|gr_liv_area|int64|TRAIN DATA|Above grade (ground) living area square feet|
|bsmt_full_bath|float64|TRAIN DATA|Basement full bathrooms|
|full_bath|int64|TRAIN DATA|Full bathrooms above grade|
|half_bath|int64|TRAIN DATA|Half baths above grade|
|bedroom_abvgr|int64|TRAIN DATA|Number of bedrooms above basement level|
|kitchen_qual|object|TRAIN DATA|Kitchen quality|
|totrms_abvgrd|int64|TRAIN DATA|Total rooms above grade (does not include bathrooms)|
|fireplaces|int64|TRAIN DATA|Number of fireplaces|
|fireplace_qu|object|TRAIN DATA|Fireplace quality|
|garage_type|object|TRAIN DATA|Garage location|
|garage_yr_blt|float64|TRAIN DATA|Year garage was built|
|garage_finish|object|TRAIN DATA|Interior finish of the garage|
|garage_cars|float64|TRAIN DATA|Size of garage in car capacity|
|garage_area|float64|TRAIN DATA|Size of garage in square feet|
|wood_deck_sf|int64|TRAIN DATA|Wood deck area in square feet|
|open_porch_sf|int64|TRAIN DATA|Open porch area in square feet|
|mo_sold|int64|TRAIN DATA|Month Sold|
|yo_sold|int64|TRAIN DATA|Year Sold|
|saleprice|int64|TRAIN DATA|the property's sale price in dollars|

### Executive Summary

The Ames Housing Dataset is an exceptionally detailed and robust dataset with over 70 columns of different features relating to houses. The dataset contains information from the Ames Assessor’s Office used in computing assessed values for individual residential properties sold in Ames, IA from 2006 to 2010.

In this project, I performed comprehensive exploratory data analysis to understand linear relationships among the most important variables and detect potential issues such as sknewness, outliers and missing values. Then, I handled these issues by cleaning the data and performed feature engineering. Lastly, I built regression models to predict the house prices.

### Conclusions and Recommendations

From the EDA, we can see that the factors that affect house price the most are likely to be quality (e.g. overall_qual) and area (e.g. gr_liv_area, total_bsmt_sf, garage_area). , based on the relationship with saleprice revealed in the correlation heatmap and scatterplots.

Limitations:

- Although my model seems to do well, it might not be able to come up with accurate predictions for properties above $400k due to the right-skewed distribution of Sale Price.
- Features with good predictive value for Sale Price tend to have high multicollinearity with each other.
- This model does not take into account any economic or external factors that may affect Sale Price: for example, housing loan interest rates, unemployment figures, inflation, natural disasters etc.

Recommendations:

- Collect more recent data (newer than 2010).
- Collect more data points with house saleprices above $400k.
- Get access to Sale Condition feature.
- Collect data on other features not in current data that may have influence on house saleprice (e.g. Transportation facilities nearby).
