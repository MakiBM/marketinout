---
trigger: always_on
---

# Stock universe

`ticker(fb,aapl,msft)`
The ticker function allows you to run the screener only on the ticker names specified as parameters. May not include more than 100 ticker names. Use the Watch List tool to run the screener on a larger ticker list.

`exch(nyse,nasdaq)`
You can specify one or more stock exchanges for screening. Only items from the following list can be used as parameters: nyse, nasdaq, otc, iex, tsx, tsxv, cse, lse, xetra, moex, tadawul, nse, bse, bm, ses, ise, hkse, shse, szse, tse, asx, nzx.

`[watch list name]`
You can specify a pre-created watchlist as a stock universe. To do this, enclose the watchlist name in square brackets. You can select multiple watchlists by specifying their names, separated by commas: [watch list 1, watch list 2, watch list 3]

`[portfolio name]`
Likewise, the name of a pre-created trading portfolio can be used. It is also possible to narrow the selection to open positions only, for example, [portfolio name@active] or closed positions [portfolio name@closed]. You can specify several portfolios by listing their names separated by commas, for example, [portfolio name 1 @active, portfolio name 2 @closed, portfolio name 3 @all]

`caps(large,mid)`
Sets the market capitalization condition. Only items from the following list can be used as parameters: micro, small, mid, large. The market capitalization breakdown is as follows, micro: 0 - 150M, small: 150M - 500M, mid: 500M - 5B, large: above 5B

`sector(energy,basic_materials)`
Sets the sector condition. Only items from the following list can be used as parameters: energy, basic_materials, industrial_goods, conglomerates, consumer_goods, healthcare, financial, technology, services, utilities, real_estate.

`industry(130,131,132)`
Sets the industry condition. An industry code or a comma-separated list of industry codes is required as parameters. Please refer to the List of Industries help topic for more details.

`index(sp500,nasdaq100)`
Sets the index membership condition. Only items from the following list can be used as parameters: dow, sp500, nyse, nasdaq, nasd100, ru1000, ru2000, ru3000, rumid, rumicro, tsx, ftse100, ftse250, ftseall, dax, asx50, asx200, asxord, hsi, sti, klci, nifty50, next50, nifty200, nifty500.

`type(stock)`
Sets the instrument type condition. The following parameters can be used: stock, fund, warrant, right, fixed, shell, and unit for stocks, ETFs, warrants, rights, fixed income instruments, shell companies, and units, respectively.

`equity(local)`
Sets the equity type condition. The following parameters can be used: local, adr, and gdr for local equities (regular stocks), ADRs, and GDRs, respectively.

`class(cs)`
Sets the equity class condition. The following parameters can be used: cs and pfd for common stocks, and preferred stocks, respectively.

`country(us,ca,gb)`
Sets the headquarter country condition. Comma-separated two-letter ISO 3166 country codes are used as parameters.

`options(yes)`
Allows specifying if a stock has options listed and tradable on a market exchange. Only two parameters are supported, yes and no.

`commodity(metals,crude_oil,gas)`
This function narrows screening to specified commodity market instruments. Only the following items can be used as parameters: metals, crude_oil, gas, agriculture.

`aggregate(indexes)`
This function narrows screening to financial world indexes. The only parameter indexes is supported.

# Calendar functions

`day(1)`
Returns true if the current day of month equal to the parameter value. The parameter value must be in the range of 1..31

`weekday(Sun)`
Returns true if the current day of week equal to the parameter value. The parameter value must be in the range of Sun..Sat

`month(Jan)`
Returns true if the current month equal to the parameter value. The parameter value must be in the range of Jan..Dec

`year(2022)`
Returns true if the current year equal to the parameter value.

`workingday(10)`
Returns true if the current working day of month equal to the parameter value

`workingdayleft(1)`
Returns true if the remaining number of working days in the current month equal to the parameter value. Applicable only in the Strategy Backtest tool.

`hour(12)`
Returns true if the current hour equal to the parameter value. The parameter value must be in the range of 9..15 for IEX exchange and in the range of 0..23 for Forex and crypto exchanges. Applicable for intraday periods only.

`minute(30)`
Returns true if the current minute of hour equal to the parameter value. Applicable for intraday periods only. Items from the list below can be used as parameters. For 5-minute periods: 0, 5, 10, 15, 20, 25, 30, 35, 40, 45, 50, 55; For 15-minute periods: 0, 15, 30, 45; For 30-minute periods: 0, 30;

# Aggregate functions

