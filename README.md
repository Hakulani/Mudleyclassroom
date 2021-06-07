# Mudleyclassroom
Use API for connect to Exchange trading , CCXT – CryptoCurrency eXchange Trading Library


พอลง anaconda แล้วเปิด jupytor เลยครับอย่าลืมติดตั้ง ccxt ก่อนนะครับ
pip install ccxt

import ccxt
import pandas as pd
ftx = ccxt.ftx({
 'api_key': '................', # API Keys
 'secret': '.................'}) # API Secret
เรียกดูราคา BNB/USD
ftx.fetch_ticker('BNB/USD')['last']

เรียกดู balance ทั้งหมด
ftx.fetch_balance()

ส่งคำสั่งซื้อขาย
create_limit_buy_order
create_limit_sell_order
create_market_buy_order
create_market_sell_order
ตัวอย่างการตั้ง sell limit
![103184741_662697967643756_1725929051651684482_n](https://user-images.githubusercontent.com/61573397/121045774-09720080-c7e0-11eb-9fd9-96324d79edbc.png)
`<addr>`ftx.create_order('BNB/USD','limit','sell',0.5,20) 

เรียกดู orders ที่ส่งไป
`<my_open_orders = ftx.fetch_open_orders('BNB/USD')>`

ใช้ pandas เรียบเรียงให้ดูได้ด้วย pd.DataFrame
`< my_open_orders = pd.DataFrame(ftx.fetch_open_orders('BNB/USD')
display(my_open_orders)>`

ยกเลิกคำสั่ง order นั้นๆด้วย id
`<ftx.cancel_order(id) >`
จัดเก็บ order ที่ส่งเข้าตลาดด้วย pandas 
ต้องทำความเข้าใจตัว .to_csv() ของ pandas ด้วยนะครับนี่เป็นตัวอย่างคร่าวๆ
`<my_open_orders.to_csv('my_csv.csv', mode='a', header=False)>`

https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.to_csv.html
ขอขอบคุณ
Teerachai Rattanabunditsakul
Nattapon Soomtha (กองทุนความมั่งคั่งแห่งชาติ Training)
B2 spetsnaz club












CCXT – CryptoCurrency eXchange Trading Library
A JavaScript / Python / PHP library for cryptocurrency trading and e-commerce with support for many bitcoin/ether/altcoin exchange markets and merchant APIs.

Install · Usage · Manual · FAQ · Examples · Contributing · Social · CCXT Pro
The CCXT library is used to connect and trade with cryptocurrency exchanges and payment processing services worldwide. It provides quick access to market data for storage, analysis, visualization, indicator development, algorithmic trading, strategy backtesting, bot programming, and related software engineering.

It is intended to be used by coders, developers, technically-skilled traders, data-scientists and financial analysts for building trading algorithms.

Current feature list:

support for many cryptocurrency exchanges — more coming soon
fully implemented public and private APIs
optional normalized data for cross-exchange analytics and arbitrage
an out of the box unified API that is extremely easy to integrate
works in Node 7.6+, Python 3, PHP 5.4+, and web browsers
https://github.com/ccxt/ccxt
