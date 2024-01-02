# K
import mplfinance as mpf
import pandas as pd
import akshare as ak

df = ak.stock_zh_a_hist(symbol="000001", period="daily", start_date="20230601", end_date='20231101', adjust="")
df = df.iloc[:, 0:6]
df.日期 = pd.to_datetime(df.日期)
# 列名记得这样定义好
df.columns = ['Date', 'Open', 'Close', 'High', 'Low', 'Volume']
df.set_index('Date', inplace=True)
