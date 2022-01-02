# stockpredictorfbprophet

Rough Background of Prophet Before Jumping Into the Task: 

Introduction: 

Prophet is a forecasting technique used for non-stationary data. Prophet is used by Meta (previously Facebook) to product forecasts for internal planning and budgeting. Meta is trying to democratise high quality forecasts. As forecasting is a specialised data science skill requiring experience, Prophet claims to enable even non-experts to quickly produce straightforward, reasonable, and accurate forecasts. 

Basic Maths Behind Facebook Prophet: 

The underlying function used by Facebook Prophet is complex and my limited understanding of math won't do it justice, so please do your own research as well. On a high level, this is the additive regression model: 
y(t) = g(t) + s(t) + h(t) + e(t)
Where: g = growth, s = seasonality, h = holiday, and e= error terms.
The growth term/function approximates the overall trend of the data. Prophet can automatically detect changepoints which highlight the start or end of growth trends, or you can manually set these changepoints yourself. To best capture growth you must identify the growth as linear (y=mx+b), logistic, or flat (i.e. the mean fluctuates around the same point throughout the series = stationary data)
The seasonality term is a Fourier Series as a function of time. Fourier Series are the sum of several sines and cosines. Each of these sine/cosines are multiplied by a coefficient. Summing these terms can approximate curves in the data; specifically seasonal or cyclical data in the case of Facebook Prophet. 
The holiday function allows Facebook Prophet to adjust forecasting when a holiday/ major event may change the underlying variable. Think earnings announcements, Christmas/New Years, any times when the stock market is closed). 

Pros: 

1.) Dealing with non-stationary data is a pain. Normally you have to "detrend" a non-stationary process to make it stationary; and then use this modified time series for prediction. There are several methods to detrending data. All of which have their pros and cons. For a deeper insight of the different methods please visit this page: https://stats.stackexchange.com/questions/82202/pros-and-cons-methods-for-detrending-time-series-data

2.) Fast, easy to use, and doesn't face the problem of missing values. Prophet forecasts are customisable in ways that make sense to non-data people. Non-experts can use Prophet to include impact of holidays, seasonality, and manually specifiy upper limits of growth curves (changepoints) allowing us to inject our own information about how the forecast will grow. 

Cons: 

1.) Users have to manually provide a list of important holidays. 

2.) A study by Lorenzo Menculini actually revealed the ARIMA model (Autoregressive Integrated Moving Average model) has better prediction power than Prophet. The study also revealed Prophet performed the poorest in terms of forecasts even when it used more data than other models. However, Menculini et al also revealed Prophet is useful for quick and dirty forecasts. 


Conclusion: 
As I'm just getting started, Prophet will be a good enough introductory exercise to forecasting time series. 


TASK: 

Background: 


At the beginning of Dec 2021, coffee prices were at a 10 year high. While there are a variety of reasons, bad weather and global supply constraints had the most substantial impact on the commodity's price. Brazil and Vietnam are two main coffee-producing countries. If there is damage in either of these countries, demand will outweigh supply. Recently Vietnam has experienced a higher than average number of Covid cases which has affected coffee harvesting & planting and Brazil (the world's largest Arabica coffee bean provider) has experienced extreme weather which has destroyed crops. This is colloquially referred to as "Frost". 

According to analysts, this is a multi-year issue. While the price of arabica coffee beans (known as premium coffee beans)is going up, there are cheaper alternatives. The robusta coffee bean is cheaper and is what instant coffee providers use. It is worth mentioning that arabica is sweeter and typically used in cappucinos and lattes, while Robusta is used in espressos and instant coffees (much less popular drink choices). However, the underlying supply problem is still relevant: while arabica's price has spiked ~80% this year, robusta's price also increased by ~50%.

While I want to eventually predict the price of coffee, I wanted to start smaller. Because my eventual goal is to predict the price of arabica coffee using machine learning, I wanted to start with predicting the price of a major coffee retailer. I chose Starbucks because that was the most recent coffee shop I visited. 


Obejctive: 

USE PROPHET TO PREDICT THE PRICE OF STARBUCKS CORP (Nasdaq Ticker: SBUX).  

Sources: https://facebook.github.io/prophet/ ; https://stats.stackexchange.com/questions/82202/pros-and-cons-methods-for-detrending-time-series-data; https://towardsdatascience.com/time-series-analysis-with-facebook-prophet-how-it-works-and-how-to-use-it-f15ecf2c0e3a; https://research.facebook.com/blog/2017/02/prophet-forecasting-at-scale/; https://arxiv.org/abs/2107.12770; https://www.investopedia.com/investing/best-coffee-stocks/; https://www.bloomberg.com/news/articles/2021-11-20/coffee-prices-are-climbing-and-roasters-are-switching-beans. 
