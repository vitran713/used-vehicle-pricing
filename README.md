This Jupyter notebook is centered around data cleaning and preprocessing for a dataset on car prices. Here's a detailed summary of what I've implemented in the notebook:

Data Loading and Initial Cleaning: I start by importing the necessary libraries (pandas and numpy) and loading the dataset from a CSV file named 'car_prices.csv'. Initial data cleaning steps include filling missing values for categorical data (like car make, model, trim, body type, and transmission) using strategies such as filling with a default value or using forward filling for ordered data. Numerical columns such as condition, odometer reading, market-related measures, and selling price are treated with statistical methods (mean or median) to handle missing entries. I also remove duplicates based on the Vehicle Identification Number (VIN) and drop rows with essential missing values to ensure data quality.

Date Validation and Conversion: To ensure data integrity, I implement a function to validate date entries in the 'saledate' column. This involves checking each date entry to confirm whether it can be correctly converted to a datetime object in pandas, flagging those that cannot. I then proceed to convert valid date entries to the pandas datetime format, considering timezone information, and remove any entries with invalid dates.

Final Data Preparation: After cleaning and validating the 'saledate' column, I drop any auxiliary columns used during the cleaning process. This leaves the dataset in a clean, well-formatted state, ready for further analysis or modeling steps.

Model Preparation and Feature Engineering: I preprocess the dataset by calculating the age of cars from their manufacturing year and creating dummy variables for categorical features such as make, model, and transmission. I then drop columns that are unnecessary or have high cardinality, ensuring the dataset is optimized for modeling.

Regression Analysis: I use the statsmodels library to perform an Ordinary Least Squares (OLS) regression. This analysis involves preparing the dataset by adding a constant to the features, fitting the model to the training data, and evaluating it using the test set. The model's performance is assessed through the root mean squared error (RMSE), which quantifies the prediction error.

By leveraging different combinations of predictors, I created two separate models with accurate predictions: one that relied on the Manheim Market Report, and another that didn't.
