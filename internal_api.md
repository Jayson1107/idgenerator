### 自选相关接口

## 添加自选

POST /watchlist

参数 | 类型 | 必需 | 说明
--- | --- | --- | ---
symbols | string | true | 添加到自选的股票集合，多个symbol以空格隔开

返回:

    {
        "status": "ok",
        "msg": "ok"
    }

## 删除自选

POST /watchlist/remove

参数 | 类型 | 必需 | 说明
--- | --- | --- | ---
symbols | string | true | 添加到自选的股票集合，多个symbol以空格隔开

返回:

    {
        "status": "ok",
        "msg": "ok"
    }

## 清空自选

POST /watchlist/empty

参数 | 类型 | 必需 | 说明
--- | --- | --- | ---

返回:

    {
        "status": "ok",
        "msg": "ok"
    }

## 删除自选

POST /watchlist/update

参数 | 类型 | 必需 | 说明
--- | --- | --- | ---
symbols | string | true | 添加到自选的股票集合，多个symbol以空格隔开

返回:

    {
        "status": "ok",
        "msg": "ok"
    }

## 自选列表

GET /watchlist

参数 | 类型 | 必需 | 说明
--- | --- | --- | ---

返回:

    {
        "status": "ok",
        "msg": "ok"
    }


### 行情相关接口

## 获取分时数据


POST /quote/time_trend

参数 | 类型 | 必需 | 说明
--- | --- | --- | ---
symbol | string | true | 股票代码
period | string | true  | K线数据类型，其值为 "day", "5day"其中之一

period为day的时候返回值:

    {
        "status": "ok",
        "msg": "ok",
        "data": {
            "symbol": "BABA",
            "period": "day",
            "preClose": 71.25,
            "items": [
                {
                    "time": 1457015400000,
                    "price": 71.28,
                    "avgPrice": 71.44531,
                    "volume": 190903
                },
                {
                    "time": 1457015460000,
                    "price": 71.54,
                    "avgPrice": 71.41769,
                    "volume": 76389
                },
                {
                    "time": 1457015520000,
                    "price": 71.47,
                    "avgPrice": 71.4587,
                    "volume": 112101
                },
                {
                    "time": 1457038740000,
                    "price": 71.02,
                    "avgPrice": 71.53249,
                    "volume": 448639
                }
            ]
        }
    }

period 为5day的时候返回值：

    {
        "status": "ok",
        "msg": "ok",
        "data": {
            "symbol": "BABA",
            "period": "5day",
            "preClose": 66.66,
            "items": [
                {
                    "items": [
                        {
                            "time": 1456497000000,
                            "price": 68.235,
                            "avgPrice": 68.061554,
                            "volume": 230162
                        },
                        {
                            "time": 1456519140000,
                            "price": 66.99,
                            "avgPrice": 67.736885,
                            "volume": 37617
                        },
                        {
                            "time": 1456520340000,
                            "price": 66.91,
                            "avgPrice": 67.659805,
                            "volume": 185079
                        }
                    ]
                },
                {
                    "items": [
                        {
                            "time": 1457015400000,
                            "price": 71.28,
                            "avgPrice": 71.44531,
                            "volume": 190903
                        },
                        {
                            "time": 1457038500000,
                            "price": 71.055,
                            "avgPrice": 71.56713,
                            "volume": 60811
                        },
                        {
                            "time": 1457038740000,
                            "price": 71.02,
                            "avgPrice": 71.53249,
                            "volume": 448639
                        }
                    ]
                }
            ]
        }
    }


## 获取K线数据

POST /quote/candle_stick

参数 | 类型 | 必需 | 说明
--- | --- | --- | ---
symbol | string | true | 股票代码
period | string | true  | K线数据类型，其值为 "day", "week", "month", "1min", "5min", "15min", "30min", "60min"其中之一

