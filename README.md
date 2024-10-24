# BinanceFuturesBot
PHP code of a full-featured bot to trade on the Binance Futures platform using TradingView signal alerts
Developer: Francisco Baddini (Brazilian system engineer and PHP/MySQL developer)

Bot features:
- Work via TradingView webhooks receiving TV alerts and starting a position on Binance Futures trading platform.
- Automatic Stop Loss orders opened together with the entry order.
- Take Profit orders of 2 types: with a fixed TP value or a Trailing Stop TP
- Protection against double entry (to reduce risk)
- Protection against opposite direction signal (closing the current position)
- Configurable limit of simultaneous positions opened
- Stop opening positions when the balance is lower than a personalized amount
- Alerts via email and/or WhatsApp on orders errors, stats and reached limits
- Stores all the positions opened on MySQL database, including Order IDs, Assets, Side, Signals used, Prices, Times and Realized PnLs
- Dashboard with the operations, results and stats

- 
