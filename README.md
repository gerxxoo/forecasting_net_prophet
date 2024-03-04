# forecasting_net_prophet

BACKGROUND
You’re a growth analyst at MercadoLibre. With over 200 million users, MercadoLibre is the most popular e-commerce site in Latin America. You've been tasked with analyzing the company's financial and user data in clever ways to make the company grow. So, you want to find out if the ability to predict search traffic can translate into the ability to successfully trade the stock. 
Instructions:
Step 1: Find unusual patterns in hourly Google search trafficStep 
2: Mine the search traffic data for seasonalityStep 
3: Relate the search traffic to stock price patternsStep 
4: Create a time series model with ProphetStep 
5: (optional): Forecast revenue by using time series models
The following section details these steps.


PROJECT
The project begins by installing and importing all the necessary libraries and dependencies. The first file I worked with is a csv containing Mercado's hourly search trends. I made sure the data frame is usable and then plot the month of May as a test. Then I compare the May figures to the median of the rest of the data frame. May resulted with higher search traffic than the median. 

In step two, I measured seasonality in the search trends. I found the beginning of the week has higher search traffic, and a heatmap demonstrated midnight was when users were most active. 

In step three, I related the search traffic trends to the stock price patterns. After importing the csv with stock data and making a data frame with closing prices, I concatenated this data frame with the one containing search trends. I added stock volatility to the data frame by calculating standard deviation over a four-day rolling window and the hourly stock return using the 'pct_change' function. I also added a column with a one-day lag. I created a correlation matrix between the lagged data, volatility, and hourly stock return and found there was a very low correlation among all these factors. 

In step four I created a time series model with Prophet. I set up the search trend data for the model, fit the data, and got a forecast for approximately eighty days. The forecast demonstrated a rapid increase in search traffic over the first 3/4 of the horizon but a sharp drop in the last 1/4. The components plot was very useful. I found that Tuesday through Thursday contained the highest projected traffic. There was high porjected traffic in the first quarter of the year, June, and the holidays, while the worst month was October. Traffic was low at about 8AM and steadily climbed to its peak at midnight before it dropped sharply again. 

The last step was a forecast of revenue using Prophet as well. I imported the csv, plotted it, and prepared the data for the Prophet model. After I fitted and forecasted the data, I found the components of this forecast. The most important part is finding that revenue peaks on Wednesdays and is at its lowest on Saturdays. The sales forecast predicts base case, worst case, and best case sales of 969.61, 887.25, and 1,050.42, respectively.

Ultimately, there isn't a strong enough correlation among the data to accurately predict the stock price. 


CODE SOURCE
The cpde was sourced from the classwork assignments. 


TECHNOLOGIES
This project required the use of pystan, Prophet, hvplot, holoviews, pandas, datatime, and matplotlib. The project was completed on a jupyter notebook on Google Colab using Python programming langauge. 
