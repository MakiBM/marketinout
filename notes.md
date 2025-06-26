exch(nyse, nasdaq) 
and cap > 1000
and range(60) <= 5
and highest(20) <= highest(20)@20 *1.05 and highest(20) >= highest(20)@20 *0.95
and highest(20) <= highest(20)@40 *1.05 and highest(20) >= highest(20)@40 *0.95
and highest(20) <= highest(20)@60 *1.05 and highest(20) >= highest(20)@60 *0.95
and lowest(20) <= lowest(20)@20 *1.05 and lowest(20) >= lowest(20)@20 *0.95
and lowest(20) <= lowest(20)@40 *1.05 and lowest(20) >= lowest(20)@40 *0.95
and lowest(20) <= lowest(20)@60 *1.05 and lowest(20) >= lowest(20)@60 *0.95
and hist(06/24/2025)


exch(nyse, nasdaq) 
and cap > 1000
and range(60) <= 5
and highest(20) / highest(20)@20 <= (1 + (0.2 * range(60)/100)) and highest(20) / highest(20)@20 >= (1 - (0.2 * range(60)/100))
and highest(20) / highest(20)@40 <= (1 + (0.2 * range(60)/100)) and highest(20) / highest(20)@40 >= (1 - (0.2 * range(60)/100))
and highest(20) / highest(20)@60 <= (1 + (0.2 * range(60)/100)) and highest(20) / highest(20)@60 >= (1 - (0.2 * range(60)/100))
and lowest(20) / lowest(20)@20 <= (1 + (0.2 * range(60)/100)) and lowest(20) / lowest(20)@20 >= (1 - (0.2 * range(60)/100))
and lowest(20) / lowest(20)@40 <= (1 + (0.2 * range(60)/100)) and lowest(20) / lowest(20)@40 >= (1 - (0.2 * range(60)/100))
and lowest(20) / lowest(20)@60 <= (1 + (0.2 * range(60)/100)) and lowest(20) / lowest(20)@60 >= (1 - (0.2 * range(60)/100))
and hist(06/24/2025)



exch(nyse, nasdaq) 
and cap > 1000
and range(60) <= 20
and range(20) >= range(60) * 0.5
and range(20)@20 >= range(60) * 0.5
and range(20)@40 >= range(60) * 0.5
and highest(60) = price
and !(highest(60)@1 = price@1)
and hist(06/24/2024)

stopat(lowest(60))
and takeat(highest(60) + (highest(60) - lowest(60)))

Dow
SP500
NYSE Composite
Nasdaq Composite
Nasdaq 100
Russell 1000
Russell 2000
Russell 3000
Russell Midcap
Russell Microcap
TSX
FTSE 100
FTSE 250
FTSE All Share
DAX
ASX 50
ASX 200
ASX All Ords
Hang Seng
Straits Times
KLCI
Nifty 50
Nifty Next 50
Nifty 200
Nifty 500