---
trigger: always_on
---

# General

`cap` - Market Capitalization, millions - cap > 100  Market Capitalization is greater than 100 million
`shares_out` - Shares Outstanding, millions - shares_out > 100  Shares Outstanding is greater than 100 million
`float_shares` - Float Shares, millions - float_shares > 100  Float Shares is greater than 100 million
`eps` - Earnings Per Share - eps > 5  EPS is greater than 5
`pe` - Price / Earnings ratio - pe < 15
`roe` - Return on Equity, % - roe > 15  Return on Equity is greater than 15%
`roa` - Return on Assets, % - roa > 15  Return on Assets is greater than 15%
`roic` - Return on Invested Capital, % - roic > 15  Return on Invested Capital is greater than 15%
`revenue` - Revenue, millions - revenue > 10000  Revenue is greater than ten billion
`rps` - Revenue Per Share - rps > 5  Revenue Per Share is greater than 5
`ebitda` - EBITDA, millions; Earnings Before Interest, Taxes, Depreciation and Amortization (millions) - ebitda > 10000  EBITDA is greater than ten billion
`enterprise_ebitda` - Enterprise Value / EBITDA ratio - enterprise_ebitda < 25
`enterprise_ebit` - Enterprise Value / EBIT ratio - enterprise_ebit < 25
`enterprise_revenue` - Enterprise Value / Revenue ratio - enterprise_revenue < 25
* Fundamental indicators are calculated based on Trailing Twelve Months data

# Financial Ratios

`leverage_ratio` - Leverage Ratio - leverage_ratio < 5
`current_ratio` - Current Ratio - current_ratio > 1
`interest_cover` - Interest Coverage Ratio - interest_cover > 5
`price_book_ratio` - Price / Book Ratio - price_book_ratio < 50
`price_tangible_book_ratio` - Price / Tangible Book Ratio - price_tangible_book_ratio < 50
`price_cash_ratio` - Price / Cash Flow Ratio - price_cash_ratio < 30
`price_free_cash_ratio` - Price / Free Cash Flow Ratio - price_free_cash_ratio < 30
`debt_equity_ratio` - Debt / Equity Ratio - debt_equity_ratio < 2
`price_sales_ratio` - Price / Sales Ratio - price_sales_ratio < 10
`ptpm` - Pre-Tax Profit Margin, % - ptpm > 25  Pre-Tax Profit Margin is greater than 25%
`peg_ratio` - PEG Ratio, 5-year expected - peg_ratio < 5
* Fundamental indicators are calculated based on Trailing Twelve Months data

# Financial Strength indicators

`altman_z_score` - Altman Z-Score - altman_z_score > 3
`piotroski_f_score` - Piotroski F-Score - piotroski_f_score >= 7
`beneish_m_score` - Beneish M-Score - beneish_m_score < -2.22
`price_intrinsic_ratio` - Price to Intrinsic Value ratio. For the Intrinsic Value calculation, the Free Cash Flow valuation model is used. - price_intrinsic_ratio < 1  Price to Intrinsic Value is less than 1. It means the stock's price is less than its intrinsic value. Thus, in this example, we want to find undervalued stocks.
`price_lynch_ratio` - Price to Peter Lynch Fair Value ratio - price_lynch_ratio < 1  Price to Lynch Fair Value is less than 1. It means the stock's price is less than its Lynch Fair Value. Thus, in this example, we want to find undervalued stocks.
`price_graham_ratio` - Price to Graham Number ratio - price_graham_ratio < 1  Price to Graham Number is less than 1. It means the stock's price is less than its Graham Number. Thus, in this example, we want to find undervalued stocks.
`shiller_pe_ratio` - Shiller P/E Ratio (a.k.a. CAPE) - shiller_pe_ratio < 15
`target` - 1-year target price, analysts estimated - target > 1.2 * price  1-year target price is at least 20% higher than the current price
* Fundamental indicators are calculated based on Trailing Twelve Months data

# Demand and supply

`short_ratio` - Short Ratio; the number of shares of a security that investors have sold short divided by average daily volume of the security - short_ratio < 2
`short_perc` - Short % of Float; percentage of shares that short-sellers have borrowed from the float - short_perc < 5  Short % of Float is less than 5%

# To industry ratios