`max(rsi(14), 10)`
Returns the maximum value of an expression for the specified number of days / bars

`min(rsi(14), 10)`
Returns the minimum value of an expression for the specified number of days / bars

`avg(rsi(14), 10)`
Returns the average value of an expression for the specified number of days / bars

`sum(v[0], 5)`
Returns the sum of values of an expression for the specified number of days / bars

`count(rsi(14) < 30, 10)`
Returns the number of days / bars for which the expression is true for the specified number of days / bars

# Auxiliary functions

`abs(rsi(14) - 50)`
Returns the absolute (positive) value of an expression

`evalat(sma(21) - sma(7), 10)`
Returns the value of the expression specified as the first parameter at the day/bar specified in the second parameter. The expression in this example works the same way as historical screening "(sma(21) - sma(7))@10" but the second parameter can contain any arithmetic expression, for example: evalat(sma(21) - sma(7), min(rsi(14), 7))

`iff(sma(7) > sma(21), sma(7), sma(21))`
If the first parameter's expression is true, the IFF function returns the second parameter's value. If the first parameter's expression is false, it returns the value of the third parameter.

# Price action functions

`gapup`
Returns the gap up % value relative to the previous close price

`gapdn`
Returns the gap down % value relative to the previous close price

`chclose`
Returns the price % change relative to the previous close price

`chopen`
Returns the price % change relative to the open price

`chlow`
Returns the price % change relative to the low price

`chhigh`
Returns the price % change relative to the high price

`chavg`
Returns the price % change relative to the 21-bar average price

`pricechange(10)`
Returns the price change over the specified number of days / bars. You can also use a shorter name for this function: pch, for example, pch(10)

`change(10)`
Returns the price % change over the specified number of days / bars

`pricerange(10)`
Returns the price range calculated using high and low values over the specified number of days / bars. You can also use a shorter name for this function: prng, for example, prng(10)

`priceclose(10)`
Returns the price range calculated using close values over the specified number of days / bars. You can also use a shorter name for this function: crng, for example, crng(10)

`contraction(21,68,10)`
This function allows you to find stocks that are in the consolidation channel (flat) condition. For example, the contraction(21,68,10) function returns true if the 21-day price range is at least 10% lower than the 68-day price range.

`expansion(21,68,200)`
This function allows you to find stocks that are in the rising phase. For example, the expansion(21,68,200) function returns true if the 21-day price range is at least 200% higher than the 68-day price range.

`sequence(price trend_up 100, price trend_dn 20, rsi(14) div_bull, rsi(14) ca 60, 50)`
This function allows to create complex screening criteria using a sequence of technical events on the stock chart. For example, the formula expression sequence(price trend_up 100, price trend_dn 20, rsi(14) div_bull, rsi(14) ca 60, 50) will find stocks for which the price grows for 100 days, then make a rollback of 20 days, RSI shows a bullish divergence and then crosses 60. All four events occur one after another over 50 days.

# Highest and lowest prices

`highest(10)`
Returns the highest price over a specific number of days/bars

`lowest(10)`
Returns the lowest price over a specific number of days/bars

`highestbar(10)`
Returns the shift of the highest price over a specific number of days/bars

`lowestbar(10)`
Returns the shift of the lowest price over a specific number of days/bars

`highestvol(10)`
Returns the highest volume value over a specific number of days/bars

`lowestvol(10)`
Returns the lowest volume value over a specific number of days/bars

`highestvolbar(10)`
Returns the shift of the highest volume value over a specific number of days/bars

`lowestvolbar(10)`
Returns the shift of the lowest volume value over a specific number of days/bars

`highestclose(10)`
Returns the highest close price over a specific number of days/bars

`lowestclose(10)`
Returns the lowest close price over a specific number of days/bars

`highestoc(10)`
Returns the highest open or close price over a specific number of days/bars

`lowestoc(10)`
Returns the lowest open or close price over a specific number of days/bars

`highestclosebar(10)`
Returns the shift of the highest close price over a specific number of days/bars

`lowestclosebar(10)`
Returns the shift of the lowest close price over a specific number of days/bars

`highestocbar(10)`
Returns the shift of the highest open or close price over a specific number of days/bars

`lowestocbar(10)`
Returns the shift of the lowest open or close price over a specific number of days/bars

`offh_21`
Returns the % distance between the current price and the highest price over the specified number of days/bars

`offl_21`
Returns the % distance between the current price and the lowest price over the specified number of days/bars

# Volume

`cvol`
Returns the current volume in millions

`avol(21)`
Returns the average volume over the specified number of days/bars in millions

