---
trigger: always_on
---

This section contains examples of more complex formulaic expressions.

`100 * (price - sma(200) / price) > 50` - Price is at least 50% above the 200-day moving average.
`abs(price - ema(10)) < 0.01 * price` - The price is within the 1% corridor of the 10-day EMA
`(ema(200) - ema(50) < min(ema(200) - ema(50), 80)@1)@weekly` - The distance between 200-period EMA and 50-period EMA has reached its minimum value over the last 80 bars on the weekly chart
`math.max( math.max(ema(7), ema(21)), ema(50) ) - math.min( math.min(ema(7), ema(21)), ema(50) ) < .05 * atr(14)` - The values of the 7-day, 21-day, and 50-day moving averages are close to each other (distant from each other by no more than 5% of the 14-day average daily range).
`(price ca sma(7))@[0..10] and count( rsi(14) ca 80, bars_since(price ca sma(7)) ) >= 1` - The price crossed above the 7-day SMA during the last ten days, and the 14-day RSI crossed above 60 some days after this event.
`price < low[bars_since(rsi(2) cb 70)]` - The price is below the Low price recorded on the day when the 14-day RSI crossed below 70.
`price ca high[bars_since(macd(12,26,9) casl)]@weekly` - The price crossed above the High price recorded on the week when the MACD crossed above the signal line on weekly periods.
`c > highestclose(20)@1` - Today's closing price has reached its highest value over the last twenty days (a new 20-day high recognized using only closing prices).
`c > o and v > max(if(c > o, v, 0), 10)@1` - Today's Close price is higher than the Open price, and today's volume is higher than the highest positive volume in the previous ten days. Positive volume here refers to the volume on a day when the Close price exceeds the Open price.
`roc(10) < min(roc(10), 50)@1` - 10-day ROC has reached its minimal value over the last 50 days.
`evalat(slowk(14,3,3), bars_since(slowk(14,3,3) ca slowd(14,3,3))) < 15` - The Stochastic %K value on the day the %K crossed above the %D is less than 15. For example, if %K crossed above %D five days ago, the value of %K on that day must be less than 15.
`wdays_since_earn_rep() = 5 and change(5) > 10` - Five working days have passed since the earnings report date, and the price over these five days has risen by at least 10%.
`100 * (close - close[wdays_since_earn_rep()]) / close[wdays_since_earn_rep()] > 20` - The price has risen at least 20% since the last earnings report date.
`price ca high[wdays_since_earn_rep()] and draw(earnrep)` - The price crossed the high price recorded on the day of the recent earnings report date. We also instruct the screener to display the earnings report dates on a stock chart.
`macd(12,26,9) ca macds(12,26,9) and !(macd(12,26,9) ca macds(12,26,9))@[1..10]` - MACD crossed above its signal line for the first time in the last ten days (no such intersection was recognized over the previous ten days).
`count(price tochb ema(20), 5) >= 3` - The price touched below 20-day EMA at least three times over the last five days.
`close[1] < low[1] + 0.25 * crange[1]` - Yesterday's closing price is in the lower quarter of the candle's range.
`offh_252 > 25` - Price at least 25% off the 252-day high (at least 25% lower than the 252-day highest price)
`offh_all > 50` - Price at least 50% off the all-time high (at least 50% lower than the all-time highest price)
`wick[1] > 0.75 * body[1]` - The wick size of yesterday's candle is at least 75% of the candle's body.
`count(abs(low - ema(20)) < 0.05 * pricerange(50), 5) >= 3` - The low price fell into the 5% EMA corridor at least three times in the last five days. The 5% corridor is calculated using a 50-day price range.
`show(max(if(gapup > 3, 100 * (h - o) / o, 0), 50) as max_growth)` - It adds a custom column with data showing the maximum price increase over the last 50 days (from open to high) on days with at least 3% upward gaps. The column will have "max_growth" heading.
`eps_qtr > 1.2 * eps_qtr[1] and eps_qtr[1] > 1.2 * eps_qtr[2] and eps_qtr[2] > 1.2 * eps_qtr[3] and eps_qtr[3] > 1.2 * eps_qtr[4]` - Quarterly EPS has been growing at least 20% for the last four quarters.
`(net_income_qtr[0] + net_income_qtr[1] + net_income_qtr[2] + net_income_qtr[3]) > 1000` - TTM (Twelve Trailing Months) Net Income above one billion.
`index(dow) and !ticker(trv,mmm)` - Exclude certain symbols from screening.
`nh_10@weekly and !(nh_10@[1..20]@weekly)` - This week makes the 10-week new high, but the stock did not make a 10-week new high any week 1..20 weeks ago.
`exch(nyse, nasdaq) and price > 0.95 * sma(200) and price < 1.05 * sma(200)` - The price is within 5% of the 200-day simple moving average corridor.
`price > ema(200) - 2 * atr(14) and price < ema(200) + 2 * atr(14)` - The price is within 2 x ATR(14) of the 200-day exponential moving average corridor.
`cap < 0.75 * max(cap, 36)@monthly` - The current market capitalization is at least 25% below the 36-month maximum of market capitalization.
`exch(iex) and (rsi(14) bon_up 70)@m15` - The 14-period RSI bounced up from 70 on the 15-minute chart.
`exch(iex) and hour(12,13,14,15,16) and (c > dayhigh@1 and c[1] < dayhigh@2 )@m5` - The price crossed the daily high on the 5-minute chart after 12 noon. "dayhigh@1" in this case indicates the high price of the day recorded one 5-minute bar ago, while "dayhigh@2" indicates the high price of the day recorded two 5-minute bars ago.
`exch(iex) and change(1)@h1 > 10` - The price has risen by at least 10 percent in one bar on the hourly chart.