`tip_eps` - EPS to Industry Average, % - tip_eps > 100  EPS to industry average ratio is greater than 100%. In this example, we want to find stocks with EPS above the industry average.
`tip_pe` - P/E to Industry Average, % - tip_pe < 100  P/E to industry average ratio is less than 100%. In this example, we want to find stocks with EPS below the industry average.
`tip_roe` - ROE to Industry Average, % - tip_roe > 200  ROE to industry average ratio is greater than 200%. In this example, we want to find stocks with ROE at least twice above the industry average.
`tip_price_book_ratio` - Price/Book to Industry Average, % - tip_price_book_ratio < 100
`tip_price_sales_ratio` - Price/Sales to Industry Average, % - tip_price_sales_ratio < 100
`tip_price_cash_ratio` - Price/Cash to Industry Average, % - tip_price_cash_ratio < 100
`tip_debt_equity_ratio` - Debt/Equity to Industry Average, % - tip_debt_equity_ratio < 100
`tip_ptpm` - Pre-Tax Profit Margin to Industry Average, % - tip_ptpm > 100
`tip_revenue` - Revenue to Industry Average, % - tip_revenue > 100
`tip_ebitda` - EBITDA to Industry Average, % - tip_ebitda > 100
`tip_price` - Price to Industry Average, % - tip_price < 100

# Dividend

`dps` - Dividend per Share - dps > 10
`dvd_yield` - Dividend Yield - dvd_yield > 2
`dvd_payout_ratio` - Dividend Payout Ratio - dvd_payout_ratio > 30

# Quarterly data

`eps_qtr` - Earnings Per Share (mrq) - eps_qtr > 5  The most recent quarter's EPS is greater than 5
`net_income_qtr` - Net Income (mrq), millions - net_income_qtr > 10000  The most recent quarter's Net Income is greater than ten billion
`ev_qtr` - Enterprise Value (mrq), millions - ev_qtr > 10000  The most recent quarter's Enterprise Value is greater than ten billion
`ebitda_qtr` - EBITDA (mrq), millions - ebitda_qtr > 10000  The most recent quarter's EBITDA is greater than ten billion
`ebit_qtr` - EBIT (mrq), millions - ebit_qtr > 10000  The most recent quarter's EBIT is greater than ten billion
`revenue_qtr` - Revenue (mrq), millions - revenue_qtr > 10000  The most recent quarter's Revenue is greater than ten billion
`rps_qtr` - Revenue Per Share (mrq) - rps_qtr > 5  The most recent quarter's Revenue Per Share is greater than 5
`roe_qtr` - Return On Equity (mrq), % - roe_qtr > 15  The most recent quarter's Return On Equity is greater than 15%
`roa_qtr` - Return On Assets (mrq), % - roa_qtr > 15  The most recent quarter's Return On Assets is greater than 15%
`roic_qtr` - Return On Invested Capital (mrq), % - roic_qtr > 15  The most recent quarter's Return On Invested Capital is greater than 15%
`free_cash_flow_qtr` - Free Cash Flow (mrq), millions - free_cash_flow_qtr > 10000  The most recent quarter's Free Cash Flow is greater than ten billion
`debt_equity_qtr` - Debt / Equity Ratio (mrq) - debt_equity_qtr < 2  The most recent quarter's Debt / Equity Ratio is less than 2
`buyback_yield_qtr` - Buyback Yield (mrq), % - buyback_yield_qtr > 3  The most recent quarter's Buyback Yield is greater than 3%
`bvps_qtr` - Book Value Per Share (mrq) - bvps_qtr > 10  The most recent quarter's Book Value Per Share is greater than 10
`ffo_qtr` - Funds From Operations (mrq), millions - ffo_qtr > 10  The most recent quarter's Funds From Operations is greater than 10 (Applicable to REITs only)
`shares_out_qtr` - Shares Outstanding (mrq), millions - shares_out_qtr > 100000  The most recent quarter's Shares Outstanding is greater than 100 billion
`price_qtr` - Share Price - price_qtr > 100  Share Price is greater than 100. The value corresponds to the quarterly reporting period's last day's closing price.
* You can also refer to the previous quarter's data using the appropriate array index. For example, eps_qtr[0] or simply eps_qtr stands for the most recent quarter's data, eps_qtr[1] means previous quarter's data, eps_qtr[2] means pre-previous quarter's data, and so on.

# Year-Over-Year performance

