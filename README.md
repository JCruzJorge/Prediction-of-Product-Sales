# Prediction of Product Sales

- Jorge Cruz ([GitHub Profile]# Prediction of Product Sales

**Author:** Jorge Cruz

## Table of Contents

- [Project Overview](#overview)
- [Data](#data)
- [Method](#method)
  - [1. Exploratory and Explanatory Data Analysis](#1-exploratory-and-explanatory-data-analysis)
  - [2. Regression Model](#2-regression-model)
  - [3. Model Evaluation](#3-model-evaluation)
- [Conclusion](#conclusion)
- [Recommendations](#recommendations)
- [Limitations](#limitations)


## Project Overview

The primary objective of the Sales Prediction Project is to use regression models to provide precise and dependable predictions of sales. The main focus of this project is on regression models, specifically linear regression and random forest regression. This choice of models highlights the aim of developing predictive tools that can effectively analyze the complex connections between different factors, including product attributes, outlet characteristics, and historical sales data. By conducting thorough exploratory data analysis, our objective is to gain a comprehensive understanding of the complexity of the information, discern patterns and trends, and ensure the data is cleansed to facilitate trustworthy analysis. The project aims to enhance capabilities in accurately predicting sales patterns through the use of regression models.

## Data
The dataset used in this project contains information about items, outlets, and corresponding sales data. It consists of 8523 observations and 12 Features. The variables included in the dataset are as follows:


| Variable Name             | Description                                                  |
|---------------------------|--------------------------------------------------------------|
| Item_Identifier           | Unique identifier for each product                          |
| Item_Weight               | Weight of product                                           |
| Item_Fat_Content          | Product fat content type                                    |
| Item_Visibility           | Product visibility                                          |
| Item_Type                 | Product category                                            |
| Item_MRP                  | Maximum Retail Price                                        |
| Outlet_Identifier         | Store ID                                                    |
| Outlet_Establishment_Year | Store establishment year                                   |
| Outlet_Size               | Store size                                                  |
| Outlet_Location_Type      | Store location type                                         |
| Outlet_Type               | Store type                                                  |
| Item_Outlet_Sales         | Product sales (target variable)   

The objective is to build predictive models that accurately estimate sales based on these attributes.

## Method
### 1. Exploratory and Explanatory Data Analysis
The initial phase involves exploring the dataset to understand its structure, identify patterns, and detect any anomalies. EDA and ExDA help us visualize relationships between variables, discover trends, and prepare the data for modeling. This phase guides feature selection, and engineering, and prepares us for model construction.

 - During the exploratory data analysis, a boxplot and histogram was visualized for each numeric datatype column. 
    - Also, a barplot was visualized for each categorical column. 
    - This gave a good baseline for all of the numeric and categorical columns for univariate EDA.

![Unknown](https://github.com/JCruzJorge/Prediction-of-Product-Sales/assets/139515726/dde5a519-6de2-483a-808e-7d7b28b622c9)

- Here we can see the quantity of different store sizes.

![Unknown-3](https://github.com/JCruzJorge/Prediction-of-Product-Sales/assets/139515726/b7063070-a528-4303-9a73-7ee4b1a456b6)

- This histogram shows that there's a major differece in weight and a large quanity of low weighing items.

- ![Unknown-4](https://github.com/JCruzJorge/Prediction-of-Product-Sales/assets/139515726/b23b9a08-75fc-4815-a6cf-d81f32a4a525)

- Here we can clearly see that in the barplot there's several outliers in the Outlet Establishment Year column. These could be valid data points, or they could be an error among the dates.

- Data shows that it's median is around the late 1990's is when more stores opened.

![Unknown-5](https://github.com/JCruzJorge/Prediction-of-Product-Sales/assets/139515726/2cba29c2-ad60-416d-9278-f6588ce7d4ab)

- Here we can see that the median of sales is roughly around 1800-1900 in sales.

- We can also see that there are higher some values higher in price and low in sales but does seem valid.

  ## Visualizing with Plots

![Unknown-6](https://github.com/JCruzJorge/Prediction-of-Product-Sales/assets/139515726/8b086a09-343b-421a-992b-61cd5f2b2787)

- Here in this graph we can see that most of the stores sales are Fruits and Vegetables.

- Also we can see the least sold product which is Seafood.

![Unknown-7](https://github.com/JCruzJorge/Prediction-of-Product-Sales/assets/139515726/80c9b624-03f1-4761-bb9e-07f3ba2423eb)

- This graph shows the number of stores opened during certain years.


#### Univariate Analysis
Univariate analysis involved exploring individual features. The analysis included histograms to visualize the distribution of numerical variables such as `Item_Weight` and `Item_MRP`. Boxplots were used to identify potential outliers in these variables. Count plots provided insights into categorical variables such as `Item_Fat_Content`, `Item_Type`, `Outlet_Size`, and `Outlet_Type`. 

-------------------

#### Multivariate Analysis
Multivariate analysis aimed to identify relationships between pairs of variables. A correlation heatmap was generated to visualize the correlations among numerical features. This helped in identifying potential collinearities and understanding variable interactions. Regression plots were also used to examine the relationship between numerical variables and the target variable `Item_Outlet_Sales`.

![Unknown-8](https://github.com/JCruzJorge/Prediction-of-Product-Sales/assets/139515726/25d868e0-3509-46d8-bb87-382cf65d96f0)

- Here we can see all the data complied and how each column correlates with one another.

---------------

#### Feature Inspection
Feature inspection involved examining the features' distributions and characteristics. This step was crucial in identifying potential anomalies, patterns, and understanding the data's nature.

The types of analysis chosen were justified by their ability to provide a comprehensive understanding of the data's characteristics, distributions, and relationships. These insights guided feature engineering and selection for model development.

### 2. Regression Model

In the regression modeling phase, two primary regression models are considered: Linear Regression and Random Forest Regression. The Linear Regression model assumes linear relationships, while the Random Forest Regression can capture complex interactions between variables. Hyperparameter tuning is applied to the Random Forest model to optimize its performance and enhance its predictive capability.

### 3. Model Evaluation

The performance of the developed models is rigorously evaluated using various metrics, including R-squared, Mean Absolute Error (MAE), Mean Squared Error (MSE), and Root Mean Squared Error (RMSE). These metrics provide insights into the accuracy of the models' predictions and their ability to generalize to new data. Comparisons between training and test data shed light on potential overfitting or underfitting issues.

Here are the key metrics for the three models:

| Model                    | R-squared   | MAE       | MSE         | RMSE      |
|--------------------------|-------------|-----------|-------------|-----------|
| Linear Regression        | 0.561       | 847.325   | 1300023.710 | 1140.186  |
| Default Random Forest    | 0.540       | 781.355   | 1269309.504 | 1126.636  |
| Tuned Random Forest      | 0.603       | 728.453   | 1096307.534 | 1047.047  |

#### Key Insights
- The Tuned Random Forest model outperforms both the Linear Regression and Default Random Forest models in all metrics.
- The Tuned Random Forest model's R-squared value of 0.603 suggests it can explain around 60.3% of the variability in sales.
- The lower MAE, MSE, and RMSE values of the Tuned Random Forest model indicate its predictions are closer to actual sales values.
- The Tuned Random Forest model offers a promising solution for accurate sales prediction, beneficial for business decisions.

## Conclusion

The final model chosen for deployment is the tuned Random Forest Regression model. After hyperparameter tuning, this model demonstrated improved performance on both training and test data compared to the default Random Forest and Linear Regression models. The tuned model strikes a balance between capturing complex relationships and avoiding overfitting.

The primary business problem is predicting sales accurately to support decision-making and resource allocation. The metrics collectively indicate that the tuned Random Forest Regression model is capable of providing reasonably accurate sales predictions, which can assist businesses in making informed decisions.

## Recommendations

Based on the analysis and model performance, the following recommendations can be made:

- **Utilize the Tuned Random Forest Model:** The tuned Random Forest model has demonstrated superior predictive performance compared to other models. It is recommended for accurate sales predictions and informed decision-making.

- **Continuous Data Collection:** Collect and incorporate more recent sales data to further enhance the model's predictive capabilities and adapt to changing sales trends.
  
- **Feature Engineering:** Explore advanced feature engineering techniques to capture more nuanced relationships between features and sales.
- **Ensemble Methods:** Experiment with ensemble methods like stacking and boosting to further enhance model performance.

  
## Limitations

Despite the success of the models, there are certain limitations:

- **Feature Availability:** Some features, such as item demand trends or external economic factors, might not have been included in the dataset. Incorporating these features could potentially improve prediction accuracy.

- **Assumption of Stationarity:** The models assume that sales patterns remain consistent over time. If significant shifts in consumer behavior occur, the models may need recalibration.

For more details, refer to the [Jupyter Notebook](Prediction_of_Product_Sales.ipynb).


## Contributors

- Jorge Cruz ([GitHub Profile](https://github.com/leratomatlala1)))
