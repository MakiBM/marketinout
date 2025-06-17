---
trigger: always_on
---

Formula Screener is the most powerful tool we provide on the portal. Whereas a regular stock screener applies "and" conditions to all selected criteria (i.e., all criteria must be met for a stock to be selected), the Formula Screener allows you to combine "and", "or" and "not" conditions to build particular criteria. Moreover, the Formula Screener tool gives you the possibility to combine criteria on different time periods. In other words, it is possible to find stocks that meet some conditions on a daily chart and others on weekly or monthly charts. It is worth mentioning that the historical screening feature gets more flexible in the Formula Screener. You can specify an offset value for any criteria in a formula expression in days, weeks, or months if the corresponding periods were set for the criteria. Range screening leverages the above approach and allows you to set a condition to be met within some time. Let's say you may allow a moving average crossover to occur within the last 3 days or require an oscillator to be in an oversold zone all the previous 10 days. It should be noted that when combining many conditions in a formula, it is essential to use parentheses so that the screener knows the order in which each condition should be evaluated. The following examples demonstrate how to code maximally flexible criteria in formula expressions:

# Simple expressions

`exch(nasdaq) and cap > 1 and price >= 5 and avol > 1 and price ca sma(50)`
Exchange: NASDAQ
and Capitalization > 1 million
and Price > 5
and Average Volume > 1 million
and Price Crossed Above MA(50)
avol in this formula stands for a 21-day average daily volume. Note that avol and cap are in millions.

`exch(nasdaq, nyse) and price trend_up 7 and ( rsi(14) div_bull or macd(12,26,9) div_bull )`
Exchange: NASDAQ or NYSE and
Price Trending Up Last 7 Days
and ( RSI(14) Bullish Divergence or MACD(12,26,9) Bullish Divergence )

`avol > 1 and gapup > 20 and rsi(14) < 80`
Average Volume > 1 million
and Gap Up is Greater than 20%
and RSI(14) is Below 80
NYSE and NASDAQ exchanges will be used by default in this formula.

`type(stock) and advol > 100 and price risunvol`
Find only regular stocks (excluding ETFs) having an average dollar volume greater than 100 million and rising on unusual volume. Please note that advol is in millions and stands for a 21-day average daily dollar volume. For finding ETFs with the same condition, the formula may look like this: type(fund) and advol > 100 and price risunvol

`index(sp500, nasdaq100) and sma(50) ca sma(200)`
Find components of the S&P 500 and Nasdaq 100 index with the 50-day SMA crossed above the 200-day SMA.

`[watch list name] and macd(12,26,9) ca macds(12,26,9)`
You can screen a pre-created watchlist by entering its name in square brackets. In this case, the watchlist will work as the stock universe criterion. To screen multiple watchlists, write their names separated by commas. To screen a pre-created trading portfolio, you can similarly enter its name in square brackets.In this example, we want to find stocks from the specified watch list with MACD crossed above its signal line.

`ticker(meta, amzn, aapl, msft, goog) and nh_21`
Find stocks from the specified list that hit their 21-day new high. Please note that the number of custom tickers has a limit of 100. Use the watchlist as a stock universe criterion for more.

# Using different time periods

`( rsi(20) > 50 )@monthly and ( price > ema(20) )@weekly and ( price ca sma(7) )@daily`
RSI(20) Is Above 50 on monthly periods and
Price Is Above EMA(20) on weekly periods and
Price Crossed Above SMA(7) on daily periods

`( cdl_ham @daily or cdl_buki @daily ) and ( cdl_lowl@weekly or cdl_bu3ws@weekly or cdl_wb@monthly )`
Hammer or Bullish Kicker on daily periods and
Long White Line or Three White Soldiers on weekly periods or White Body on monthly periods

`exch(iex) and ( price ca sma(50) )@hourly and ( price > sma(50) )@h4`
Exchange: IEX and Price Crossed Above SMA(50) on hourly periods and Price is Above SMA(50) on 4-hour periods.
Please note that 5-minute, 15-minute, 30-minute, 1-hour, and 4-hour periods are currently available only for IEX, Forex, and crypto exchanges. Regarding the IEX exchange, data for IEX stocks and NYSE/NASDAQ stocks are almost identical. Thus, you may run a screening on IEX, and it will give the same results as for the NYSE/NASDAQ. It should be noted that the suffix ".IX" is added to the tickers on the IEX exchange, for example, AAPL.IX.

# Referring to a ticker or index data