`eps_yoy` - YOY EPS Growth, % - eps_yoy > 20  Year-over-year Earnings Per Share growth is greater than 20%
`net_income_yoy` - YOY Net Income Growth, % - net_income_yoy > 20  Year-over-year Net Income growth is greater than 20%
`ebitda_yoy` - YOY EBITDA Growth, % - ebitda_yoy > 20  Year-over-year EBITDA growth is greater than 20%
`ebit_yoy` - YOY EBIT Growth, % - ebit_yoy > 20  Year-over-year EBIT growth is greater than 20%
`revenue_yoy` - YOY Revenue Growth, % - revenue_yoy > 20  Year-over-year Revenue growth is greater than 20%
`rps_yoy` - YOY RPS Growth, % - rps_yoy > 20  Year-over-year Revenue Per Share growth is greater than 20%
`roic_yoy` - YOY ROIC Growth, % - roic_yoy > 10  Year-over-year ROIC growth is greater than 10%
`free_cash_flow_yoy` - YOY Free Cash Flow Growth, % - free_cash_flow_yoy > 10  Year-over-year Free Cash Flow growth is greater than 10%
`bvps_yoy` - YOY Book Value Per Share Growth, % - bvps_yoy > 10  Year-over-year Book Value Per Share growth is greater than 10%
`ffo_yoy` - YOY Funds From Operations Growth, % - ffo_yoy > 10  Year-over-year Funds From Operations growth is greater than 10% (Applicable to REITs only)
* Year-over-year performance is calculated by comparing the most recent quarter's data to the same quarter's previous year's data.  ** You can also refer to the previous quarter's year-over-year data using the appropriate array index. For example, eps_yoy[0] or simply eps_yoy stands for the most recent quarter's year-over-year performance, eps_yoy[1] means the previous quarter's year-over-year performance, eps_yoy[2] means pre-previous quarter's year-over-year performance, and so on.

# Quarter-Over-Quarter performance

`eps_qoq` - QOQ EPS Growth, % - eps_qoq > 10  Quarter-over-quarter Earnings Per Share growth is greater than 10%
`net_income_qoq` - QOQ Net Income Growth, % - net_income_qoq > 10  Quarter-over-quarter Net Income growth is greater than 10%
`ebitda_qoq` - QOQ EBITDA Growth, % - ebitda_qoq > 10  Quarter-over-quarter EBITDA growth is greater than 10%
`ebit_qoq` - QOQ EBIT Growth, % - ebit_qoq > 10  Quarter-over-quarter EBIT growth is greater than 10%
`revenue_qoq` - QOQ Revenue Growth, % - revenue_qoq > 10  Quarter-over-quarter Revenue growth is greater than 10%
`rps_qoq` - QOQ RPS Growth, % - rps_qoq > 10  Quarter-over-quarter Revenue Per Share growth is greater than 10%
`roic_qoq` - QOQ ROIC Growth, % - roic_qoq > 10  Quarter-over-quarter ROIC growth is greater than 10%
`free_cash_flow_qoq` - QOQ Free Cash Flow Growth, % - free_cash_flow_qoq > 10  Quarter-over-quarter Free Cash Flow growth is greater than 10%
`bvps_qoq` - QOQ Book Value Per Share Growth, % - bvps_qoq > 10  Quarter-over-quarter Book Value Per Share growth is greater than 10%
`ffo_qoq` - QOQ Funds From Operations Growth, % - ffo_qoq > 10  Quarter-over-quarter Funds From Operations growth is greater than 10% (Applicable to REITs only)
* Quarter-over-quarter performance is calculated by comparing the most recent quarter data to the previous quarter's data.  ** You can also refer to the previous quarter's Quarter-over-quarter performance using the appropriate array index. For example, eps_qoq[0] or simply eps_qoq stands for the most recent quarter's Quarter-over-quarter performance, eps_qoq[1] means the previous quarter's Quarter-over-quarter performance, eps_qoq[2] means pre-previous quarter's Quarter-over-quarter performance, and so on.

# Annual data

