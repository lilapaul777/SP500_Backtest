**S&P 500 Moving Average Crossover Backtest**

This notebook tests a popular trading strategy, the 50/200 day moving average crossover, on the S&P 500 (using the SPY ETF) and compares it to just buying and holding. The data covers about ten years, from January 2016 to January 2026.

**What it does**

Downloads roughly 10 years of daily SPY prices from Yahoo Finance with yfinance
Calculates the 50-day and 200-day moving averages and plots them against price
Sets up the strategy: hold the S&P 500 when the 50-day MA is above the 200-day MA, move to cash when it drops below. Positions are shifted by one day so the strategy only uses information it would have actually had at the time.
Runs the backtest and tracks the growth of $1 for both the strategy and buy and hold
Compares total return and annualized Sharpe ratio (assuming a risk-free rate of 0) for both


**Results**

Buy and hold wins over this period.

MetricBuy & HoldMoving Average StrategyGrowth of $1~$4.00~$2.50Total Return~3.00 (300%)~1.55 (155%)Sharpe RatioHigherLower

The crossover strategy loses on both raw and risk-adjusted returns. Trading costs and taxes aren't even included here, and since the strategy trades while buy and hold doesn't, adding them would only make it look worse.

**Caveats**

2016 to 2026 was mostly one long bull market, which is exactly the environment where staying invested wins. A sample with a real bear market in it could look different.
The strategy is flat for the first 200 trading days while the long moving average builds up.
No transaction costs, slippage, or taxes are modeled.
The Sharpe ratio assumes a risk-free rate of 0.

**Requirements**

pandas
numpy
yfinance
matplotlib

Install with:

bashpip install pandas numpy yfinance matplotlib

**Usage**

Open SP500_Backtest.ipynb in Jupyter or Google Colab and run the cells top to bottom. The notebook pulls fresh data from Yahoo Finance every run, so numbers may shift slightly over time.
