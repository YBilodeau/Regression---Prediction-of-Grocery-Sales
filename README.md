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
- **Item_Weight Weight:** of product
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
**Sales by Outlet Identifier**
![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/e5be04ca1f91850eaf079e10bbd3141cc01f05aa/Images/Sales_by_Outlet_Identifier.png)

**Average Oulet Sales by Outlet Size**
![image](https://github.com/YBilodeau/Regression-Prediction-of-Grocery-Sales/blob/841f56132a8ad6645443d11d75d852c216ed91ca/Images/Average%20Outlet%20Sales%20by%20Outlet%20Size.png)
