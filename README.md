# Forecasting Monthly Shampoo Sales in Hair Haven


# 1.Business Understanding


Hair Haven operates in the competitive market of hair care products, specializing in shampoos. To thrive in this dynamic industry, Hair Haven needs to implement a robust forecasting system to anticipate and adapt to changes in customer demand, market trends, and external factors.



By implementing a comprehensive forecasting strategy, Hair Haven can navigate the complexities of the hair care market, optimize operations, and stay ahead in an ever-changing industry. The insights gained from accurate monthly sales forecasts will empower the company to make data-driven decisions, enhance customer satisfaction, and achieve sustainable growth.


# 1.1.Objectives


The primary goal of this project is to provide a forecast for the next 4 months of sales for the Hair Haven brand and report the findings.

Specific Objectives:



1.To forecast sales using time series modellling.



2.To do exploratory data analysis on the data



3.To Utilize time series analysis techniques to identify underlying patterns, trends, and seasonality in the monthly sales data.



4.To Build a time series predictive model that can forecast real estate prices.



5.To Evaluate the forecasting model performance by comparing its predictions against actual sales.


# Your Task: Forecasting Monthly Shampoo Sales using Time Series Modelling


# 2.Data Understanding


The provided dataset represents monthly sales data for the Hair Haven shampoo brand. Each row corresponds to a specific month, and the associated monthly sales figures are given. Let us break down the key aspects of the data:


Time Period: The data spans from January 2008 to September 2013, covering multiple years. This extended time period allows for the identification of seasonal patterns and trends.


Monthly Sales: Monthly sales figures are provided in the "Monthly Sales" column.Sales figures vary from month to month, reflecting the dynamic nature of the hair care product market.


# 3.Data Preparation


In this section, we are going to do several actions to prepare our data for exploratory data analysis and modelling. First, we will import all the necessary libraries, load the dataset using pandas library, preview the data, do exploratory data analysis, conduct data preprocessing and determine Trend, Seasonal, and Error components by decomposition.


Following EDA Analysis:

Time Series Plots of Sales Amount shows general movement of sales data. The monthly sales amount of the company is generally increasing over the time. There seems to be a trend (increasing).

Yearly box plot suggests that series has a significant trend. Sales is increasing then reduces in the year 2013, the presence of outliers in this year may represent months with exceptionally high sales compared to the typical pattern.

Monthly box plots suggests that we have a seasonal component each year. Also, we see that there are no outliers present.

As seen from plotting quarterly sales across years, Q4 has the highest sales. After that Q3, Q1 then Q2 has lowest sales.

Plotting sales for every year shows that the average monthly sales generally increases every year then there is a slight decrease in the year 2013.


Train & Test records:


In preparation for construction of a predictive models, we filter out the last 4 records (from 2013-06-01 to 2013-09-30), as a holdout sample so that we can check the accuracy of my model to forecast predicted values against the actual values.


Determining Trend, Seasonal, and Error components:

The decomposition plot shows our time series broken down into its three components: trend, seasonal and the error. Each of these components makes up our time series and helps us confirm what we saw in our initial time series plot.

The Trend line confirmed that there is an upward trending.

The Seasonality subplot shows that the regularly occurring spike in sales each year changes in magnitude, ever so slightly. Our dataset definitely contains seasonality, and this suggests that any ARIMA models used for analysis will need seasonal differencing. The change in magnitude suggests that any ETS models will use a multiplicative method in the seasonal component.



The Error plot of the series presents a fluctuations between large and smaller errors as the time series goes on. Since the fluctuations are not consistent in magnitude then we will apply error in a multiplicative manner for any ETS models.


# 4.Modelling


Build the forecasting Models:


In the previous section, we analyzed the decomposition graphs to inform forecasting models on the business problem. In this section, we determine the appropriate measurements to apply to the ETS model, the (Seasonal) ARIMA, ARMA, ARIMA models. Then we compare the models based on in-sample errors.

1. ETS Models

  2.Seasonal ARIMA

3. ARMA Model

4. ARIMA Model



In Time Series Analysis, we should start the analysis with a "stationary" data. make the data stationary. As the decomposition plots exhibit, the provided dataset seems to have seasonality and linear Trend. Augmented Dickey Fuller test reminds us the fact that the given data is not stationary.



# 5.Evaluation


In this section we describe the in-sample errors based on ETS models. The in-sample error measures give us a look at how well our model is able to predict future values. Among the various Error Terms chosen:

RMSE (Rooted Mean Squared Error)


MAE (Mean Absolute Error)


MAPE (Mean Absolute Percentage Error)


MASE (Mean Absolute Scaled Error)




We also check the AIC and BIC values. The Akaike Information Criterion (AIC) and Bayesian Information Criterion (BIC) are used to compare the relative goodness of fit of statistical models. Lower AIC and BIC values indicate a better fit.



After we analyze the training part of time series data using ETS Models , Seasonal ARIMA, ARMA and ARIMA. Then we compare the performance of each model with In-Sample Error Measures such as RMSE, MAPE and MASE. When comparing the in-sample error measures we used, the ETS model does have a much narrower standard deviation(RMSE) compared to other models. Though the MASE value of ETS model is lower than that of Seasonal ARIMA and ARMA they are below 1.00, the generally accepted MASE threshold for model accuracy.



Based on the AIC and BIC values, the SARIMA model appears to be the most suitable model among the ones considered. It has the lowest AIC and BIC, suggesting a better trade-off between goodness of fit and model complexity.

Next, we compare the prediction performance of both models using holdout samples.


Predicting the Holdout Sample:


When looking at the model's ability to predict the holdout sample, we can recognize that the Seasonal ARIMA model shows better predictive performance in all metrics.


Forecast for the next 4 months of Sales:


Previously, we concluded that the Seasonal ARIMA model shows better performance in terms of prediction. Now, we forecast for the next four-month sales using all the time series data based on the same Seasonal ARIMA model. First, we diagnose the stationarity of the whole time series data again. Then the forecast results are calculated using 95% and 80% confidence intervals.


# Summary


This analysis is mainly about forecasting for upcoming sales in a Shampoo Company. Firstly, we investigate and prepare the time series data. The provided data was appropriate to use time series models and we held out the last 4 periods of data points for validation. Then, we determined Trend, Seasonal and Error components in the data based on decomposition plots. After that, we analyse the data by applying the ARMA, ARIMA, SEASONAL ARIMA and ETS models and describe the errors for the models. We compared the in-sample error measurements to the models,also compared their aic and bic values and compared error measurements for the holdout sample in the forecast. Finally,we choose the best fitting model and forecast the next four periods.