`eps_y` - Earnings Per Share - eps_y > 15  Last fiscal year's Earnings Per Share is greater than 15
`net_income_y` - Net Income, millions - net_income_y > 50000  Last fiscal year's Net Income is greater than fifty billion
`ebitda_y` - EBITDA, millions - ebitda_y > 50000  Last fiscal year's EBITDA is greater than fifty billion
`ebit_y` - EBIT, millions - ebit_y > 50000  Last fiscal year's EBIT is greater than fifty billion
`ev_y` - Enterprise Value, millions - ev_y > 100000  Last fiscal year's Enterprise Value is greater than 100 billion
`revenue_y` - Revenue, millions - revenue_y > 50000  Last fiscal year's Revenue is greater than fifty billion
`rps_y` - Revenue Per Share - rps_y > 15  Last fiscal year's Revenue Per Share is greater than 15
`roe_y` - Return On Equity, % - roe_y > 15  Last fiscal year's Return On Equity is greater than 15%
`roa_y` - Return On Assets, % - roa_y > 15  Last fiscal year's Return On Assets is greater than 15%
`roic_y` - Return On Invested Capital, % - roic_y > 15  Last fiscal year's Return On Invested Capital is greater than 15%
`free_cash_flow_y` - Free Cash Flow, millions - free_cash_flow_y > 10000  Last fiscal year's Free Cash Flow is greater than ten billion
`debt_equity_y` - Debt / Equity Ratio - debt_equity_y < 2  Last fiscal year's Debt / Equity Ratio is less than 2
`bvps_y` - Book Value Per Share - bvps_y > 50  Last fiscal year's Book Value Per Share is greater than 50
`ffo_y` - Funds From Operations, millions - ffo_y > 10  Last fiscal year's Funds From Operations is greater than 10 million (Applicable to REITs only)
`buyback_yield_y` - Buyback Yield, % - buyback_yield_y > 3  Last fiscal year's Buyback Yield is greater than 3%
`dvd_yield_y` - Dividend Yield, % - dvd_yield_y > 2  Last fiscal year's Dividend Yield is greater than 2%
`dpr_y` - Dividend Payout Ratio, % - dpr_y > 20  Last fiscal year's Dividend Payout Ratio is greater than 20%
`shares_out_y` - Shares Outstanding, millions - shares_out_y > 100000  Last fiscal year's Shares Outstanding is greater than 100 billion
`price_y` - Share Price - price_y > 100  Share Price is greater than 100. The value corresponds to the annual reporting period's last day's closing price.
* You can also refer to the previous fiscal year's data using the appropriate array index. For example, eps_y[0] or simply eps_y stands for the most recent fiscal year's data, eps_y[1] means previous fiscal year's data, eps_y[2] means pre-previous fiscal year's data, and so on.

# 5-Year Annual Growth (CAGR)

`eps_5y_growth` - Earnings Per Share 5-Year Annual Growth, % - eps_5y_growth > 20  Earnings Per Share 5-year compound annual growth rate is greater than 20%
`net_income_5y_growth` - Net Income 5-Year Annual Growth, % - net_income_5y_growth > 20  Net Income 5-year compound annual growth rate is greater than 20%
`ebitda_5y_growth` - EBITDA 5-Year Annual Growth, % - ebitda_5y_growth > 20  EBITDA 5-year compound annual growth rate is greater than 20%
`ebit_5y_growth` - EBIT 5-Year Annual Growth, % - ebit_5y_growth > 20  EBIT 5-year compound annual growth rate is greater than 20%
`ev_5y_growth` - Enterprise Value 5-Year Annual Growth, % - ev_5y_growth > 20  Enterprise Value 5-year compound annual growth rate is greater than 20%
`revenue_5y_growth` - Revenue 5-Year Annual Growth, % - revenue_5y_growth > 20  Revenue 5-year compound annual growth rate is greater than 20%
`rps_5y_growth` - Revenue Per Share 5-Year Annual Growth, % - rps_5y_growth > 20  Revenue Per Share 5-year compound annual growth rate is greater than 20%
`roe_5y_growth` - Return On Equity 5-Year Annual Growth, % - roe_5y_growth > 20  Return On Equity 5-year compound annual growth rate is greater than 20%
`roa_5y_growth` - Return On Assets 5-Year Annual Growth, % - roa_5y_growth > 20  Return On Assets 5-year compound annual growth rate is greater than 20%
`roic_5y_growth` - Return On Invested Capital 5-Year Annual Growth, % - roic_5y_growth > 20  Return On Invested Capital 5-year compound annual growth rate is greater than 20%
`free_cash_flow_5y_growth` - Free Cash Flow 5-Year Annual Growth, % - free_cash_flow_5y_growth > 20  Free Cash Flow 5-year compound annual growth rate is greater than 20%
`bvps_5y_growth` - Book Value Per Share 5-Year Annual Growth, % - bvps_5y_growth > 20  Book Value Per Share 5-year compound annual growth rate is greater than 20%
`ffo_5y_growth` - Funds From Operations 5-Year Annual Growth, % - ffo_5y_growth > 20  Funds From Operations 5-year compound annual growth rate is greater than 20% (Applicable to REITs only)
`debt_equity_5y_growth` - Debt / Equity Ratio 5-Year Annual Growth, % - debt_equity_5y_growth > 20  Debt / Equity Ratio 5-year compound annual growth rate is greater than 20%
`buyback_yield_5y_growth` - Buyback Yield 5-Year Annual Growth, % - buyback_yield_5y_growth > 20  Buyback Yield 5-year compound annual growth rate is greater than 20%
`dvd_yield_5y_growth` - Dividend Yield 5-Year Annual Growth, % - dvd_yield_5y_growth > 20  Dividend Yield 5-year compound annual growth rate is greater than 20%
`dpr_5y_growth` - Dividend Payout Ratio 5-Year Annual Growth, % - dpr_5y_growth > 20  Dividend Payout Ratio 5-year compound annual growth rate is greater than 20%
`shares_out_5y_growth` - Shares Outstanding 5-Year Annual Growth, % - shares_out_5y_growth > 20  Shares Outstanding 5-year compound annual growth rate is greater than 20%
* You can also refer to the previous fiscal year's 5-Year Annual Growth data using the appropriate array index. For example, eps_5y_growth[0] or simply eps_5y_growth stands for the most recent fiscal year's EPS 5-Year Annual Growth, eps_5y_growth[1] means previous fiscal year's EPS 5-Year Annual Growth, eps_5y_growth[2] means pre-previous fiscal year's EPS 5-Year Annual Growth, and so on.

