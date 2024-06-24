
# Algorithm Trading using Python

This project covers the methods and ideas to create quantitative strategies in Python using real world company stocks.

For this project I tested stock prices of companies like : Apple, Microsoft, S&P 500, Coco-cola, Disney, IBM.

The data is extracted from Yahoo Finance library 

import yfinance as yf

stocks  = yf.download(ticker)


# Explorartory Data analysis

1. **Statistical analysis**: For the stocks in question, analysis was done to understand there annual mean return, annual variance and standard deviation.

For apple it was seen that the annual mean return was around 27% , with a standard deviation of ~30%

![APPLE variation range](https://github.com/aeshna25/Algorithm-trading-using-Python/assets/31938370/a0f86b0c-ab8f-4475-bd8e-694dfb3d0d42)

2. **Risk to reward ratio** : Risk to reward ratio is an important metric to understand which stocks are worth investing given the deviation and there annual mean return

![risk to reward 2](https://github.com/aeshna25/Algorithm-trading-using-Python/assets/31938370/8a4bc47b-932e-43e7-8261-9afffaa8b4e4)


***Insights***:

Dell , Apple and MSFT have a good return but comes with high risk

DEUTSCHE BANK, Vodafone, Wells fargo, Disney, wipro have low return but high risk

AT & T , Coco-cola, Kellogg, IBM, Pepsi have low return and low risk

SPY, Honeywell, United health group, J P Morgan have high return for low risk

3. **Correlation  and covariance** :  Companies belonging to same domain have high correlation. E.g.: (Coco-cola, Pepsi), (Apple, Qcom, Msft), (DB, JPM, WFC), (Metlife, JPM, WFC, DB)


![correlation](https://github.com/aeshna25/Algorithm-trading-using-Python/assets/31938370/48a2ea68-31ef-4dff-be12-1d92f22fd62e)

4. **Simple and Log returns ** : To understand the returns we took Simple moving average for 50 and 100 days and exponential moving average for 100 days. The calculation helps us in understanding different type of returns calculation.

![smaema](https://github.com/aeshna25/Algorithm-trading-using-Python/assets/31938370/499ecf8a-ef6b-4fb3-81db-310474b6a3ce)

5. **Cummalative returns and Dropdowns** : With the help of Cummalative return we can check what $1 invested at the start of the stock would have converted to till now.

![cummalativereturn](https://github.com/aeshna25/Algorithm-trading-using-Python/assets/31938370/86d7f629-3d94-4d02-bcd9-4ddce8908ca7)


***Insights*** 

In case of Apple, $1 invested in 1980 , should return around $1700 in 2024.

*Dropdowns and Dropdown%* : A drawdown refers to how much an investment or trading account is down from the peak before it recovers back to the peak.Percentage between the peak and the subsequent trough.If a trading account has $10,000 in it, and the funds drop to $9,000 before moving back above $10,000, then the trading account witnessed a 10% drawdown.

![dropdown](https://github.com/aeshna25/Algorithm-trading-using-Python/assets/31938370/6f60290a-57aa-437d-92f5-4a1190e40537)

***Insights*** 

apple['drowdown'] =apple['cummax'] - apple['cummareturns']

In case of Apple, max dropdown noticed was 444. and from the image we can notice since the last past days, there was flatuation around Close price ranging from $129 to $125.

6. **Strategies** : I tested 3 statergies with regards to SMA 50 and SMA 200, namely

a. Buy and hold
b. Long and short : IF SMA 50 > SMA 100 then long (1) else short(-1)
c. Long bias : IF SMA 50 > SMA 100 then long (1) else no moment (0)

![long and short](https://github.com/aeshna25/Algorithm-trading-using-Python/assets/31938370/7640a786-b615-4c2a-85b7-429ef5d53f27)


On the basis of, conversion of $1 using individual strategies as well as the standard deviation offered by each, conclusion was made that long bias strategy will yield best returns with minmum risks.

*Standard deviation(risk)*:

a. Buy and hold : 43%

b. Long and short : 43%

c. Long bias : 31%


*$1 value(reward)*:

a. Buy and hold : 438%

b. Long and short : 15%

c. Long bias : 82%