`index(sp500, nasdaq100) and rsi(3) < rsi(3)@aapl and pp_21 > pp_21@sp500`
You can refer to any ticker or market index data. In this example, we want to find S&P 500 and Nasdaq 100 index components with a 3-day RSI lower than AAPL's 3-day RSI and a 21-day price performance (%) greater than the S&P 500's 21-day price performance (%). The following index tokens can be used: dow, sp500, nasdaq, nasd100, ru1000, ru2000, ru3000, rumid, rumicro, tsx, ftse100, ftse250, ftseall, dax, hsi, sti, asx50, asx200, asxord, klci, nifty50, next50, nifty200, nifty500, vix, axvi.

# Regime filter

`(ema(7) > ema(200))@sp500 and rsi(14) ca 80`
Find stocks for which RSI(14) crossed above 80. Give results only if EMA(7) is above EMA(200) on the S&P 500 chart. The (ema(7) > ema(200))@sp500 condition here works as a regime filter. Please note that if SMA(7) < SMA(200) for S&P 500, the screener will give no results.
Any ticker name or the following index tokens can be used: dow, sp500, nasdaq, nasd100, ru1000, ru2000, ru3000, rumid, rumicro, tsx, ftse100, ftse250, ftseall, dax, hsi, sti, asx50, asx200, asxord, klci, nifty50, next50, nifty200, nifty500, vix, axvi.

`(advdec trend_up 10)@nasdaq and (mo > 0)@nasdaq and (msi > 0)@nasdaq and rsi(14) ca 80`
Find stocks for which RSI(14) crossed above 80. Give any results only if Nasdaq Composite Advance/Decline is trending up last 10 days and both McClillan Oscillator and Summation Index are above zero.

`(price > ema(200))@aapl@weekly and rsi(14) ca 80`
Find stocks for which RSI(14) crossed above 80. Give results only if price is above EMA(200) on the AAPL's weekly chart.

`index(nasdaq100) and price higher_highs 3 and price@vix > 20 and pp_10@qqq > pp_10@spy`
Find stocks from the Nasdaq 100 index that have made a series of higher highs over the last three days. Give results only if the VIX index is higher than 20 and the QQQ ETF's 10-day price performance (%) is higher than the SPY ETF's 10-day price performance (%).

# Historical screening

`(ema(7) ca ema(50))@2 and cdl_ham@1`
EMA(7) Crossed Above EMA(50) 2 days ago
and "Hammer" 1 day ago
(The @2 and @1 designators here specify shift relative to the current bar the given amount of periods ago)

`(price ca sma(7))@2@weekly and (chopen > 5)@1@daily`
Price Crossed Above SMA(7) on weekly periods 2 weeks ago
and Change From Open > 5% yesterday
(The @2 and @1 designators here specify shift relative to the current bar the given amount of periods ago)

`sma(50) > sma(50)@10`
Current value for SMA(50) is greater than value for SMA(50) taken 10 days ago

`macdh(12,26,9) > macdh(12,26,9)@1 and macdh(12,26,9)@1 < macdh(12,26,9)@2`
Today's MACD histogram value is higher than yesterday's, and yesterday's MACD histogram value is lower than the day before yesterday.

`price ca sma(100) and hist(12/31/2019)`
Find stocks for which the price has crossed above SMA(100) on December 31, 2019. The Stock Screener will only select tickers that match the formula expression as of the specified date. The date should be indicated in a short date format: month/day/year

# Range screening

`(rsi(14) ca 80)@[0..4]`
RSI(14) indicator crossed above 80 within the last 5 days/bars. This formula is equivalent to
(rsi(14) ca 80)@0
or (rsi(14) ca 80)@1
or (rsi(14) ca 80)@2
or (rsi(14) ca 80)@3
or (rsi(14) ca 80)@4
Note that in this example, we used square brackets.

`(rsi(14) > 80)@{0..4}`
RSI(14) indicator is above 80 during the last 5 days/bars. This formula is equivalent to
(rsi(14) > 80)@0
and (rsi(14) > 80)@1
and (rsi(14) > 80)@2
and (rsi(14) > 80)@3
and (rsi(14) > 80)@4
Note that in this example, we used curly brackets.

`( rsi(14)@fixed > rsi(14 )@1)@{0..9}`
RSI(14) indicator has reached its maximum value in the last ten days. This formula is equivalent to rsi(14) > rsi(14)@1 and rsi(14) > rsi(14)@2 and .. and rsi(14) > rsi(14)@10. Note that in this example, we used curly brackets.
Range shifts are not applied to a @fixed expression, allowing it to have a fixed value. As if we can build loops, leaving some expressions inside the loop unchanged.

