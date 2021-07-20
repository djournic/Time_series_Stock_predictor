# The Capstone Project

Welcome to my Capstone Project at the Flatiron School. This is the last project, and hopefully the best, so let's get into it.

Retail investors are a huge fad these days. And fad or not, they are here to stay. Pretty much everyone and their cousin knows about the Gamestop/Wall Street Bets drama that took place months ago. Companies like Robinhood began offering commission-free trading, and now almost all brokers do it. Millions of new investors are trying to make some quick cash.

The problem is, researching stocks is hard. Especially if you're looking at options trading, since those are far more influenced by the news of the day, and odd, unpredictable elements. And most investors just don't want to put in the work.
Enter KISSSS: Keep It Simple Stock Selector (the last 'S' is a typo). Where I'll use some simple time forecasting techniques to predict which of 4 stocks entered by the user stands the gain the most.
This is similar to my Phase 4 project where I did some time forecasting on real estate data. One of the main lessons I've learned from the project, at least with ARIMA, the train-test split matters. So the first notebook is basically me trying to find the best train -test split to use with Auto ARIMA.
The next notebook is where I play around more with Prophet, from Facebook. This library served me very well on the previous project, and I wanted to stick with it. There was no real need for various train-test splits, at least not in the forecasting side of things. Prophet only cares about that when it comes to cross validation.
Also prominently featured in both of these notebooks is the Yahoo Finance library. This is instrumental to the app working. This is what gathers the stock data we need for the modeling.
The data cleaning aspect of this project was very simple for the ARIMA section, and a little more complicated for the Prophet. But overall, writing the functions to automate the process was a piece of cake.