# 5-Year Averages 

`eps_5y_avg` - Earnings Per Share 5-Year Average - eps_5y_avg > 15  Earnings Per Share 5-year average is greater than 15
`net_income_5y_avg` - Net Income 5-Year Average - net_income_5y_avg > 50000  Net Income 5-year average is greater than fifty billion
`ebitda_5y_avg` - EBITDA 5-Year Average - ebitda_5y_avg > 50000  EBITDA 5-year average is greater than fifty billion
`ebit_5y_avg` - EBIT 5-Year Average - ebit_5y_avg > 50000  EBIT 5-year average is greater than fifty billion
`ev_5y_avg` - Enterprise Value 5-Year Average - ev_5y_avg > 100000  Enterprise Value 5-year average is greater than 100 billion
`revenue_5y_avg` - Revenue 5-Year Average - revenue_5y_avg > 50  Revenue 5-year average is greater than fifty billion
`rps_5y_avg` - Revenue Per Share 5-Year Average - rps_5y_avg > 15  Revenue Per Share 5-year average is greater than 15
`roe_5y_avg` - Return On Equity 5-Year Average - roe_5y_avg > 20  Return On Equity 5-year average is greater than 20%
`roa_5y_avg` - Return On Assets 5-Year Average - roa_5y_avg > 20  Return On Assets 5-year average is greater than 20%
`roic_5y_avg` - Return On Invested Capital 5-Year Average - roic_5y_avg > 20  Return On Invested Capital 5-year average is greater than 20%
`free_cash_flow_5y_avg` - Free Cash Flow 5-Year Average - free_cash_flow_5y_avg > 100000  Free Cash Flow 5-year average is greater than 100 billion
`bvps_5y_avg` - Book Value Per Share 5-Year Average - bvps_5y_avg > 50  Book Value Per Share 5-year average is greater than 50
`ffo_5y_avg` - Funds From Operations 5-Year Average - ffo_5y_avg > 50  Funds From Operations 5-year average is greater than fifty million
`debt_equity_5y_avg` - Debt / Equity Ratio 5-Year Average - debt_equity_5y_avg < 2  Debt / Equity Ratio 5-year average is less than 2
`buyback_yield_5y_avg` - Buyback Yield 5-Year Average - buyback_yield_5y_avg > 3  Buyback Yield 5-year average is greater than 3%
`dvd_yield_5y_avg` - Dividend Yield 5-Year Average - dvd_yield_5y_avg > 2  Dividend Yield 5-year average is greater than 2%
`dpr_5y_avg` - Dividend Payout Ratio 5-Year Average - dpr_5y_avg > 20  Dividend Payout Ratio 5-year average is greater than 20%
`shares_out_5y_avg` - Shares Outstanding 5-Year Average - shares_out_5y_avg > 100000  Shares Outstanding 5-year average is greater than 100 billion
* You can also refer to the previous fiscal year's 5-Year Average data using the appropriate array index. For example, eps_5y_avg[0] or simply eps_5y_avg stands for the most recent fiscal year's EPS 5-Year Average, eps_5y_avg[1] means previous fiscal year's EPS 5-Year Average, eps_5y_avg[2] means pre-previous fiscal year's EPS 5-Year Average, and so on.
