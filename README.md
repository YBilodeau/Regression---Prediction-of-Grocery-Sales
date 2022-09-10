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
![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/7c96966fefb9f118019456d9348c80928f4f49a0/Images/MAE%20Formula.jpg)

MAE is the arithmetic average (mean) of the absolute errors ${\displaystyle |\hat{y}-y_i|}$, where ( $\hat{y}$ ) are the predicted values and ( $y_i$ ) are the true values.

**Advantages:**
- It prevents positive (+) and negative (-) errors from canceling out.
- It has the same units of measure as the target.

![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/cd1871432fe8488a45b53fff69e3937e12a46ea4/Images/Model%20Performance%20MAE%20Scores.png)

### **Mean Squared Error (MSE)**
![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/7c96966fefb9f118019456d9348c80928f4f49a0/Images/MSE%20Formula.jpg)

MSE is the arithmetic average (mean) of the squared errors ${\displaystyle (\hat{y}-y_i)^2}$, where ( $\hat{y}$ ) are the predicted values and ( $y_i$ ) are the true values.

**Advantages:**
- It prevents positive (+) and negative (-) errors from canceling out.
- It punishes large errors.

**Disadvantages:**
- It does not have the same units of measure as the target.

![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/2cdc26ca30daf3719b66f07ae7b23e0246988eaf/Images/Model%20Performance%20MSE%20Scores.png)

### **Root-Mean Squared Error (RMSE)**
![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/7c96966fefb9f118019456d9348c80928f4f49a0/Images/RMSE%20Formula.jpg)

RMSE is the square root of MSE, and is probably the most-useful and a better metric than MAE, MSE, and RMSE.

**Advantages:**
- It prevents positive (+) and negative (-) errors from canceling out.
- It punishes large errors.
- It has the same units of measure as the target.
 
 ![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/2cdc26ca30daf3719b66f07ae7b23e0246988eaf/Images/Model%20Performance%20RMSE%20Scores.png)

### **Coefficient of Determination (R2)**
![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/7c96966fefb9f118019456d9348c80928f4f49a0/Images/R2%20Formula.jpg)

- **The $R^2$ Coefficient of Determination** is a statistical measure that is used to assess the goodness of fit of a regression model. It should have a value between 0 and 1, however a poor model may have a negative $R^2$. $R^2$ is the proportion (%) of the variance in our target that our model could explain.
- The **Sum of Squared Errors (SSE)** of the **Models Predicted Values** ( $\hat{y}$ ) vs the **True Values** ( $y_i$ ): 
$$\text{SSE of our Predictions } = \sum_i(y_i - \hat y_i)^2$$
- The **Sum of Squared Errors (SSE)** for the **Mean Values** ( $\bar{y}$ ) vs the **True Values** ( $y_i$ ): 
 $$\text{SSE of the Mean } = \sum_i(y_i - \overline y_i)^2$$
- $R^2$ **Coefficient of Determination** calculates how much better our model's predictions are vs if we just used the mean instead. 

![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/2cdc26ca30daf3719b66f07ae7b23e0246988eaf/Images/Model%20Performance%20R2%20Scores.png)

## **Feature Importances**
![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/2cdc26ca30daf3719b66f07ae7b23e0246988eaf/Images/Feature%20Importance.png)
