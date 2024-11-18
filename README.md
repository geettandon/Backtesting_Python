# Project Overview: Intraday Backtesting with ABC Strategy
This project focuses on backtesting an intraday trading strategy in the stock market using a custom ABC strategy. The ABC strategy is built around technical indicators like the Moving Average, Bollinger Bands, and candlestick patterns, applied on a 5-minute candlestick chart. The goal is to test the viability of this strategy when it comes to making buy-only trades in the market.

## ABC Strategy Breakdown
_A_ stands for the Simple Moving Average (SMA), where we specifically use the 50-period SMA. For a valid trade signal, this SMA must be trending upward for at least the last 10 candlesticks.

_B_ stands for the Bollinger Bands (BB), with a focus on the lower Bollinger Band. A buy signal is only considered if the lower BB is positioned near the 50-period SMA line. This confluence between the 50 SMA and the lower Bollinger Band acts as a zone of interest for entering a trade.

_C_ stands for Candlestick Patterns. We look for a clear buying candle that forms near the aforementioned zone of interest. Once this candle’s high is broken, it triggers the buy entry, with the stop-loss placed at the lower of either the buying candle’s low or the previous candle’s low.

## Trade Parameters
1. _Entry Signal_: A buy order is placed when the high of a confirmed buying candle breaks after the 50 SMA and lower Bollinger Band converge.
2. _Stop-Loss_: The stop-loss is set at the lower of the buying candle’s low or the previous candle’s low.
3. _Target_: A risk-to-reward ratio of 1:2 is used, aiming to capture twice the distance of the stop-loss as profit.
