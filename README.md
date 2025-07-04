# 📈 Retail Demand Forecasting Using ARIMA

This project is part of the **CodeClause Internship** and focuses on applying time series analysis techniques to forecast product demand using the **ARIMA model**. The forecasting helps businesses make informed decisions for **inventory planning** and **supply chain management**.

---

## 📌 Objective

The main goal of this project is to analyze historical retail sales data and forecast future demand using the **ARIMA (AutoRegressive Integrated Moving Average)** model. This helps businesses anticipate product requirements and reduce understock or overstock situations.

---

## 📁 Dataset Description

The dataset used in this project contains **over 169,000 retail sales records** with the following key features:

- `date` : Date of the order  
- `Order_Demand` : Quantity of product ordered  
- `Product_Code` : Unique product identifier  
- `Warehouse` : Location of product storage  
- `Product_Category` : Category of the item  
- `Promo` : Whether the product was on promotion  
- `State_Holiday` : Indicates public holidays  
- `School_Holiday` : Indicates school closures  
- `Petrol_Price` : External economic factor  

---

## 🔍 Exploratory Data Analysis (EDA)

- Removed **null values** and **duplicates**  
- Converted `Order_Demand` to positive integers (absolute values)  
- Transformed `date` column into datetime format  
- Aggregated data by daily order demand  
- Visualized demand trends to detect seasonality and outliers  

### 📊 Total Daily Demand Over Time


![image](https://github.com/user-attachments/assets/8771c2bd-44f3-42bb-96bd-55550f52f885)


> A clear view of fluctuations and seasonal patterns in product demand throughout the year.

---

## ⚙️ Preprocessing

- Aggregated the dataset to daily totals for time series modeling  
- Checked and enforced stationarity using:  
  - **Augmented Dickey-Fuller (ADF) Test**  
  - Differencing the time series for stationarity if needed  
- Scaled and cleaned the data where necessary  

---

## 🧪 Time Series Modeling (ARIMA)

- Performed **time series decomposition** to extract:  
  - **Trend**  
  - **Seasonality**  
  - **Residuals**  

### 📉 Decomposition of Time Series


![image](https://github.com/user-attachments/assets/0aa25ce1-2690-4898-995a-0030808398ee)



> The decomposition shows the trend, seasonal cycles, and residuals clearly, supporting further ARIMA modeling.

- Confirmed stationarity with:  
  - ADF Statistic = -8.09  
  - p-value = 1.33e-12 → ✅ **Series is stationary**  
- Chose **ARIMA(1,1,1)** based on exploratory analysis  
- Trained ARIMA model on complete historical data  

---

## 🔮 Forecasting

- Forecasted demand for the **next 30 days**  
- Visualized forecast vs actual trend  
- Evaluated performance using Root Mean Squared Error (RMSE)

### 📅 30-Day Demand Forecast Plot


![image](https://github.com/user-attachments/assets/ab894241-311d-4d06-9d4c-c5684e389271)



> The red line represents predicted values, showing how ARIMA forecasts upcoming demand based on past patterns.

```txt
RMSE: 2,387,893.62