`volch`
Returns the volume % change relative to the previous day/bar

`volchavg`
Returns the volume % change relative to the 21-bar average volume

`dvol`
Returns the current dollar volume in millions. The current dollar volume is calculated as the current volume multiplied by the last price.

`advol(21)`
Returns the average dollar volume over the specified number of days in millions

`rvol`
Returns the relative volume ratio. The relative volume is calculated as the current daily volume divided by the 21-day average daily volume.

# Candlestick functions

`price`
Returns the current price. You can also use the following synonyms: last, close, c

`open`
Returns the open price. You can also use the following synonym: o

`high`
Returns the high price. You can also use the following synonym: h

`low`
Returns the low price. You can also use the following synonym: l

`wick(0)`
Returns the size of the "upper shadow" part of a candle. The parameter value is the shift relative to the current bar

`tail(0)`
Returns the size of the "lower shadow" part of a candle. The parameter value is the shift relative to the current bar

`body(0)`
Returns the size of the "real body" part of a candle. The parameter value is the shift relative to the current bar

`abody(0)`
Returns the value of the 21-day average size of the "real body" part of a candle. The parameter value is the shift relative to the current bar

`crange(0)`
The range the price moved during the time frame of the candlestick (high - low). The parameter value is the shift relative to the current bar

`arange(0)`
Returns the value of the 21-day average range that the price moved during the time frame of the candlestick (high - low). The parameter value is the shift relative to the current bar

`bmid(0)`
The middle of the candlestick's "real body" (close + open) / 2. The parameter value is the shift relative to the current bar

`tprice(0)`
Returns the Typical Price value for a given bar: (high + low + close) / 3. The parameter value is the shift relative to the current bar

`mprice(0)`
Returns the Median Price value for a given bar: (high + low) / 2. The parameter value is the shift relative to the current bar

`wprice(0)`
Returns the Weighted Price value for a given bar: (high + low + 2 * close) / 4. The parameter value is the shift relative to the current bar

# Math functions

`math.max(ema(50), ema(200))`
Returns the largest of two values passed to it as parameter

`math.min(ema(50), ema(200))`
Returns the smallest of two values passed to it as parameter

`math.sqrt(rsi(14))`
Calculates the square root of the parameter given to it

`math.pow(rsi(14), 2)`
The method returns the value of the first parameter raised to the power of the second parameter

`math.round(rsi(14))`
Rounds a floating point value to the nearest integer using normal math round rules (either up or down)

`math.ceil(rsi(14))`
Rounds a floating point value up to the nearest integer value

`math.floor(rsi(14))`
Rounds a floating point value down to the nearest integer value

`correl(spy)`
Returns the correlation coefficient between the specified ticker and the ticker that is checked against the screening criteria. For example, if we want to find all stocks whose correlation coefficient with the ticker SPY is more than 0.95, the formula expression will be correl(spy) > 0.95. The correlation will be calculated for the last 21 business days by default. You can change this period by setting the second parameter, for example: correl(spy,50) > 0.95.

`correlx(spy)`
Same as the CORREL function but calculated based on daily increments of two tickers.

# Time-based functions

`days_since_ipo()`
Returns the number of days that have passed since the IPO day. In the event of a merger or split-up, this function returns the number of days that have passed since such a corporate event.

`wdays_since_ipo()`
Returns the number of working days that have passed since the IPO day. In the event of a merger or split-up, this function returns the number of working days that have passed since such a corporate event.

`days_to_earn_rep()`
Returns the number of days to the next earnings report date

`days_since_earn_rep()`
Returns the number of days that have passed since the last earnings report date

`wdays_since_earn_rep()`
Returns the number of working days that have passed since the last earnings report date

`minutes_since_update()`
Returns the number of minutes since the last stock quote update

`bars()`
Returns the total number of bars available for a ticker

`bars_since(sma(50) ca sma(200))`
Returns the number of days/bars that have passed since the specified technical event. Returns a zero value if the technical event occurred today (on the current bar). The function will use only the last 500 bars to search for the specified technical event.
Output instructions

`sortby(rsi(7), desc, 10)`
Instructs the Stock Screener to sort results by the specified indicator, financial metric or other parameter, using the ascending (asc) or descending (desc) order. The third parameter indicates how many stocks to select after sorting. The second and third parameters are optional. If the parameter indicating the sorting direction is not specified, then ascending order will be used. If the third parameter is not specified, then after sorting all stocks will be selected.

