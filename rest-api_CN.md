# REST行情与交易接口 (2019-05-16)
# 基本信息
* 所有接口的响应都是JSON格式
* 响应中如有数组，数组元素以时间升序排列，越早的数据越提前。
* 所有时间戳均为UNIX时间，单位为毫秒

# 主平台行情 API



# 接口说明

名称 | 说明
------------ | ------------
说明 | 根据市场id和统计时间周期查询市场行情
域名 | https://quotation.d1.kinmall.lan
路径 | /feixiaohao/mqe
请求方式 | GET
请求参数格式 | 无
参数例子 | 无
返回数据 | ["ticker":[{"symbol":"USDT/KM","h":6432.8763456,"lo":6324.56789765,"a":2134565.3456752,<br>"cp":0.3636,"v":342.345678,"mId":100,"eId":100,"p":"24h"},eId:1]
请求错误信息格式 | {"status":http status,"message":"describe status info"}
错误信息例子 | {"status":404,"message":"market quotation not found"}


# 请求参数说明

无


# 返回数据说明

名称 | 全称 | 类型 | 备注
------------ | ------------ | ------------| ------------
ticker | ticker | Array | 行情
eId | exchangeId | string | 交易所id
mId | marketId | Long | 市场id
h | highestPrice | string | 最高价
lo | lowestPrice | String | 最低价
la | lastPrice | String | 最新价
v | volume | String | 成交量
a | amount | String | 成交额
p | period | String | 统计周期
cp | changePct | string | 涨跌幅
mId | marketId | Long | 市场id




# 市场行情 API



# 接口说明

名称 | 说明
------------ | ------------
说明 | 根据市场id和统计时间周期查询市场行情
域名 | https://quotation.kinmall.co
路径 | /quotation/market
请求方式 | GET
请求参数格式 | ?mId=marketId&p=period<br>?p=period<br>?mId=marketId&p=period&s=size
参数例子 | ?mId=1000&p=24h<br>?p=24h<br>?p=24h&s=8
返回数据 | [{"h":6432.8763456,"lo":6324.56789765,"a":2134565.3456752,"cp":0.3636,"v":342.345678,"mId":100,<br>"eId":100,"p":"24h","st": 1556186972901000,"et": 1556467880018000}]
请求错误信息格式 | {"status":http status,"message":"describe status info"}
错误信息例子 | {"status":404,"message":"market quotation not found"}


# 请求参数说明

名称 | 全称 | 类型 | 必填 | 备注
------------ | ------------ | ------------ | ------------ | ------------
mId | marketId | Long | 否 | 市场id(可以为空，为空则是所有市场行情)
p | period | String | 是 | 统计周期（24h）
s | size | Interger | 否 | 条数


# 返回数据说明

名称 | 全称 | 类型 | 备注
------------ | ------------ | ------------| ------------
h | highestPrice | string | 最高价
lo | lowestPrice | String | 最低价
la | lastPrice | String | 最新价
a | amount | String | 成交额
v | volume | String | 成交量
cp | changePct | string | 涨跌幅
mId | marketId | Long | 市场id
eId | exchangeId | Long | 交易所id
p | period | String | 统计周期
st | startTime | Long | 开始时间（微秒）
et | endTime | Long | 结束时间（微秒）
h | highestPrice | string | 最高价
lo | lowestPrice | String | 最低价
la | lastPrice | String | 最新价
a | amount | String | 成交额


# 市场列表API



# 接口说明
名称 | 说明
------------ | ------------
说明 | 获取平台所有市场数据
域名 | https://www.kinmall.co
路径 | /api/markets/all
请求方式 | GET
请求参数格式 | -
参数例子 | -
返回数据 | {"items":[{"i":1,"bci":1,"sci":17,"tp":"BTC/USDT","ca":"2019-06-12T09:29:12Z","ds":true,<br>"ei":1,"oa":null,"s":"running","tai": 2,"tr":"0.00200"}]}
请求错误信息格式 | {"status":http status,"message":"describe status info"}
错误信息例子 | {"status":404,"message":"request not found"}


# 请求参数说明

无

# 返回数据说明

名称 | 全称 | 类型 | 备注
------------ | ------------ | ------------| ------------
bci | buyerCoinId | Long | 买方币种ID
ca | closedAt | String | 关闭时间
ds | deepSharing | Boolean | 是否深度共享
ei | amount | Long | 交易所ID
i | volume | Long | 市场ID(marketId)
oa | changePct | string | 开放时间
s | marketId | String | 市场状态
sci | exchangeId | Long | 卖方币种ID
tai | period | Long | 撮合引擎ID
tp | startTime | String | 交易对
tr | endTime | String | 交易手续费

s 字段为 "running" 时,市场为有效市场



# Market_id 对照表


交易所 | 市场 | Market_id
------------ | ------------ | ------------
KinMall主板 | BCH/USDT | 1
KinMall主板 | IEC/USDT | 2
KinMall主板 | ETH/USDT | 3
KinMall主板 | LTC/USDT | 4
KinMall主板 | VET/USDT | 5
KinMall主板 | XRP/USDT | 6
KinMall主板 | TRX/USDT | 7
KinMall主板 | KM/USDT | 8
KinMall主板 | ZRX/USDT | 9
KinMall主板 | OMG/USDT | 10
KinMall主板 | CGK/USDT | 11
KinMall主板 | BTC/USDT | 12
KinMall主板 | XYCC/USDT | 22
KinMall主板 | NMC/USDT | 23
KinMall主板 | GOLC/USDT | 24
KinMall主板 | BTRCM/USDT | 28
KinMall主板 | HZ/USDT | 29
KinMall主板 | CWV/USDT | 120
KinMall主板 | DASH/USDT | 123
KinMall主板 | BSV/USDT | 124
KinMall主板 | BTG/USDT | 140
KinMall主板 | ZEC/USDT | 141
KinMall主板 | PPT/USDT | 150
KinMall主板 | ENJ/USDT | 151
KinMall主板 | FET/USDT | 152
KinMall主板 | ZIL/USDT | 153
KinMall主板 | IOST/USDT | 154
KinMall主板 | MCO/USDT | 155
KinMall主板 | REP/USDT | 157
KinMall主板 | BAT/USDT | 158
KinMall主板 | WTC/USDT | 159
KinMall主板 | STORM/USDT | 160
KinMall主板 | MANA/USDT | 161
KinMall主板 | TT/USDT | 177
KinMall主板 | ONION/USDT | 190
KinMall创新区 | BTC/USDT | 100
KinMall创新区 | XYCC/USDT | 101
KinMall创新区 | GOLC/USDT | 102
KinMall创新区 | HZ/USDT | 103
KinMall创新区 | BTRCM/USDT | 104
KinMall创新区 | CGK/USDT | 105
KinMall创新区 | BCH/USDT | 108
KinMall创新区 | XRP/USDT | 109
KinMall创新区 | ETH/USDT | 110
KinMall创新区 | TRX/USDT | 111
KinMall创新区 | LTC/USDT | 112
KinMall创新区 | DDP/USDT | 129
KinMall创新区 | KM/USDT | 138
KinMall创新区 | FB/USDT | 162
KinMall创新区 | CWV/USDT | 170
KinMall创新区 | CDR/USDT | 171
KinMall创新区 | HDS/USDT | 187
KinMall创新区 | WRTC/USDT | 189
KinMall创新区 | GQ/USDT | 191
五福临门 | ETH/USDT | 106
五福临门 | BTC/USDT | 107
五福临门 | XRP/USDT | 113
五福临门 | LTC/USDT | 114
五福临门 | BCH/USDT | 115
五福临门 | FB/USDT | 128
五福临门 | KM/USDT | 137
云币 | BTC/USDT | 42
云币 | ETH/USDT | 43
云币 | BCH/USDT | 44
云币 | LTC/USDT | 45
云币 | TRX/USDT | 46
云币 | XRP/USDT | 47
币信交易所 | BTC/USDT | 72
币信交易所 | ETH/USDT | 73
币信交易所 | LTC/USDT | 74
币信交易所 | BCH/USDT | 75
币信交易所 | TRX/USDT | 76
币信交易所 | XRP/USDT | 77
币牛交易所 | BTC/USDT | 84
币牛交易所 | ETH/USDT | 85
币牛交易所 | BCH/USDT | 86
币牛交易所 | LTC/USDT | 87
币牛交易所 | TRX/USDT | 88
币牛交易所 | XRP/USDT | 89
币金国际交易所 | BTC/USDT | 48
币金国际交易所 | ETH/USDT | 49
币金国际交易所 | BCH/USDT | 50
币金国际交易所 | LTC/USDT | 51
币金国际交易所 | TRX/USDT | 52
币金国际交易所 | XRP/USDT | 53
币多多 | BTC/USDT | 90
币多多 | ETH/USDT | 91
币多多 | BCH/USDT | 92
币多多 | LTC/USDT | 93
币多多 | TRX/USDT | 94
币多多 | XRP/USDT | 95
比特星球 | BTC/USDT | 36
比特星球 | ETH/USDT | 37
比特星球 | BCH/USDT | 38
比特星球 | LTC/USDT | 39
比特星球 | TRX/USDT | 40
比特星球 | XRP/USDT | 41
柯赢交易所 | ETH/USDT | 173
柯赢交易所 | GTW/USDT | 178
宝二爷交易所 | GOD/USDT | 142
宝二爷交易所 | BTC/USDT | 143
宝二爷交易所 | ETH/USDT | 144
宝二爷交易所 | LTC/USDT | 145
宝二爷交易所 | TRX/USDT | 146
宝二爷交易所 | XRP/USDT | 147
宝二爷交易所 | BCH/USDT | 148
宝二爷交易所 | KM /USDT | 149
宝二爷交易所 | ADC/USDT | 156
Xcoin | BTC/USDT | 163
Xcoin | ETH/USDT | 164
Xcoin | XRP/USDT | 165
Xcoin | LTC/USDT | 166
Xcoin | BCH/USDT | 167
Xcoin | KM/USDT | 168
Nice国际交易所 | KM/USDT | 179
Nice国际交易所 | BCH/USDT | 180
Nice国际交易所 | ETH/USDT | 181
Nice国际交易所 | BTC/USDT | 182
Nice国际交易所 | LTC/USDT | 183
Nice国际交易所 | XRP/USDT | 184
Nice国际交易所 | TRX/USDT | 185
Morning | LTC/USDT | 32
Morning | XRP/USDT | 117
Morning | ETH/USDT | 118
Morning | TRX/USDT | 119
Morning | NMC/USDT | 131
Morning | BSC/USDT | 172
Morning | LSC/USDT | 188
OneBit | BTC/USDT | 78
OneBit | ETH/USDT | 79
OneBit | BCH/USDT | 80
OneBit | LTC/USDT | 81
OneBit | TRX/USDT | 82
OneBit | XRP/USDT | 83
CoinTop | BTC/USDT | 60
CoinTop | ETH/USDT | 61
CoinTop | BCH/USDT | 62
CoinTop | LTC/USDT | 63
CoinTop | TRX/USDT | 64
CoinTop | XRP/USDT | 65
Coinstar币星交易所 | BTC/USDT | 66
Coinstar币星交易所 | ETH/USDT | 67
Coinstar币星交易所 | BCH/USDT | 68
Coinstar币星交易所 | LTC/USDT | 69
Coinstar币星交易所 | XRP/USDT | 70
Coinstar币星交易所 | TRX/USDT | 71
Chain Mew趣喵交易所 | KM/USDT | 25
Chain Mew趣喵交易所 | ETH/USDT | 26
Chain Mew趣喵交易所 | TRX/USDT | 30
Chain Mew趣喵交易所 | XRP/USDT | 31
BYEX | BX/USDT | 19
BYEX | BTC/USDT | 33
BYEX | ETH/USDT | 34
BYEX | LTC/USDT | 35
BYEX | BCH/USDT | 96
BYEX | XRP/USDT | 97
BYEX | TRX/USDT | 98
BYEX | KM/USDT | 136
Bmus创业板 | BTC/USDT | 20
Bmus创业板 | ETH/USDT | 21
Bmus创业板 | LOOIS/USDT | 99
Bmus创业板 | KM/USDT | 134
Bmus创业板 | BMUS/USDT | 169
Bmus创业板 | HDS/USDT | 186
Adam国际数字资产交易平台 | BTC/USDT | 13
Adam国际数字资产交易平台 | ETH/USDT | 14
Adam国际数字资产交易平台 | XRP/USDT | 15
Adam国际数字资产交易平台 | LTC/USDT | 16
Adam国际数字资产交易平台 | TRX/USDT | 17
Adam国际数字资产交易平台 | BCH/USDT | 18
Acoin | BTC/USDT | 54
Acoin | ETH/USDT | 55
Acoin | BCH/USDT | 56
Acoin | LTC/USDT | 57
Acoin | TRX/USDT | 58
Acoin | XRP/USDT | 59
Wave | IEC/USDT | 130
Wave | BTC/USDT | 132
Wave | ETH/USDT | 133
P.O太平洋交易所 | BTC/USDT | 122
P.O太平洋交易所 | KM/USDT | 139
P.O太平洋交易所 | POC/USDT | 174
KKY | BTC/USDT | 127
KKY | KM/USDT | 135
Kim Universe | BTC/USDT | 175
Kim Universe | KM/USDT | 176
GWG金牌交易所 | ETH/USDT | 27
GWG金牌交易所 | GWG/USDT | 126
万博国际数字资产交易所 | CGK/USDT | 116
SuperCoin数字资产交易所 | ETH/USDT | 125
华链CCSS | ETH/USDT | 121