返回:

    {
        "status": "ok",
        "msg": "ok",
        "data": {
            "symbol": "BABA",
            "period": "1min",
            "items": [
                {
                    "open": 70.92,
                    "time": 1457023680000,
                    "volume": 6385,
                    "high": 70.95,
                    "low": 70.92,
                    "close": 70.95
                },
                {
                    "open": 70.9331,
                    "time": 1457023740000,
                    "volume": 7005,
                    "high": 70.985,
                    "low": 70.9331,
                    "close": 70.98
                },
                {
                    "open": 70.98,
                    "time": 1457023800000,
                    "volume": 30065,
                    "high": 71.08,
                    "low": 70.98,
                    "close": 71.071
                },
                {
                    "time": 1457038740000,
                    "price": 71.02,
                    "avgPrice": 71.53249,
                    "volume": 448639
                }
            ]
        }
    }



## 获取股票描述

GET /quote/stock_description

参数 | 类型 | 必需 | 说明
--- | --- | --- | ---
symbols | string | true | 添加到自选的股票集合，多个symbol以空格隔开

返回:

    {
        "status": "ok",
        "msg": "ok",
        "data": [
            "该ETF为两倍做多VIX指数短期期权合约\n\nVIX指数即波动率指数，以S&P500指数期权未来30天的隐含波动率计算得来。VIX反映了市场对未来30天市场波动性的预期",
            ""
        ]
    }

## 获取股票状态

GET /quote/stock_status

参数 | 类型 | 必需 | 说明
--- | --- | --- | ---
symbols | string | true | 添加到自选的股票集合，多个symbol以空格隔开

返回:

    {
        "status": "ok",
        "msg": "ok",
        "data": [
            1,
            1
        ]
    }

## 获取股票简介

GET /quote/stock_brief

参数 | 类型 | 必需 | 说明
--- | --- | --- | ---
symbols | string | true | 添加到自选的股票集合，多个symbol以空格隔开

返回:

    {
        "status": "ok",
        "msg": "ok",
        "data": [
            {
                "open": 29.86,
                "time": 1457384399999,
                "avgPrice": 29.815634,
                "symbol": "BAB",
                "volume": 264461,
                "high": 29.86,
                "low": 29.733,
                "preClose": 29.88,
                "close": 29.86
            },
            {
                "open": 178,
                "time": 1457384400000,
                "avgPrice": 177.82065,
                "symbol": "BIDU",
                "volume": 1948362,
                "high": 180,
                "low": 175.89,
                "preClose": 178.55,
                "close": 177.2
            }
        ]
    }

##  获取股票盘后行情

GET /quote/hour_trading


参数 | 类型 | 必需 | 说明
--- | --- | --- | ---
symbol | string | true | 股票代码

返回值：

    {
        "status": "ok",
        "msg": "ok",
        "data": {
            "detail": {
                "open": 72.91,
                "tag": "盘后",
                "change": 0,
                "volume": 231695,
                "high": 73.2411,
                "latestTime": "19:59 EST",
                "low": 72.86,
                "preClose": 72.89,
                "latestPrice": 72.89
            },
            "symbol": "BABA",
            "items": [
                {
                    "time": 1457384400000,
                    "price": 72.89,
                    "avgPrice": 72.89,
                    "volume": 0
                },
                {
                    "time": 1457385480000,
                    "price": 72.92,
                    "avgPrice": 73.1696,
                    "volume": 0
                },
                {
                    "time": 1457385540000,
                    "price": 72.92,
                    "avgPrice": 73.1696,
                    "volume": 0
                },
                {
                    "time": 1457398740000,
                    "price": 72.89,
                    "avgPrice": 72.912636,
                    "volume": 56
                }
            ]
        }
    }


### 市场相关接口

## 获取市场概览

GET  /market

参数 | 类型 | 必需 | 说明
--- | --- | --- | ---

