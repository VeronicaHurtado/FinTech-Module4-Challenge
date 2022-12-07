# FinTech-Module4-Challenge

The aim of this tool is to evaluate a number of portfolios and select the portfolio that is performing the best across 
multiple areas: volatility, returns, risk, and Sharpe ratios.

The code is presented in a Jupyter Lab notebook that uses quantitative analysis techniques to assess the historical 
daily returns of the portfolios.

The data provided for comparison includes: the historical **daily returns** for some algorithmic portfolios from a simulated 
company `algo_returns.csv`, the historical **daily returns** from a representation of the portfolios of famous "whale" 
investors like Warren Buffett `whale_returns.csv`, and the **closing prices** for the S&P/TSX 60 Index (60 large companies 
listed on the Toronto Stock Exchange) `sp_tsx_history.csv`.

Additionally, a Custom portfolio of stocks is proposed, and then compared with the aforementioned portfolios to determine
which of them is performing the best. The historical closing prices for the Custom portfolio has been obtained using the 
GOOGLEFINANCE formula in Google Sheets.

## I. Data Preparation
The following operations were required to obtain clean, useful and comparable data:
- Removal of null values.
- Removal of any non-numeric values (e.g., dollar signs).
- Data types conversion.
- Conversion of closing prices to daily returns, where applicable.

## II. Quantitative Analysis
Analysis of the portfolios to determine if any of them could outperform the "S&P TSX 60" stock market.

### Performance analysis
- Calculate and plot daily returns of all portfolios.
- Calculate and plot cumulative returns for all portfolios. Does any portfolio outperform the S&P TSX 60?

### Risk analysis
- Create a box plot for each of the returns. 
- Calculate the standard deviation for each portfolio. 
- Determine which portfolios are riskier than the S&P TSX 60. 
- Calculate the annualised standard deviation.

### Rolling statistics
- Calculate and plot the rolling standard deviation for all portfolios, using a 21-day window. 
- Calculate and plot the correlation between each stock to determine which portfolios mimic the S&P TSX 60. 
- Choose one portfolio, then calculate and plot the 60-day rolling beta between that portfolio and the S&P TSX 60.
- Exponentially Weighted Average with a 21-day half-life.

### Sharpe ratios
Investment managers and their institutional investors look at the return-to-risk ratio, not just the returns.
- Using the daily returns, calculate the Sharpe ratios and visualise them in a bar plot.
- Determine whether the algorithmic strategies outperform both the market (S&P TSX 60) and the whales portfolios.

## III. Custom Portfolio

### Data sources
Formulas used to obtain the data via Google Sheets for the different stocks from the ASX:
```
=GOOGLEFINANCE("ASX:BHP","price", DATE(2018,1,1), DATE(2019,12,31), "DAILY")
=GOOGLEFINANCE("ASX:CBA","price", DATE(2018,1,1), DATE(2019,12,31), "DAILY")
=GOOGLEFINANCE("ASX:RIO","price", DATE(2018,1,1), DATE(2019,12,31), "DAILY")
```
