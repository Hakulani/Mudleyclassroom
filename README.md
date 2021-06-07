# Mudleyclassroom CryptoCurrency eXchange Trading 
Use API for connect to Exchange trading , CCXT – CryptoCurrency eXchange Trading Library
CCXT – CryptoCurrency eXchange Trading Library A JavaScript / Python / PHP library for cryptocurrency trading and e-commerce with support for many bitcoin/ether/altcoin exchange markets and merchant APIs.

Install · Usage · Manual · FAQ · Examples · Contributing · Social · CCXT Pro The CCXT library is used to connect and trade with cryptocurrency exchanges and payment processing services worldwide. It provides quick access to market data for storage, analysis, visualization, indicator development, algorithmic trading, strategy backtesting, bot programming, and related software engineering.

It is intended to be used by coders, developers, technically-skilled traders, data-scientists and financial analysts for building trading algorithms.

Current feature list:

support for many cryptocurrency exchanges — more coming soon fully implemented public and private APIs optional normalized data for cross-exchange analytics and arbitrage an out of the box unified API that is extremely easy to integrate works in Node 7.6+, Python 3, PHP 5.4+, and web browsers https://github.com/ccxt/ccxt


พอลง anaconda แล้วเปิด jupytor เลยครับอย่าลืมติดตั้ง ccxt ก่อนนะครับ

<h1>Install</h1>

Python
ccxt in PyPI

pip install ccxt
import ccxt
print(ccxt.exchanges) # print a list of all available exchange classes
The library supports concurrent asynchronous mode with asyncio and async/await in Python 3.5.3+

import ccxt.async_support as ccxt # link against the asynchronous version of ccxt


pip install ccxt
```
import ccxt
import pandas as pd
ftx = ccxt.ftx({
 'api_key': '................', # API Keys
 'secret': '.................'}) # API Secret
 ```
<h2> Usage</h2>
Intro
The CCXT library consists of a public part and a private part. Anyone can use the public part immediately after installation. Public APIs provide unrestricted access to public information for all exchange markets without the need to register a user account or have an API key.

Public APIs include the following:

market data
instruments/trading pairs
price feeds (exchange rates)
order books
trade history
tickers
OHLC(V) for charting
other public endpoints
In order to trade with private APIs you need to obtain API keys from an exchange's website. It usually means signing up to the exchange and creating API keys for your account. Some exchanges require personal info or identification. Sometimes verification may be necessary as well. In this case you will need to register yourself, this library will not create accounts or API keys for you. Some exchanges expose API endpoints for registering an account, but most exchanges don't. You will have to sign up and create API keys on their websites.

Private APIs allow the following:

manage personal account info
query account balances
trade by making market and limit orders
deposit and withdraw fiat and crypto funds
query personal orders
get ledger history
transfer funds between accounts
use merchant services
This library implements full public and private REST APIs for all exchanges. WebSocket and FIX implementations in JavaScript, PHP, Python are available in CCXT Pro, which is a professional addon to CCXT with support for WebSocket streams.

The CCXT library supports both camelcase notation (preferred in JavaScript) and underscore notation (preferred in Python and PHP), therefore all methods can be called in either notation or coding style in any language.

 
เรียกดูราคา BNB/USD
```
ftx.fetch_ticker('BNB/USD')['last']
```
เรียกดู balance ทั้งหมด
```
ftx.fetch_balance()
```
ส่งคำสั่งซื้อขาย
```
create_limit_buy_order
create_limit_sell_order
create_market_buy_order
create_market_sell_order
```
ตัวอย่างการตั้ง sell limit
![103184741_662697967643756_1725929051651684482_n](https://user-images.githubusercontent.com/61573397/121045774-09720080-c7e0-11eb-9fd9-96324d79edbc.png)
```
ftx.create_order('BNB/USD','limit','sell',0.5,20) 
```

เรียกดู orders ที่ส่งไป
```
my_open_orders = ftx.fetch_open_orders('BNB/USD')
```

ใช้ pandas เรียบเรียงให้ดูได้ด้วย pd.DataFrame
``` 
my_open_orders = pd.DataFrame(ftx.fetch_open_orders('BNB/USD')
display(my_open_orders)
```

ยกเลิกคำสั่ง order นั้นๆด้วย id
```
ftx.cancel_order(id) 
```
จัดเก็บ order ที่ส่งเข้าตลาดด้วย pandas 
ต้องทำความเข้าใจตัว .to_csv() ของ pandas ด้วยนะครับนี่เป็นตัวอย่างคร่าวๆ
```
my_open_orders.to_csv('my_csv.csv', mode='a', header=False)
```

https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.to_csv.html
<br>ขอขอบคุณ</br>
- Teerachai Rattanabunditsakul
- Nattapon Soomtha (กองทุนความมั่งคั่งแห่งชาติ Training)
- B2 spetsnaz club

<h5>Contributing</h5>
Please read the  [CONTRIBUTING](https://github.com/ccxt/ccxt/blob/master/CONTRIBUTING.md) document before making changes that you would like adopted in the code. Also, read the 
[Manual](https://github.com/ccxt/ccxt/wiki)for more details.
