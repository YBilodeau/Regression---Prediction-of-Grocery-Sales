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

## **Explanatory Data Analysis**

### **Company**
- The company has 10 outlet stores.
- The first outlet store was opened in 1985, and the most recent in 2009.
- The company offers 1559 items across a total of 16 product category types.
- The total sales for the period was $18,591,125.41.

### **Outlets**
![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/0353675ed8116de305d344b7716d0184c18501ee/Images/Total%20Sales%20by%20Outlet.png)

- Outlet OUT027 significantly outperformed the other outlets with 3,453,926.05 dollars of total sales.
  - It is the only Supermarket Type3 outlet.
  
- Outlets OUT010 and OUT019 significantly underperformed the other outlets, having only 188,340.17 dollars and 179,694.09 dollars in total sales respectively.
  - These are the only Grocery Stores outlets.

#### **Outlet Types**

![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/0353675ed8116de305d344b7716d0184c18501ee/Images/Total%20Company%20Sales%20by%20Outlet%20Type.png)

![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/0353675ed8116de305d344b7716d0184c18501ee/Images/Average%20Outlet%20Sales%20by%20Outlet%20Type.png)

Outlet Type has a significant correlation with the Outlet Type's Average Outlet Sales.

- Supermarket Type1 outlets may have contributed the most to Total Company Sales, however they do not have the highest Average Outlet Sales.

- Supermarket Type3 has only only one outlet, and it has the highest Average Outlet Sales. There are (2) Grocery Store Outlet Types, and they have the least Average Outlet Sales of the Outlet Types.

#### **Outlet Size**
![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/0353675ed8116de305d344b7716d0184c18501ee/Images/Total%20Company%20Sales%20by%20Outlet%20Size.png)

![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/0353675ed8116de305d344b7716d0184c18501ee/Images/Average%20Outlet%20Sales%20by%20Outlet%20Size.png)

Outlet Size does have some correlation with the Outlet Type's Average Outlet Sales. It is noted however, that due to the high variance within each Outlet Size it may not be overly helpful in predicting an Outlet Type's Average Outlet Sales.

- Medium Size outlets contributed the most, and Small and Unknown Sized Outlets contributed the least to Total Company Sales.

- Though High Size outlets contributed a lessor amount than either Small or Unknown Size to Total Company Sales, their Average Outlet Sales were higher.

#### **Outlet Location Types**

![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/0353675ed8116de305d344b7716d0184c18501ee/Images/Total%20Company%20Sales%20by%20Outlet%20Location.png)

![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/0353675ed8116de305d344b7716d0184c18501ee/Images/Average%20Outlet%20Sales%20by%20Outlet%20Location%20Type.png)

Outlet Location Type does have some correlation with the Outlet Type's Average Outlet Sales. It is noted however, that due to the high variance within each Outlet Location Type it may not be overly helpful in predicting an Outlet Type's Average Outlet Sales.

- Tier 3 Outlet Location Types contributed the most to Total Company Sales.

- Though Tier 2  Outlet Location Types contributed a lessor amount than either Tier 3 to Total Company Sales, their Average Outlet Sales were higher.

### **Items**

![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/0353675ed8116de305d344b7716d0184c18501ee/Images/Total%20Sales%20Top%2010%20Items.png)

#### **Item Types**

![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/0353675ed8116de305d344b7716d0184c18501ee/Images/Total%20Company%20Sales%20by%20Item%20Type.png)

![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/0353675ed8116de305d344b7716d0184c18501ee/Images/Average%20Item%20Sales%20by%20Item%20Type.png)

Item Type does have a significant correlation with the Items Type's Average Outlet Sales.

- It is of interest to note that while the Seafood Item contrubutes the least to Total Conpany Sales, it has the highest Item Sales, this Item Type has the highest Average Outlet Sales.

- The Fruits and Vegetables Item Type contributed greatly to the Company Sales Total and had high Average Outlet Sales.

