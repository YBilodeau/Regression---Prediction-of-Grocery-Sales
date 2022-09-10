# Regression – Prediction of Grocery Sales
- **Author:** Yvon Bilodeau
- **Last updated:** August 2022
 
![image credit: rd.com/food/](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/703c4210d50e9f2e81cd4ccdf3ccdca936cb35c1/Images/Grocery_Produce.jpg)

## **Project Desciption**
### **Overview**
The data scientists at BigMart have collected 2013 sales data for 1559 products across 10 stores in different cities. Also, certain attributes of each product and store have been defined. The aim is to build a predictive model and predict the sales of each product at a particular outlet.

Using this model, BigMart will try to understand the properties of products and outlets which play a key role in increasing sales.

### **Data Source**
The data was sourced from [analyticsvidhya.com](https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/)

There are 8523 rows, and 12 columns.
The rows represent 8523 observations, and the columns represent 11 features and 1 target variable.

### **Data Dictionary**
- **Item_Identifier:** Unique product ID
- **Item_Weight:** Weight of product
- **Item_Fat_Content:** Whether the product is low fat or regular
- **Item_Visibility:** The percentage of total display area of all products in store allocated to the particular product
- **Item_Type:** The category to which the product belongs
- **Item_MRP:** Maximum Retail Price (list price) of the product
- **Outlet_Identifier:** Unique store ID
- **Outlet_Establishment_Year:** The year in which store was established
- **Outlet_Size:** The size of the store in terms of ground area covered
- **Outlet_Location_Type:** The type of area in which the store is located
- **Outlet_Type:** Whether the outlet is a grocery store or some sort of supermarket
- **Item_Outlet_Sales:** Sales of the product in the particular store. This is the target variable to be predicted.

## **Exploratory Data Analysis**

![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/82e8f642fa4517278aa1ec6263fce5360bfec8aa/Images/Total%20Sales%20Top%2010%20Items.png)

![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/46afeebacc84ec51c349711eee0af7bb16c7b926/Images/Total%20Sales%20by%20Outlet%20Identifier.png)

![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/82e8f642fa4517278aa1ec6263fce5360bfec8aa/Images/Average%20Outlet%20Sales%20by%20Outlet%20Location%20Type.png)

![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/82e8f642fa4517278aa1ec6263fce5360bfec8aa/Images/Average%20Outlet%20Sales%20by%20Outlet%20Size.png)

![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/82e8f642fa4517278aa1ec6263fce5360bfec8aa/Images/Average%20Outlet%20Sales%20by%20Outlet%20Type.png)

## **Model Performance**

### **Mean Absolute Error (MAE)**
$$ \Large MAE = \frac{\sum_ {i=1}^{n} |y_{i} - \hat y_{i}|}{n}$$

To prevent a + error and - error from cancelling each other out, we take the absolute value of the errors before we sum them.

 MAE will still be in the same units as the original target.

On average, how off is the model's prediction from the true value?

![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/cd1871432fe8488a45b53fff69e3937e12a46ea4/Images/Model%20Performance%20MAE%20Scores.png)

### **Mean Squared Error (MSE)**
To prevent a + error and - error from cancelling each other out, we could also square the error (since a negative number squared becomes a positive number).

$$ \Large MSE = \frac{\sum_{i=1}^{n}(y_{i} - \hat y_{i})^2}{n}$$

Statisticians like MSE over MAE because it punishes larger errors more severely, we can square $y_{i} - \hat y_{i}$ instead of taking the absolute value.
Unlike MAE, MSE is no longer in the same units as the data, it is in units-squared. 

![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/2cdc26ca30daf3719b66f07ae7b23e0246988eaf/Images/Model%20Performance%20MSE%20Scores.png)

### **Root-Mean Squared Error (RMSE)**
To convert MSE back to the same units as the original target, we can take the square-root of the MSE to get the RMSE.

$$\Large RMSE = \sqrt{\frac{\sum_{i=1}^{n}(y_{i} - \hat y_{i})^2}{n}}$$

RMSE is probably the best/most-useful metric out of MAE, MSE, and RMSE.
 
![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/2cdc26ca30daf3719b66f07ae7b23e0246988eaf/Images/Model%20Performance%20RMSE%20Scores.png)

### **Coefficient of Determination (R2)**

 **The $R^2$ or Coefficient of determination is a statistical measure that is used to assess the goodness of fit of a regression model**

- Value should be between 0 and 1.
    - $R^2$ is the proportion (%) of the variance in our target that our model could explain.
    - $R^2$=0.8 means our model can explain 80% of the variance in our target.
    - If we have a REALLY BAD model, we may get a negative $R^2$



- The **Sum of Squared Errors (SSE)** for our Models **Predicted Values ($\hat{y}$) vs the true values ($y_i$)**: 
$$\text{SSE of our Predictions } = \sum_i(y_i - \hat y_i)^2$$

- The **SSE if we use the Mean as Our Prediction ($\bar{y}$) vs the true values  ($y_i$)**

 $$\text{SSE of the Mean } = \sum_i(y_i - \overline y_i)^2$$


- $R^2$ (R-Square) calculates how much better our model's predictions are vs if we just used the mean instead. 


$$ \large R^2 = 1 - \dfrac{\text{SSE of our Predictions}}{ \text{SSE of the Mean }}  $$

<br>

$$ \large R^2  = 1 - \dfrac{\sum_i(y_i - \hat y_i)^2}{\sum_i(y_i - \overline y_i)^2} $$

![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/2cdc26ca30daf3719b66f07ae7b23e0246988eaf/Images/Model%20Performance%20R2%20Scores.png)

## **Feature Importances**
![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/2cdc26ca30daf3719b66f07ae7b23e0246988eaf/Images/Feature%20Importance.png)
