# Used Car Price Prediction model using Decision Tree Regressor

#### Employed a prediction model using Decision Tree Regressor without and with imputed data (using an approximation method and HistGradientBoostingClassifier).

Used Cars dataset: [Dataset Link](https://www.kaggle.com/datasets/austinreese/craigslist-carstrucks-data) 

Dataset contains all relevant information that Craigslist provides on car sales including columns like price, condition, manufacturer, model, and 18 other categories.

Agenda: To Develop a predictive model to estimate the price of used cars by leveraging various parameters that characterize the automobiles.

## Data Cleaning
### Removing Outliers for "Price"
<img width="1034" alt="Screenshot 2024-02-07 at 11 05 40 AM" src="https://github.com/Shanephear/decision_t_reg_car/assets/67944253/26309ff7-b807-4764-a5f3-81f341ccd927">

### Removing Outliers for "odometer"

<img width="1033" alt="Screenshot 2024-02-07 at 11 06 10 AM" src="https://github.com/Shanephear/decision_t_reg_car/assets/67944253/a5514378-ba8c-481f-ba73-dcadd28638b0">

### Removing Outliers for "Year"

<img width="1067" alt="Screenshot 2024-02-07 at 11 07 06 AM" src="https://github.com/Shanephear/decision_t_reg_car/assets/67944253/73110e18-6c14-42af-89e1-cb548a15f685">

## Enhancing Data Quality

* Conducted a thorough analysis of the dataset to identify the percentage of null values in each column.
* Dropped columns with null values of percentage less than 5%, namely 'title_status', 'fuel', 'transmission', 'model', and 'manufacturer', as they are unlikely to significantly affect the analysis outcome.
* Decided to drop the "Size" column as it contains 71% missing values, which renders it unsuitable for analysis purposes.
* Employed a data imputation technique for the remaining columns with missing values, namely 'drive', 'type', and 'cylinders'.

### Filling Missing Values with Imputation Techniques

* Utilized an approximation method to impute missing values in these columns. Specifically, if two out of three values were present, we looked for similar conditions in other rows and imputed the missing value with the value of the other row.
* Utilized HistGradientBoostingClassifier, a machine learning algorithm, to impute the remainder of the missing values in the dataset, resulting in a more comprehensive and accurate dataset for analysis.

<img width="1153" alt="Screenshot 2024-02-07 at 11 09 50 AM" src="https://github.com/Shanephear/decision_t_reg_car/assets/67944253/f34c36e4-ee05-490b-b9d9-48266ebea358">

## Data Exploration

### Price vs Other parameters

<img width="1175" alt="Screenshot 2024-02-07 at 11 12 08 AM" src="https://github.com/Shanephear/decision_t_reg_car/assets/67944253/107cc12e-1239-47ad-9188-f3bcda6267d5">

### Using Correlation Matrix

<img width="785" alt="Screenshot 2024-02-07 at 11 12 39 AM" src="https://github.com/Shanephear/decision_t_reg_car/assets/67944253/7f5bc641-1b0c-4eca-bb3d-4bdd9d1712b4">

## Observation

* As our goal is to predict the price(continuous variable), we decided to employ a regression model. We began with a correlation matrix and scatter plot analysis, but unfortunately did not identify any strong patterns or correlations between the features and price.

* Therefore, given the non-linear relationship between the target variable and features, we determined that a Decision Tree Regressor model would be a more suitable approach for our prediction task.

## Prediction Model

* Utilize the imputed dataset and remove the "Price" and "ID" columns.
* Divide the dataset into training and testing subsets.
* Construct the model utilizing the Decision Tree Regressor algorithm.
* Utilize the test data to predict the target variable, "Price."
* Evaluate the model's performance using metrics such as Mean Absolute Error, Root Mean Squared Error, and R^2 Score.

<img width="992" alt="Screenshot 2024-02-07 at 11 15 26 AM" src="https://github.com/Shanephear/decision_t_reg_car/assets/67944253/6ec778da-76cb-4377-9562-dbaed2e351e5">


## Feature importance of the trained model

<img width="454" alt="Screenshot 2024-02-07 at 11 15 56 AM" src="https://github.com/Shanephear/decision_t_reg_car/assets/67944253/8a9e4311-2132-454e-a7e1-03d69720f8d0">

* This plot shows the relative importance of each feature in the model.
* Based on the graph, “year” “cylinder” “odometer” feature contribute more to the model's output, while features like “type” and “manufacturer” have less impact. 