#### **Item Fat Content**

![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/0353675ed8116de305d344b7716d0184c18501ee/Images/Total%20Company%20Sales%20by%20Item%20Fat%20Content.png)

![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/0353675ed8116de305d344b7716d0184c18501ee/Images/Average%20Item%20Sales%20by%20Item%20Fat%20Content.png)

Low Fat Items contributed much more significantly to the Total Company Sales.

Outlet Fat Content does have some correlation with the an Item's Average Outlet Sales. Though the amount may not be overly helpful in predicting Item's Average Outlet Sales.

- Low Fat items may have contributed the more significantly to Total Company Sales than Regular items, however they do not have higher Average Outlet Sales.

## **Model Performance**

### **Mean Absolute Error (MAE)**
![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/7c96966fefb9f118019456d9348c80928f4f49a0/Images/MAE%20Formula.jpg)

MAE is the arithmetic average (mean) of the absolute errors ${\displaystyle |\hat{y}-y_i|}$, where ( $\hat{y}$ ) are the predicted values and ( $y_i$ ) are the true values.

**Advantages:**
- It prevents positive (+) and negative (-) errors from canceling out.
- It has the same units of measure as the target.

![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/1f0496ee44dd322e237d4cadab49adc9df53befa/Images/Model%20Performance%20MAE%20Scores.png)

### **Mean Squared Error (MSE)**
![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/7c96966fefb9f118019456d9348c80928f4f49a0/Images/MSE%20Formula.jpg)

MSE is the arithmetic average (mean) of the squared errors ${\displaystyle (\hat{y}-y_i)^2}$, where ( $\hat{y}$ ) are the predicted values and ( $y_i$ ) are the true values.

**Advantages:**
- It prevents positive (+) and negative (-) errors from canceling out.
- It punishes large errors.

**Disadvantages:**
- It does not have the same units of measure as the target.

![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/0353675ed8116de305d344b7716d0184c18501ee/Images/Model%20Performance%20MSE%20Scores.png)

### **Root-Mean Squared Error (RMSE)**
![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/7c96966fefb9f118019456d9348c80928f4f49a0/Images/RMSE%20Formula.jpg)

RMSE is the square root of MSE, and is probably the most-useful and a better metric than MAE, MSE, and RMSE.

**Advantages:**
- It prevents positive (+) and negative (-) errors from canceling out.
- It punishes large errors.
- It has the same units of measure as the target.
 
 ![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/0353675ed8116de305d344b7716d0184c18501ee/Images/Model%20Performance%20RMSE%20Scores.png)

### **Coefficient of Determination ( $R^2$ )**
![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/7c96966fefb9f118019456d9348c80928f4f49a0/Images/R2%20Formula.jpg)

**The Sum of Squared Errors (SSE) of the Models Predicted Values**:
$$\text{SSE of our Predictions } = \sum_i(y_i - \hat y_i)^2$$
**The Sum of Squared Errors (SSE) for the Mean Values**
 $$\text{SSE of the Mean } = \sum_i(y_i - \overline y_i)^2$$

**The $R^2$ Coefficient of Determination**  is the proportion (%) of the variation in the dependent variable, or target variable, that a model is able to predict, or explain, from the independent variables, or features. It is a measure of the goodness of fit of a regression model.  $R^2$ calculates how much better our model's predictions are vs if the mean was used instead. It should have a value between 0 and 1, however a poor model may have a negative $R^2$.

**Advantages:**
- It uses a consistent scale, which is used for all datasets, and thus may be used for comparison.

**Disadvantages:**
- It is difficult to interpret and very difficult to explain to non-technical audiences.
- A high $R^2$ doesn’t always mean a good model and a low score doesn’t always mean a bad one.  

![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/0353675ed8116de305d344b7716d0184c18501ee/Images/Model%20Performance%20R2%20Scores.png)