返回值：

    {
        "status": "ok",
        "msg": "ok",
        "data": {
            "topics": [
                {
                    "headers": [
                        "名称代码",
                        "最新价格",
                        "涨跌幅"
                    ],
                    "id": "package_china",
                    "name": "中概股",
                    "data": [
                        [
                            "YGE",
                            "英利绿色能源",
                            4.97,
                            0.092308
                        ],
                        [
                            "CNIT",
                            "中国信息技术",
                            1.56,
                            0.090909
                        ],
                        [
                            "LEJU",
                            "乐居",
                            4.37,
                            0.089776
                        ],
                        [
                            "TEDU",
                            "达内科技",
                            10.34,
                            0.019724
                        ],
                        [
                            "BITA",
                            "易车网",
                            23.55,
                            0.017718
                        ]
                    ]
                },
                {
                    "headers": [
                        "名称代码",
                        "最新价格",
                        "涨跌幅"
                    ],
                    "id": "package_popular",
                    "name": "明星股",
                    "data": [
                        [
                            "SCTY",
                            "太阳城",
                            24.19,
                            0.080393
                        ],
                        [
                            "TRUE",
                            "TrueCar, Inc.",
                            6.4,
                            0.068447
                        ],
                        [
                            "NUS",
                            "如新集团",
                            34.41,
                            0.048127
                        ],
                        [
                            "LC",
                            "LendingClub",
                            9.4,
                            0.046771
                        ],
                        [
                            "JCP",
                            "彭尼百货",
                            11.68,
                            0.041927
                        ],
                        [
                            "MTCH",
                            "Match Group, Inc.",
                            12,
                            0.041667
                        ],
                        [
                            "BBRY",
                            "黑莓",
                            8.26,
                            0.041614
                        ],
                        [
                            "GPRO",
                            "GoPro",
                            13.88,
                            0.038922
                        ],
                        [
                            "ILMN",
                            "Illumina",
                            161.62,
                            0.035097
                        ],
                        [
                            "GILD",
                            "吉利德科学",
                            89.65,
                            0.027978
                        ]
                    ]
                }
            ],
            "market": "US",
            "indices": [
                {
                    "timestamp": 1457384400000,
                    "market": "US",
                    "symbol": ".DJI",
                    "name": "道琼斯",
                    "preClose": 17006.76953,
                    "latestPrice": 17073.94922
                },
                {
                    "timestamp": 1457384400000,
                    "market": "US",
                    "symbol": ".IXIC",
                    "name": "纳斯达克",
                    "preClose": 4717.02002,
                    "latestPrice": 4708.25
                },
                {
                    "timestamp": 1457384400000,
                    "market": "US",
                    "symbol": ".INX",
                    "name": "标普500",
                    "preClose": 1999.98999,
                    "latestPrice": 2001.76001
                }
            ]
        }
    }

## 获取细分市场行情

GET /market/package_quote

参数 | 类型 | 必需 | 说明
--- | --- | --- | ---
packageName | string | true | 股票包名称, package_china: 中概股 package_popular: 明星股 package_etf: ETF

返回值：

    {
        "status": "ok",
        "msg": "ok",
        "data": {
            "topics": [
                {
                    "headers": [
                        "名称代码",
                        "最新价格",
                        "涨跌幅"
                    ],
                    "id": "package_etf",
                    "name": "ETF",
                    "data": [
                        [
                            "UWTI",
                            "VelocityShares三倍做多原油ETN",
                            2.49,
                            0.147465,
                            "大宗商品",
                            "石油"
                        ],
                        [
                            "FXY",
                            "CurrencyShares Japanese Yen Trus",
                            85.42,
                            0.005651,
                            "外汇",
                            "其他"
                        ],
                        [
                            "SPY",
                            "标普500指数ETF",
                            200.59,
                            0.000798,
                            "美股大盘指数ETF",
                            "标普500"
                        ]
                    ]
                }
            ]
        }
    }

## 获取细分市场股票

GET /market/package_symbol

参数 | 类型 | 必需 | 说明
--- | --- | --- | ---
packageName | string | true | 股票包名称, package_china: 中概股 package_popular: 明星股 package_etf: ETF

返回值：

    {
        "status": "ok",
        "msg": "ok",
        "data": {
            "items": [
                "AAXJ",
                "XPP",
                "YANG",
                "YCS",
                "YINN",
                "YXI",
                "ZSL"
            ]
        }
    }