`( close[0]@fixed > close[1] )@[0..9]`
Today's closing price is higher than the closing price of at least one of the last ten days. This formula is equivalent to close[0] > close[1] or close[0] > close[2] or .. or close[0] > close[10]. Note that in this example, we used square brackets.

# Using data arrays

`high[1] > high[2] and low[1] > low[2] and v[1] > 2 * v[2] and close[0] > high[1] and open[0] > low[1] and v[0] > 1`
The previous bar shows ascending high and low with doubling volume, and the current price is greater than the previous high, the open price is greater than the previous low, and the current volume is greater than 1 million.
You can also use shorter names o, h, l, and c for open, high, low, and close respectively. Note that close[0] = price = last. Volume values in the v array are in millions.

`low[0] > 1.05 * high[1] and close[0] > 1.05 * open[0]`
Gap up is greater than 5%
and change from open is greater than 5%

`v[0] > 1 and open[0] > close[1] + 10`
Today's volume is greater than 1 million and open price is greater than previous close + $10

# Volume

`avol(10) > 1 and advol(10) > 100`
10-day average daily volume is greater than 1 million
and 10-day average daily dollar volume is greater than 100 million
We use avol and advol with parameters in this example. If the parameter is not specified, then they use the period of 21. It is worth noting that this period corresponds to one calendar month since there are usually 21 trading days in one month.
avol and advol used without parameters in the previous examples are equivalent to avol(21) and advol(21) correspondingly.

`( v[0] > 3 * avol(10) or v[1] > 3 * avol(10) ) and (v[0] + v[1]) > 5 * avol(10)`
Today's or yesterday's volume is at least three times greater than the 10-day average daily volume, and today's and yesterday's volume, in sum, is at least five times greater than the 10-day average daily volume average.

`volume trend_up 7 and vma(21) trend_up 7`
The volume has been trending up over the last seven days, and the volume 21-day moving average has been trending up over the last seven days

`rvol > 5`
Relative volume is greater than five. Relative volume is calculated as the ratio of the current daily volume to the 21-day average daily volume. You can also use rvol with a parameter. For example, rvol(10) > 5 expression reads as the ratio of the current daily volume to the 10-day average daily volume is greater than five.

# Aggregate functions

`price > max( h, 10 )@1`
The current price is higher than the maximum value of high prices calculated for the last 10 days at the time of yesterday.

`price < min( l, 10 )@1`
The current price is lower than the minimum value of low prices calculated for the last 10 days at the time of yesterday.

`max( ema(200), 10 ) - min( ema(200), 10 ) < .02 * price`
The difference between the maximum and minimum value of the EMA indicator for the last 10 days is less than 2% of the price.

`avg( rsi(14), 10 ) > 80`
The average value of the RSI indicator for the last 10 days is above 80.

`abs( rsi(14) - 50 ) > 40`
The absolute value of the difference between the value of the RSI indicator and 50 is greater than 40.

# Scoring conditions

`(price trend_up 21) + (price risunvol) + (price higher_highs 7) >= 2`
At least two of the three conditions in the expression must be met.
Note that each condition in the expression is converted to 0 or 1, depending on whether it is met or not.

`(rsi(14) div_bull) + (ao(5,34) div_bull) + (cci(14) div_bull) + (mom(14) div_bull) + (stoch(5,3,3) div_bull) >= 4`
At least four of the five conditions in the expression must be met.

#Negate operator

`exch(nasdaq, nyse) and ! sector(financial) and ! industry(425,426,427) and price ca bbub(20,2)`
Exchange: NASDAQ or NYSE
and not Financial sector
and not an industry with code 425, 426 or 427
and Price Crossed Above Upper Band of BBands(20,2)

`index(ru1000) and nh_all and ! [watch list name]`
You can exclude a pre-created watchlist from screening. This list may include undesirable stocks for screening, such as leveraged or inverse ETFs. In this example, we want to find all stocks from Russell 1000 index that hit their all-time new high and are not included in the specified watchlist.

`price trend_up 200 and ! ( rsi(14) div_bear )`
Price Trending Up Last 200 Days
and
not "RSI(14) Bearish Divergence"

# Conditional expressions

`rsi(14) ca iff(price > ema(21), 60, 40)`
This formula expression will work like rsi(14) ca 60 in case if price > ema(21) and as rsi(14) ca 40 otherwise. It is worth noting that this expression is a shorter form for
(price > ema(21) and rsi(14) ca 60) or (price <= ema(21) and rsi(14) ca 40).

# Fundamental criteria

