<i>DISCLAIMER:<br>
This repository is only for informative purpose, i renounce any responsibility regarding this code and trained model causing loss of money during trading on real market.</i>

# Stock-Price-Prediction-by-CNN-LSTM-model
# Stock price prediction : AAPL

<b>Trading strategy</b><br>
Trading chart: Daily<br>
Trade type: LONG<br>
Stock: AAPL<br>
Entry price: High price of our last formed candle in formation<br>
Exit price: Model is trying to predict High price of newly formed candle after our formation was formed. if predicted price is not reached out, calculation of profit/loss is done on close price of trading candle, it means, we do trade only in a day, trade is closed by end of each session.

We are trading AAPL stock, since it is stable company that has been in up-trend from its foundation.

<b>Trading Data</b><br>
We are loading daily data from yahoo finance from year 2000 until end of 2021.

Bellow condition is trying to make sure we are trading in upper trend. Trades will be done only with long position.

<b>Traded formation</b><br>
Condition 1: <i>Last candle high is higher than previous candle high</i><br>
Condition 2: <i>Last candle <b>high</b> is higher than Exponential moving average 4</i><br>
Condition 3: <i>EMA4 is higher than EMA8</i><br>
Condition 4: <i>EMA8 is higher than EMA16</i><br>



We are getting windows from stock dataset, each window has 4 rows (4 candles) representing formation of 3 rows (formation) + 1 row (label).Our above condition is using only 1st two candles from formation, however model will be trained on 3 candles

<b>Trading performance</b><br>
On validation dataset (from 8.2018 - 12.2021, cca 3 years and 4 months) model achieved 28% return, also there must be pointed out, the model does not subtract trading fees, so, the return 28% must be decreased by amounth broker is charging per each trade.

<b>Trading formation sample</b>

<img src="AAPL Formation.jpg" width=600 height=500 align="left">
