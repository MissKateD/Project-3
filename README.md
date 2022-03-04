# Putting the Rhythm in Algorithym
![hOMEWORK](./AI.png)

## Overview
Created an algorithmic trading model to evaluate the success of the Golden Cross trading strategy. This was applied to MGM Resorts International stock listed on the NYSE, evaluating daily close prices of the date range of January 1st, 2019 through March 3rd, 2022. The purpose of the study was to evaluate a company that has implemented a sportsbook app with which BetMGM is a part of the MGM Resorts International.

## Package Requirements
```
conda create -n algotrading python=3.7 anaconda
conda activate algotrading
conda install -c pyviz hvplot
pip install finta
```
## Analysis Results
This code tests the profitability of a 4 day and a 20 day simple moving average Golden Cross trading strategy.

MGM stock data was pulled using Alpaca API.

```python
# Set the short_window and long window variables
short_window = 4
long_window = 20

# Generate the short and long moving averages
df_close['SMA4'] = df_close['Close'].rolling(window=short_window).mean()
df_close['SMA20'] = df_close['Close'].rolling(window=long_window).mean()
```
![hOMEWORK](./SMA.png)

In the given time period the estimated portfolio value fell from $100,000 to approximately $85,000.

![hOMEWORK](./short.png)

Utilized Logistic Regression to learn the model.
```