`show(rsi(14))`
Instructs the Stock Screener to add the listed columns to the results page. Columns will be added to the right of the standard columns of the stock screen and will display the corresponding values for each ticker. The indicators listed in the show function will also be plotted on charts that are opened from the stock screen and on mini charts when switching to the "Charts" view.
In this example, you can also set the column name as follows: show(rsi(14) as rsi)

`draw(rsi(7), rsi(14))`
Instructs the Stock Screener to draw the listed indicators on charts that are opened on the results page and on mini charts when switching to the "Charts" view.

# Historical screening

`hist(12/31/2019)`
Instructs the Stock Screener to perform historical screening. The screener will only select stocks that match the formula expression as of the specified date. The date should be indicated in a short date format: month/day/year.

# Price level functions

`fibo23s(1)`
Returns the value of the 23.6% Fibonacci retracement level. Fibonacci is applied to the first (nearest by registering date) recognized uptrend. Examples:
price cb fibo23s(1) - price crossed below the 23.6% fibo level.
price tocha fibo23s(1) - price touched above the 23.6% fibo level.
price bon_up fibo23s(1) - price bounced up from the 23.6% fibo level.
For 38.2%, 50.0%, 61.8% and 78.6% fibonacci levels, you can use the following functions: fibo38s, fibo50s, fibo62s, fibo78s.

`fibo23r(1)`
Returns the value of the 23.6% Fibonacci retracement level. Fibonacci is applied to the first (nearest by registering date) recognized downtrend. Examples:
price ca fibo23r(1) - price crossed above the 23.6% fibo level.
price tochb fibo23r(1) - price touched below the 23.6% fibo level.
price bon_dn fibo23r(1) - price bounced down from the 23.6% fibo level.
For 38.2%, 50.0%, 61.8% and 78.6% fibonacci levels, you can use the following functions: fibo38r, fibo50r, fibo62r, fibo78r.

`snr_sup(9,1)`
Returns the value of the first (nearest by registering date) support level of the SNR(9) indicator. Examples:
price cb snr_sup(9,1) - price crossed below the 1st support level of the SNR(9) indicator.
price tocha snr_sup(9,2) - price touched above the 2nd support level of the SNR(9) indicator.
price bon_up snr_sup(9,3) - price bounced up from the 3nd support level of the SNR(9) indicator.
You can also use snrc_sup and snroc_sup functions for accessing the support level of the SNRC(9) and SNROC(9) indicator correspondingly.

`snr_res(9,1)`
Returns the value of the first (nearest by registering date) resistance level of the SNR(9) indicator. Examples:
price ca snr_res(9,1) - price crossed above the 1st resistance level of the SNR(9) indicator.
price tochb snr_res(9,2) - price touched below the 2nd resistance level of the SNR(9) indicator.
price bon_dn snr_res(9,3) - price bounced down from the 3nd resistance level of the SNR(9) indicator.
You can also use snrc_res and snroc_res functions for accessing the resistance level of the SNRC(9) and SNROC(9) indicator correspondingly.

`snr_minsup(9,50)`
Returns the value of the lowest support level found using the SNR(9) indicator in the last 50 bars/days. Examples:
price cb snr_minsup(9,50) - price crossed below the value of the lowest support level found using the SNR(9) indicator in the last 50 bars/days.
You can also use the snr_minres function for accessing the lowest resistance level of the SNR(9) indicator.
Use snrc_minsup and snroc_minsup functions for accessing the lowest support level of the SNRC(9) and SNROC(9) indicator correspondingly.

`snr_maxres(9,50)`
Returns the value of the highest resistance level found using the SNR(9) indicator in the last 50 bars/days. Examples:
price ca snr_maxres(9,50) - price crossed above the value of the highest resistance level found using the SNR(9) indicator in the last 50 bars/days.
You can also use the snr_maxsup function for accessing the highest support level of the SNR(9) indicator.
Use snrc_maxres and snroc_maxres functions for accessing the highest resistance level of the SNRC(9) and SNROC(9) indicator correspondingly.

`snrmap(9,5)`
Returns "1" if the corresponding bar creates a support line and "2" if it creates a resistance line. Examples: snrmap(9,5) = 1 - The fifth bar back from the current bar creates a support line.

# Williams' Fractals

`frasup(2,2,1)`
Returns the value of the first (nearest by registering date) lower fractal level of the Fractals(2,2) indicator. Examples:
price cb frasup(2,2,1) - price crossed below the 1st lower fractal level of the Fractals(2,2) indicator.
price tocha frasup(2,2,1) - price touched above the 1st lower fractal level of the Fractals(2,2) indicator.
price bon_up frasup(2,2,1) - price bounced up from the 1st lower fractal level of the Fractals(2,2) indicator.

