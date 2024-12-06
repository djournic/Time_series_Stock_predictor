# The Stock Selection Project


Retail investors are a huge fad these days. And fad or not, they are here to stay. Pretty much everyone and their cousin knows about the Gamestop/Wall Street Bets drama that took place months ago. Companies like Robinhood began offering commission-free trading, and now almost all brokers do it. Millions of new investors are trying to make some quick cash.

![alt text](https://upload.wikimedia.org/wikipedia/en/f/f0/WallStreetBets.png)

## The Business Problem:
   Most retail investors don't know what a P/E ratio is, or EBITA, or what 'Trading above 3 times valuation' means. They want a simple, quick answer to "Which stock should I buy?". That's what I'd like to solve here with some simple time forecasting.
Like I mentioned before, researching stocks is hard. Especially if you're looking at options trading, since those are far more influenced by the news of the day, and odd, unpredictable elements. And a lot of investors just don't want to put in the work.
Enter KISSSS: Keep It Simple Stock Selector (the last 'S' is a typo). Where I'll use some simple time forecasting techniques to predict which of 4 stocks entered by the user stands the gain the most.
This is similar to a previous project where I did some time forecasting on real estate data. One of the main lessons I've learned from the project, at least with ARIMA, the train-test split matters. So the first notebook is basically me trying to find the best train -test split to use with Auto ARIMA.
The next notebook is where I play around more with Prophet, from Facebook. This library served me very well on the previous project, and I wanted to stick with it. There was no real need for various train-test splits, at least not in the forecasting side of things. Prophet only cares about that when it comes to cross validation.

![alt text](https://i.kym-cdn.com/entries/icons/original/000/029/959/Screen_Shot_2019-06-05_at_1.26.32_PM.jpg)

## The Data:
For testing the various splits, I need stock data to test with, so I found the following:
S&P 500 stocks: https://datahub.io/core/s-and-p-500-companies
NASDAQ: https://datahub.io/core/nasdaq-listings
Dow Jones: https://www.money-zine.com/download/dow-jones-industrial-average-components.xls
Also prominently featured in both of these notebooks is the Yahoo Finance library. This is instrumental to the app working. This is what gathers the stock data we need for the modeling.
The data cleaning aspect of this project was very simple for the ARIMA section, and a little more complicated for the Prophet. But overall, writing the functions to automate the process was a piece of cake. Although the NASDAQ csv I got was 3 years old, so many of the stocks in that file are not in the NASDAQ any more. So I had to clean that up and remove all the delisted stocks. Then save that for future use. However I hashed out that code , again for future use.
## The Process:
There isn't a lot to optimize in modeling with ARIMA or Prophet, mostly just how much data to use for the model. So as I mentioned earlier, the first notebook is about trying out different train-test splits for ARIMA modeling, using the Mean Absolute Error as the primary metric to evaluate the model. After running a number of stocks from the Dow, NASDAQ and S&P 500 through various combinations of train-test splits, there was no clear winner on the training length. However, test length was another story: 7 days was by far the best value. Which was unfortunate because I wanted to do at least 14 days for the predictions.
The next notebook is where I try something similar with Prophet, from Facebook. Again there was a little more data cleaning needed to get the Yahoo Finance library data into Prophet useable format. Still, I wrote a few functions to streamline the process, and commenced testing.
Interestingly enough, while ARIMA seemed to work best with a 30/7 split, Prophet worked best with a 180/7 split. Which again, is unfortunate since I wanted to predict at least 14 days out.
The entire code is built off the Yahoo Finance library, which is fantastic, it has a lot of functionality. However, during the coding the library got updated and the new one wasn't working very well at the start. So then I turned to Tiingo, another stock history library; that's why there are those Tiingo folders in repo. However, they aren't completed as I was able to resolve the issues with the Yahoo library and continued onward.
## The Results:
As I mentioned earlier, neither model really worked best with the 2 week horizon I wanted. But overall Prophet worked better. Originally I wanted to use Mean Absolute Error as the main metric to evaluate, but I ended up using multiple metrics (which just goes to show you can't just look at one). Overall it looked likeProphet was better (but I kind of knew that going in).
The next step was to write the function, and that wasn't too difficult; and for a bare bones jupyter notebook function, it works just fine. In the future I'd like to make a Streamlit app, or even a mobile app, with a lot of bright colors and fancy buttons and all the bells and whistles.







