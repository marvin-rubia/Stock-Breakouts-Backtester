# Python Backtester for Stock Breakouts
The Colab Notebook contains the function I developed for coding the profitability of breakout setups for a given stock in its entire history. Yahoo Finance is the source of the stock data, which were scraped using the `yahoo-fin` open-source library. The function's output is a histogram of the breakout profits and some trading probabilities that can be used to calculate **expected profit**.

## Sample Output
Using my `breakout_profitability(ticker)` function, here is the output for Apple Inc. (ticker = AAPL):

![image](https://github.com/marvin-rubia/Stock-Breakouts-Backtester/assets/140475770/1641ce40-5e1c-479e-94da-36db5122faa4)

In addition to this histogram, the function also outputs supplementary information:
"Additional Info: The first breakout for AAPL was observed on 1982-10-06 while the most recent breakout was on 2022-10-28. The average positive profit is 17.42% while the average negative profit (from false breakouts) is -6.16%."

## Conditions for a Breakout Candle
The function considered a candle as a breakout candle if:
- It is a green candle;
- Its body is longest in 10 days;
- Its body is at least 100% higher than the 20-day moving average;
- Its selling pressure (i.e. distance between High and Close) is 40% or lower than the length of the body; and
- Its volume is at least 50% higher than the 20-day moving average.

NOTE: The number of holding days is a maximum of 10 days. The Buy Price is the Close of the breakout candle, the ideal Sell Price is the highest price within 10 days, and the Stop Loss Price is the Open of the breakout candle. 

## Stock Breakout Example:
In trading, a breakout is a signal for buying. Strong price and volume actions accompany a breakout candle. Look at the following example of a breakout setup for AAPL in November 2021.

![image](https://github.com/marvin-rubia/Stock-Breakouts-Backtester/assets/140475770/11ad8f40-980b-4237-88f7-59b2095e8e9e)

## I wrote a blog about this
If you want to understand my thought processes for developing the function, read my article here: [Coding a Backtester for Stock Breakouts in Python](https://python.plainenglish.io/coding-a-backtester-for-stock-breakouts-in-python-a21dc61c81ff).