`frares(2,2,1)`
Returns the value of the first (nearest by registering date) upper fractal level of the Fractals(2,2) indicator. Examples:
price ca frares(2,2,1) - price crossed above the 1st upper fractal level of the Fractals(2,2) indicator.
price tochb frares(2,2,1) - price touched below the 1st upper fractal level of the Fractals(2,2) indicator.
price bon_dn frares(2,2,1) - price bounced down from the 1st upper fractal level of the Fractals(2,2) indicator.

`framinsup(2,2,50)`
Returns the value of the lowest support fractal level found using the Fractals(2,2) indicator in the last 50 bars/days. Examples:
price cb framinsup(2,2,50) - price crossed below the lowest support fractal level found in the last 50 days.
You can also use the framinres function for accessing the lowest resistance fractal.

`framaxres(2,2,50)`
Returns the value of the highest resistance fractal level found using the Fractals(2,2) indicator in the last 50 bars/days. Examples:
price ca framaxres(2,2,50) - price crossed above the highest resistance fractal level found in the last 50 days.
You can also use the framaxsup function for accessing the highest support fractal.

`framinsupbar(2,2,50)`
Returns the shift of the lowest support fractal found using the Fractals(2,2) indicator in the last 50 bars/days. Examples:
framinsupbar(2,2,50) < 5 - the 50-day lowest support fractal was registered over the last 5 days.
You can also use the framinresbar function for accessing the shift of the lowest resistance fractal.

`framaxresbar(2,2,50)`
Returns the shift of the highest resistance fractal found using the Fractals(2,2) indicator in the last 50 bars/days. Examples:
framaxresbar(2,2,50) < 5 - the 50-day highest resistance fractal was registered over the last 5 days.
You can also use the framaxsupbar function for accessing the shift of the highest support fractal.

`fractalmap(2,2,3)`
Returns "1" if the corresponding bar has a lower fractal and "2" if it has an upper one. Examples: fractalmap(2,2,3) = 1 - The third bar back from the current bar has a lower fractal.

# Backtesting aids

`posprice`
Formula expression can be used as a criteria for closing a position in the Strategy Backtest tool. This can be done by ticking the "Set by a formula expression" option and assigning the corresponding formula expression.

You can get the value of the price at which the position was opened using the "posprice" literal.

`posbar`
You can get the index of the day/bar at which the position was opened using the "posbar" literal. It is typically used in data arrays: open, high, low, close, v. For example, low[posbar] will give the low price of the day/bar at which the position was opened.

`evalat`
You can get the value of the indicator or expression at the moment the position was opened using the "posbar" literal and the "evalat" function. For example, evalat(rsi(14), posbar) will give the value of the RSI(14) indicator recorded on the day the position was opened.

`posage`
You can get the number of days/bars elapsed since the position was opened.

`stopat(psar(0.02,0.2))`
Instructs the trading simulator to move the stop loss level to the specified value. As a parameter, you can specify an indicator, function, or other formula expression that returns a numerical value. For example: stopat(psar(0.02,0.2)), stopat(ema(7)), stopat(lowest(21)). If the expression for closing a position has already been set, then the function must be added using the "or" operator. For example: rsi(14) < 60 or stopat(psar(0.02,0.2)). Please note that the "stopat" function is applied with a one day/bar delay. That is, stop loss is calculated on the current day/bar but will be applied on the next day/bar.

`takeat(bbub(20,2))`
Instructs the trading simulator to move the take profit level to the specified value. As a parameter, you can specify an indicator, function, or other formula expression that returns a numerical value. For example: takeat(bbub(20,2)), takeat(1.5 * ema(50)), takeat(highest(21)). If the expression for closing a position has already been set, then the function must be added using the "or" operator. For example: rsi(14) > 75 or takeat(bbub(20,2)). Please note that the "takeat" function is applied with a one day/bar delay. That is, take profit is calculated on the current day/bar but will be applied on the next day/bar.

`iff(price > 1.05 * posprice, stopat(low[0]))`
The IFF function can be useful in the formula for closing a position in combination with the STOPAT or TAKEAT instructions. In this formula, the stop loss will be set at the day's low level, but only if the position's profit is more than 5%. If the expression for closing a position has already been set, then the function must be added using the "or" operator. For example: rsi(14) < 60 or if(price > 1.05 * posprice, stopat(low[0]))