`exch(nasdaq,nyse) and cap > 100 and eps > 5 and pe < 10 and roic > 15 and ebitda > 10000 and enterprise_ebitda < 25`
Exchange NASDAQ or NYSE and Capitalization > 100 million and EPS > 5 and P/E < 10 and ROIC > 15 and EBITDA > 10 billion and Enterprise Value / EBITDA ratio < 25.
Please refer to the Fundamental Indicators help page to view the complete list of supported fundamental indicators.

`sector( financial, technology, services ) and tip_ptpm > 100 and tip_ebitda > 100`
The sector is one of the following: Financial, Technology, Services, and Pre-tax Profit Margin to Industry Average, % > 100%, and Earnings to Industry Average, % > 100%

`price_book_ratio < 50 and price_free_cash_ratio < 30 and debt_equity_ratio < 2`
The Price / Book ratio is less than 50, and Price / Free Cash Flow ratio is less than 30, and the Debt / Equity ratio is less than 2

`altman_z_score > 3 and piotroski_f_score >= 7 and beneish_m_score < -2.22`
The Altman Z-Score is above 3, the Piotroski F-Score is above or equal to 7, and the Beneish M-Score is less than -2.22

`dvd_yield > 2 and dvd_payout_ratio > 30`
The Dividend Yield is above 2, and the Dividend Payout Ratio is above 30

`eps_qtr[0] > eps_qtr[1] and eps_qtr[1] > eps_qtr[2]`
The most recent quarter's EPS is greater than the previous quarter's EPS, and the previous quarter's EPS is greater than the pre-previous quarter's EPS. Please refer to the Quarterly data section of the Fundamental Indicators help page for more details.

`ebitda_y[0] > 1.2 * ebitda_y[1] and ebitda_y[1] > 1.2 * ebitda_y[2]`
The most recent fiscal year's EBITDA is at least 20% greater than the previous fiscal year's EBITDA, and the previous fiscal year's EBITDA is at least 20% greater than the pre-previous fiscal year's EBITDA. Please refer to the Annual data section of the Fundamental Indicators help page for more details.

`eps_yoy > 20`
Year-over-year Earnings Per Share growth is greater than 20%

`revenue_qoq > 10`
Quarter-over-quarter Revenue growth is greater than 20%

`net_income_5y_growth > 20`
Net Income 5-year compound annual growth rate is greater than 20%

`buyback_yield_5y_avg > 3`
Buyback Yield 5-year average is greater than 3%

# Technical criteria

`( fibo_ta23 or fibo_ta38 or fibo_ta50 ) and ln_art`
( "Price Touched 0.23 Fibonacci Support Level"
or "Price Touched 0.38 Fibonacci Support Level"
or "Price Touched 0.50 Fibonacci Support Level" )
and "Price Is Above Rising Trend Line" )

`cap > 100 and price < 50 and ( cdl_lowl or price risunvol )`
Capitalization > 100 mln
and Price < 50
and ( "Long White Line" or "Rising on Unusual Volume" )

`( price ca sma(200) or price ca sma(50) ) and rsi(14) div_bull`
( "Price Crossed Above MA(200)" or "Price Crossed Above MA(50)" )
and "RSI(14) Bullish Divergence"

# Heikin Ashi chart criteria

`(price ca sma(50))@heikin`
For any condition, you can indicate that it must apply to the Heikin Ashi chart.
Price crossed above SMA(50) on the Heikin Ashi chart.

`(price < sma(50))@heikin and price ca sma(50)`
Price is lower than SMA(50) on the Heikin Ashi chart, but it crossed above SMA(50) on a classical bar chart.

`(price higher_closes 5)@heikin@weeks`
A five-candlestick series of rising closing prices on the weekly periods of the Heikin Ashi chart.

# Output instructions

`rsi(7) trend_up 5 and sortby(rsi(7), asc)`
RSI(7) is trending up over the last 5 days. Stock Screener results will be sorted in ascending order by the RSI(7) indicator value. We could also just write sortby(rsi(7)) here since the ascending order will be used by default.
The sortby function can also be used in the Strategy Backtest tool to set more flexible prioritization when adding stocks to the trading portfolio. In this case, the criteria for opening a position should be set using a formula expression.

`rsi(7) trend_dn 5 and sortby(rsi(7), desc)`
RSI(7) is trending down over the last 5 days. Stock Screener results will be sorted in descending order by the RSI(7) indicator value.

`enterprise_ebitda < 15 and sortby(dvd_yield, desc, 10)`
Enterprise Value to EBITDA ratio is less than 15. Stock Screener results will be sorted by dividend yield in descending order and only the top 10 stocks will be selected.

