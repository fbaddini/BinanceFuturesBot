# BinanceFuturesBot
PHP code of a full-featured bot to trade on the Binance Futures platform using TradingView signal alerts

Developer: Francisco Baddini | Version: 1.0 | Based on PHP Binance API Library from Jon Eyrick (the library was adapted to the Futures platform) - Thanks Jon!

Bot features:
- Works via TradingView webhooks receiving TV alerts and starting a position on Binance Futures trading platform. Can work with other trading platforms that support sending JSON messages to a webhook (not tested).
- Automatic Stop Loss orders opened together with the entry order.
- Take Profit orders of 2 types: with a fixed TP value or a Trailing Stop TP.
- Protection against double entry (to reduce risk).
- Protection against opposite direction signal (closing the current position).
- Configurable limit of simultaneous positions opened.
- Stop opening positions when the balance is lower than a personalized amount.
- Alerts via email and/or WhatsApp on orders errors, stats and reached limits.
- Works only with USDT Perpetual positions.
- Stores all the positions opened on MySQL database, including Order IDs, Assets, Side, Signals used, Prices, Times and Realized PnLs.
- Dashboard with the operations, results and stats.

How to install:
Web server (tested on PHP 7.4):
1) Publish the folder bot.
2) Create a API key on Binance, copy the key and secret and enable Futures trading on it. Add your balance to the Futures account.
3) Create a database on MySQL and run the file createstructure.sql on it.
4) Update the file bot.php seting the parameters needed, keep the variable $tablename unchanged. Update also the file config.php with your database connection settings, timezone setting and email SMTP server settings.
5) Create your signal alert on TradingView and set as alert message a JSON content with the following structure (see example below). You need to enable the Webhook URL option in the Notifications tab of the alert and type the URL of your bot.php page there.

The JSON message sent should look like this:
{"direction": "SELL", "ticker": "BTCUSDT.P", "TPtrailingstop": "yes", "price": "66470.00", "timeframe": "60", "signalname": "HREV", "assettype": "BINANCE", "TP": "66000", "SL": "67000", "key": "Trade2024!", "wait": "0.5"}

Note: you can find a real-world example of a very good trading signal alert that monitors up to 40 assets in the file alert-example.txt (Pinescript code). Use it as a template and change your logic/assets according your preferences. In the tab Settings of the alert, keep the 'Alert name' field blank because the JSON will be sent via Pinescript code. In the Notifications tab of the alert, enable the Webhook URL option and type the URL of your bot.php page there.

I hope I can help you to automate your trades and make a lot of money! Have a good life!

Thanks,
Francisco Baddini


(RELEASING THE CODE SOON!)
