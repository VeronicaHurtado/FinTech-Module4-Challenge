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
- Calculation and plotting of the daily returns of all portfolios.
- Calculation and plotting of the cumulative returns for all portfolios.

### Risk analysis
- Creation of a box plot for each of the returns. 
- Calculation of the standard deviation for each portfolio.
- Calculation of the annualised standard deviation.

### Rolling statistics
- Calculation and plotting of the rolling standard deviation for all portfolios, using a 21-day window. 
- Calculation and plotting of the correlation between each stock to determine which portfolios mimic the S&P TSX 60. 
- Calculation and plotting of the 60-day rolling beta between Berkshire Hathaway and the S&P TSX 60.
- Exponentially Weighted Average with a 21-day half-life.

### Sharpe ratios
- Using the daily returns, calculation of the Sharpe ratios and visualisation in a bar plot.
- Analysis to determine whether the algorithmic strategies outperform both the market (S&P TSX 60) and the whales portfolios.

## III. Custom Portfolio
Proposed custom portfolio with stocks BHP, CBA and RIO.

### Data sources
Formulas used to obtain the data via Google Sheets for the different stocks from the ASX:
```
=GOOGLEFINANCE("ASX:BHP","price", DATE(2018,1,1), DATE(2019,12,31), "DAILY")
=GOOGLEFINANCE("ASX:CBA","price", DATE(2018,1,1), DATE(2019,12,31), "DAILY")
=GOOGLEFINANCE("ASX:RIO","price", DATE(2018,1,1), DATE(2019,12,31), "DAILY")
```
