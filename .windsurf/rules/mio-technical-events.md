---
trigger: always_on
---

# List of Technical Events

The following table contains the complete list of technical events that can be used in a formula expression. They can also be viewed using the Formula Expression Helper pane below the formula editing text area. Technical events serve to build stock screening criteria. You can view examples of technical criteria on charts here. In the examples below, macds, slowk, and slowd stands for MACD Signal Line, Stochastic %K line, and Stochastic %D line correspondingly. You can view the complete list of supported indicators and lines on the Technical Indicators help page.

`ca` - Crossed Above
price ca ema(50)
ema(7) ca ema(50)
rsi(14) ca 80
macd(12,26,9) ca macds(12,26,9)
slowk(14,3,3) ca slowd(14,3,3)

`cb` - Crossed Below
price cb ema(50)
ema(7) cb ema(50)
rsi(14) cb 20
macd(12,26,9) cb macds(12,26,9)
slowk(14,3,3) cb slowd(14,3,3)

`>` - Is Above
price > 10
price > ema(50)
ema(7) > ema(50)
rsi(14) > 80
macd(12,26,9) > macds(12,26,9)
slowk(14,3,3) > slowd(14,3,3)

`<` - Is Below
price < 100
price < ema(50)
ema(7) < ema(50)
rsi(14) < 20
macd(12,26,9) < macds(12,26,9)
slowk(14,3,3) < slowd(14,3,3)

`tocha` - Touched Above
price tocha ema(50)
ema(7) tocha ema(50)
rsi(14) tocha smarsi(14,9)
macd(12,26,9) tocha macds(12,26,9)
slowk(14,3,3) tocha slowd(14,3,3)

`tochb` - Touched Below
price tochb ema(50)
ema(7) tochb ema(50)
rsi(14) tochb smarsi(14,9)
macd(12,26,9) tochb macds(12,26,9)
slowk(14,3,3) tochb slowd(14,3,3)

`bon_up` - Bounced Up From
price bon_up ema(50)
ema(7) bon_up ema(50)
rsi(14) bon_up smarsi(14,9)
macd(12,26,9) bon_up macds(12,26,9)
slowk(14,3,3) bon_up slowd(14,3,3)

`bon_dn` - Bounced Down From
price bon_dn ema(50)
ema(7) bon_dn ema(50)
rsi(14) bon_dn smarsi(14,9)
macd(12,26,9) bon_dn macds(12,26,9)
slowk(14,3,3) bon_dn slowd(14,3,3)

`div_bull` - Bullish Divergence
rsi(14) div_bull
macd(12,26,9) div_bull
stoch(14,3,3) div_bull

`div_bear` - Bearish Divergence
rsi(14) div_bear
macd(12,26,9) div_bear
stoch(14,3,3) div_bear

`trend_up` - Trending Up over the specified number of days/bars
price trend_up 20
ema(7) trend_up 20
rsi(14) trend_up 7
macd(12,26,9) trend_up 7
stoch(14,3,3) trend_up 7

`trend_dn` - Trending Down over the specified number of days/bars
price trend_dn 20
ema(7) trend_dn 20
rsi(14) trend_dn 7
macd(12,26,9) trend_dn 7
stoch(14,3,3) trend_dn 7

`new_high` - New High over the specified number of days/bars
price new_high 10
ema(7) new_high 10
rsi(14) new_high 10
macd(12,26,9) new_high 10
stoch(14,3,3) new_high 10

`new_low` - New Low over the specified number of days/bars
price new_low 10
ema(7) new_low 10
rsi(14) new_low 10
macd(12,26,9) new_low 10
stoch(14,3,3) new_low 10