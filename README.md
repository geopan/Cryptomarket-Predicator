# Cryptomarket Predicator

# Run with jupyter

1. Run `./src/data-pre-processing.ipynb`

Change parameters sa below:

```python
# Currency use in comparison to Bitcoin.
currency = 'ETH'
# Time Interval (oneMin, fiveMin, halfHour, hour, day...).
tickInterval = 'fiveMin'
# Row limit to process.
limit = 2000
```

2. Run `./src/prediction.ipynb`

# Data

The main component in any **Market prediction** problem is the **price**. But
this time we also need another 3 features. It's suggested to use some textual
features but following Siraj's advice "Be creative, good luck!", we are going to
use **three popular technical indicators** that (hopefully) will help the model
predict the price (as they help human traders to do the same task).

## Technical Indicators

There are A LOT of different technical indicators for market analysis. The
universe of "technical analysis" for trading is vast. Most of it is out of our
scope, so we're just going to present three simple technical indicators, each
specialized in a different task.

### Trend indicator

[What is Trend?](http://www.investopedia.com/university/technical/techanalysis3.asp)

#### MACD

The Moving Average Convergence/Divergence oscillator (MACD) is one of the
simplest and most effective momentum indicators available. The MACD turns two
trend-following indicators, moving averages, into a momentum oscillator by
subtracting the longer moving average from the shorter moving average.

### Momentum indicator

[What is Momentum?](http://www.investopedia.com/terms/m/marketmomentum.asp)

#### Stochastics Oscillator

The Stochastic Oscillator is a momentum indicator that shows the location of the
close relative to the high-low range over a set number of periods.

### Volume indicator

[What is Volume?](http://www.investopedia.com/terms/v/volume.asp)

#### Average True Range

Is an indicator to measure the volalitility (NOT price direction). The largest
of:

* Method A: Current High less the current Low
* Method B: Current High less the previous Close (absolute value)
* Method C: Current Low less the previous Close (absolute value)

# Model

## Recurrent Neural Network

A (more appropiate) recurrent neural network model. Details in the corresponding
Notebook "./src/prediction.ipynb"

## Results

### Price vs Prediction w/ Recurrent Neural Network

<img src="./result/BTC-ETH-PriceVsPrediction.png?raw=true">

## Dependencies

* jupyter
* json
* urllib (for fetching data)
* matplotlib (for plotting)
* pandas (for dataset manipulation)
* numpy
* tensorflow

### References

* [SirajsCodingChallenges by Alberto Blanco Garcés](https://github.com/alberduris/SirajsCodingChallenges)
* [Technical Analysis - The use of Trend - Investopedia](http://www.investopedia.com/university/technical/techanalysis3.asp)
* [Momentum Market - Investopedia](http://http://www.investopedia.com/terms/m/marketmomentum.asp)
* [Volume - Investopedia](http://www.investopedia.com/terms/v/volume.asp)
* [Siraj Raval - Youtube - Quantum Computing - The Math of Intelligence #10](https://www.youtube.com/watch?v=LhtnECml-KI)
* [A simple deep learning model for stock price prediction using TensorFlow](https://medium.com/mlreview/a-simple-deep-learning-model-for-stock-price-prediction-using-tensorflow-30505541d877)
