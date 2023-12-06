# car-price-prediction
Data science project for car price prediction using machine learning algorithms and exploratory data analysis. This project was first done on my kaggle profile.

Libraries: 
  1. pandas
  2. numpy
  3. matplotlib
  4. sklearn
  5. seaborn

## 1. Familiarize and prepare the data

The project starts with a segment dedicated to understanding and familiarizing ourselves with the data. In this phase, we import the data into a pandas DataFrame, rename its column names, and verify and rectify the data types. Additionally, we explore the data, identifying null values and outliers. Subsequently, we partition the data into training and test sets, allowing us to conduct exploratory data analysis exclusively on the test set.

<img src='/figures/df_info.png' alt='info of the dataset columns' title='nfo of the dataset columns' style='width: 300px'> <img src='/figures/histograms.png' alt='Histograms for the numeric columns' title='Histograms for the numeric columns' style='width: 500px'>
<img src='/figures/nulls.png' alt='Null values in the levy column' title='Null values in the levy column'>

## 2. Exploratory Data Analys

In this section, we conduct a thorough exploratory data analysis, delving deep into the dataset to gain insights and uncover interesting relationships between variables. Throughout this phase, we generate a variety of high-quality data visualizations to effectively communicate our findings.


To view all the visualizations, please refer to the project's notebook.
<center>
<img src='/figures/correlations.png' width='70%'>
</center>
<img src='/figures/brands.png' width='100%'>
<img src='/figures/levy_vs_price.png' width='100%'>
<img src='/figures/engine_and_turbo.png' width='100%'>
<img src='/figures/models.png' width='100%'>

## 3. Creating a machine learning model
Within this section, we begin our journy creating a machine learning model to predict the car's prices. 
We initiate the creation of a data preprocessing pipeline using both scikit-learn's transformers and custom ones, adhering to the scikit-learn interface. The main steps for this task are: 
1. Handle infrequent clases.
2. Encode categorical features with the OneHotEncoding strategy.
3. Handle outliers.
4. Impute null values.
5. Scale the data.

<img src='/figures/pipeline.png' width='300px'>

To select the model, we tested 4 different machine learning algorithms: K Neearest Neighbors Regressor, Support Vector Machines Regressor, Random Forest Regressor and Linear Regressor (using Stockastic Gradient Descent). After this, we selected the Random Forest Regressor and performed a hyperparameter-tunning usning scikit-learn's GridSearchCV.

<img src='/figures/models.png' width='100%'>


Finally, after evaluating our model using k-fold cross validation (10 folds) and studying it's learning curves, we tested our model with the test test, obtaining a performance of:

* **RMSE: $5282**
* **MAE: $3101**
* **MAPE: 71.88%**
* **R2: 0.79**

## 4. Conclusions

1. During EDA, we notice some missing/null values, as well as outliers due to incorrect data.
2. We performed Data Visualization to gain some insights and answar some questions like the brands and models with most used cars in the market, their average prices, use of leather interior by different manufacturers, and much more, which can be used later for storytelling.
3. We create a full preprocessing pipeline to prepare the data for machine learning models, using both sklearn's and created transformers, which included category encoding, handling outliers, imputation of null values, and scaling.
4. We selected a model for the regression task, and performed hyperparameter tunning.
5. We evaluated the model using different metrics and check for bias/variance using learning curves, detecting a high variance which can be improved by increasing the train size.

6. We proposed a final model with an RMSE of 5286, a Mae of 3090 and R2 of 0.79.