`rsi(14) ca 30 and show(rsi(14))`
Find stocks for which the RSI(14) indicator crossed above 30 and add the "RSI(14)" column to the Stock Screener results page. Columns will be added to the right of the standard columns of the stock screen and will display the corresponding values for each ticker. The indicators listed in the show function will also be plotted on charts that are opened from the stock screen and on mini charts when switching to the "Charts" view.

`rsi(7) ca rsi(14) and rsi(7) < 30 and show(rsi(7), rsi(14), ebitda, dvd_yield, pe)`
Find stocks for which the RSI(7) line crossed above RSI(14) and RSI(7) is less than 30 and add RSI(7), RSI(14), ebitda, dividend yield and P/E ratio columns to the Stock Screener results page.

`rsi(14) ca 30 and show(rsi(14) - smarsi(14,9) as diff)`
Find the stocks for which the RSI(14) crossed above 30 and add a column named "diff", showing the difference between the RSI(14) and the 9-period simple moving average of RSI(14) on the Stock Screener results page.

`ema(100) trend_up 100 and draw(rsi(7), rsi(14))`
EMA(100) is trending up over the last 100 days. The RSI(7) and RSI(14) indicators listed in the draw function will be plotted on charts that are opened from the Stock Screener results page and on mini charts when switching to the "Charts" view.

# Access to a trading position in the backtesting tool

`price < posprice - 1`
Formula expression can be used as a criteria for closing a position in the Strategy Backtest tool. This can be done by ticking the "Extract criteria from screen" option and selecting the appropriate formula screen. In this formula, you can get the value of the price at which the position was opened using the "posprice" literal.
In this example, we want to close a position as soon as the current price has fallen below the purchase price minus one dollar.

`price cb sma(7) and price > 1.2 * posprice`
In this example, we close the position when the price crosses down SMA(7), but only if the profit is already more than 20%.
You can also get access to the position's stop loss and take profit by using the posstop and postake variables correspondingly.

`price < low[posbar]`
You can get the index of the day/bar on which the position was opened using the "posbar" literal. In this example, we want to close the position as soon as the current price has fallen below the low price formed on the day the position is opened.

`rsi(14) < evalat(rsi(14), posbar)`
You can get the value of the indicator or expression at the moment the position was opened using the "posbar" literal and the "evalat" function. In this example, we want to close the position as soon as the current value of the RSI(14) falls below the value of the RSI(14) recorded on the day the position was opened.

`posage = 5`
You can get the number of days/bars elapsed since the position was opened. In this example, we want to close a position 5 days after it was opened.

`stopat(psar(0.02,0.2))`
Instructs the trading simulator to move the stop loss level to the specified value. As a parameter, you can specify an indicator, function, or other formula expression that returns a numerical value. If the expression for closing a position has already been set, then the function must be added using the "or" operator. For example: rsi(14) < 60 or stopat(psar(0.02,0.2)). Please note that the "stopat" function is applied with a one day/bar delay. That is, stop loss is calculated on the current day/bar but will be applied on the next day/bar.

`takeat(bbub(20,2))`
Instructs the trading simulator to move the take profit level to the specified value. As a parameter, you can specify an indicator, function, or other formula expression that returns a numerical value. If the expression for closing a position has already been set, then the function must be added using the "or" operator. For example: rsi(14) > 75 or takeat(bbub(20,2)). Please note that the "takeat" function is applied with a one day/bar delay. That is, take profit is calculated on the current day/bar but will be applied on the next day/bar.

`iff(price > 1.05 * posprice, stopat(low[0]))`
The IFF function can be useful in the formula for closing a position in combination with the STOPAT or TAKEAT instructions. In this formula, the stop loss will be set at the day's low level, but only if the position's profit is more than 5%. If the expression for closing a position has already been set, then the function must be added using the "or" operator. For example: rsi(14) < 60 or iff(price > 1.05 * posprice, stopat(low[0]))

# Adding comments inside a formula expression

```
/* find components of the S&P 500 and Nasdaq 100
with rsi(14) at least 10 higher than AAPL's rsi(14) */

index(sp500, nasd100) and rsi(14) > rsi(14)@aapl + 10   
```
You may add your comments inside a formula expression.
Multi-line comments start with /* and end with */. The Formula Screener will ignore any text between /* and */.

```
// find tickers in the custom list
ticker(meta, amzn, aapl, msft, goog)

// outperforming S&P 500 by a 5-day % change
and pp_5 > pp_5@sp500
```
Single-line comments start with two forward slashes //. The Formula Screener ignores any text between // and the end of the line.
