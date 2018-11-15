#币智慧-开放API


币智慧开放API，提供最全面、最快捷的资讯、行情数据及分析。



**特性：**

1、全网最全的币圈资讯数据

​      已经覆盖交易所公告、知名媒体站点、公众号、今日头条、百度等，数据实时更新。

2、丰富的文章分析属性

​      提供资讯文章的重要性、文章的聚合结果、利好利空倾向预测等属性

3、实时的交易平台行情、公告

​      提供K线行情及实时公告内容



**使用场景：**

1、币圈资讯阅读平台，参考 https://www.bizhihui.vip

2、价格行情监控平台，参考 “币智慧币圈助手” 小程序

3、其他需要资讯、行情信息的平台



**使用方式：**

1、了解API请求方式

2、申请API token：发送申请邮件到 api@truxing.com 申请，标题请注明：币智慧接口申请。邮件请说明使用场景及联系方式

3、测试、使用API



注意：如果token不正确，会直接返回401





API列表
---

|接口|版本|描述|
|---|---|---|
|[/v1/coin_basic](#获取币种基本信息)||获取币种基本信息|
|[/v1/coin_quotation](#获取币种行情)||获取币种行情|
|[/v1/coin_news](#获取币种资讯)||获取币种资讯|
|[/v1/notice](#获取最新公告)||获取最新公告|
|[/v1/message](#获取最新快讯)||获取最新快讯|
|[/v1/news](#获取最新资讯)||获取最新资讯|
|[/v1/intro_news](#获取入门资讯)||获取入门资讯|
|[/v1/essence_news](#获取精选资讯)||获取精选资讯|
|[/v1/ticker](#获取ticker)||获取ticker|
|[/v1/records](#获取k线)||获取K线|
|[/v1/getexchangepair](#获取交易对接口)||获取交易对接口|
|[/v1/getcoinlist](#获取币种列表)||获取币种列表|
|[/v1/getchangemsg](#获取异动资讯)||获取异动资讯|
|[/v1/getchangemsg](#获取异动资讯)||获取异动资讯|
|[/v1/getchangeindex](#获取异动指数)||获取异动指数|
|[/v1/getchangeevent](#获取异动事件列表)||获取异动事件列表|


获取币种基本信息
---
|接口|版本|描述|
|---|---|---|
|[/v1/coin_basic](#获取币种基本信息)||获取币种基本信息|
#### 参数列表

|参数名|参数类型|描述|是否必选|
|---|---|---|---|
|key|string|查询币的名称或中文名或英文名,获取币种列表接口中的_id就是参数|必选|

#### 请求举例

```shell
$ curl -XGET http://api.bizhihui.info/v1/coin_basic?key=bitcoin&token={token}
```

#### 返回结果

```shell
{
    "code": 200,
    "data": {
        "descriptions": {
            "en": [
                "The concept of Bitcoin (Bitcoin) was first proposed by Nakamoto in 2009, according to Satoshi Nakamoto's idea of ​​designing open source software and building a P2P network. Bitcoin is a P2P digital currency. Point-to-point transmission means a decentralized payment system. Unlike most currencies, Bitcoin does not rely on specific currency institutions to issue. It is based on specific algorithms and generated by a large number of calculations. The Bitcoin economy uses a distributed database of multiple nodes in the entire P2P network to confirm and record all transactions. And the use of cryptography design to ensure the security of the various aspects of currency circulation. P2P decentralization features and algorithms itself can ensure that can not be manipulated through the large number of bitcoin to manipulate the currency value. The cryptographic design allows bitcoin to be transferred or paid only by the real owner. This also ensures the anonymity of currency ownership and liquidity transactions. The biggest difference between Bitcoin and other virtual currencies is that their total number is very limited and they are extremely scarce. The currency system had no more than 10.5 million in 4 years, and the total amount will be permanently limited to 21 million."
            ],
            "zh": [
                "比特币（BitCoin）的概念最初由中本聪在2009年提出，根据中本聪的思路设计发布的开源软件以及建构其上的P2P网络。比特币是一种P2P形式的数字货币。点对点的传输意味着一个去中心化的支付系统。与大多数货币不同，比特币不依靠特定货币机构发行，它依据特定算法，通过大量的计算产生，比特币经济使用整个P2P网络中众多节点构成的分布式数据库来确认并记录所有的交易行为，并使用密码学的设计来确保货币流通各个环节安全性。P2P的去中心化特性与算法本身可以确保无法通过大量制造比特币来人为操控币值。基于密码学的设计可以使比特币只能被真实的拥有者转移或支付。这同样确保了货币所有权与流通交易的匿名性。比特币与其他虚拟货币最大的不同，是其总数量非常有限，具有极强的稀缺性。该货币系统曾在4年内只有不超过1050万个，之后的总数量将被永久限制在2100万个。"
            ]
        },//币种描述
        "ex_num": 166,//交易所数量
        "github": "https://github.com/bitcoin/bitcoin",//开源代码地址
        "publish_time": 1231027200000,//发布时间
        "website": "",//官网地址
        "whitepaper": "http://www.bitcoin.org/bitcoin.pdf"//白皮书地址
    },
    "msg": "Succeed"
}
```

获取币种行情
---
|接口|版本|描述|
|---|---|---|
|[/v1/coin_quotation](#获取币种行情)||获取币种行情|
#### 参数列表

|参数名|参数类型|描述|是否必填|
|---|---|---|---|
|key|string|查询币的名称或中文名或英文名,参数使用币种列表接口中的_id|必选|

#### 请求举例

```shell
$ curl -XGET http://api.bizhihui.info/v1/coin_quotation?token={token}&key=bitcoin
```

#### 返回结果

```shell
{
    "code": 200,
    "data": {
        "_id": "5ac4c239bd2133b5e958dfa5",
        "last_updated": 1522844046,//最后更新时间
        "market_cap_cny": 0,//人民币总价格
        "market_cap_usd": 0,//美元总价格
        "max_supply": 0,//最大发行量
        "name": "Cashme",//币名称
        "percent_change_1h": -0.109999999403954,//1小时涨跌幅
        "percent_change_24h": -27.8199996948242,//24小时涨跌幅
        "percent_change_7d": -34.6199989318848,//7天涨跌幅
        "price_btc": 2.99999989294975e-8,//比特币价格
        "price_cny": 0.00133788923267275,//人民币价格
        "price_cny_high_24h": 0.00187352590728551,//24小时最高人民币价格
        "price_cny_low_24h": 0.00132845528423786,//24小时人民币最低价格
        "price_usd": 0.00021203700453043,//美元价格
        "price_usd_high_24h": 0.000297771010082215,//24小时美元最高价格
        "price_usd_low_24h": 0.000211077000130899,//24小时美元最低价格
        "rank": 1496,//排名
        "symbol": "CME",//简称
        "total_supply": 0,//总流通量
        "volume_cny_24h": 568.171813964844,//24小时人民币交易量
        "volume_usd_24h": 90.0474014282227//24小时美元交易量
    },
    "msg": "Succeed"
}
```

获取币种资讯
---
|接口|版本|描述|
|---|---|---|
|[/v1/coin_news](#获取币种资讯)||获取币种资讯|
#### 参数列表

|参数名|参数类型|描述|是否必填|
|---|---|---|---|
|key|string|查询币的名称或中文名或英文名,参数使用币种列表接口中的_id|必选|
|limit|number|数量最大为100|必选|

#### 请求举例

```shell
$ curl -XGET http://api.bizhihui.info/v1/coin_news?token={token}&key=CME&limit=1
```

#### 返回结果

```shell
{
    "code": 200,
    "data": [
        {
            "_id": "oXdwiC6co4",
            "abstract": [
                " 根据市场的情况及用户的建议，EXX于北京时间2018年1月22日全球首发上线Electronic PK Chain（简称EPC，发行量：5亿），目前已开放充值，并计划于北京时间2018年1月24日14时开放EPC/QC、EPC/BTC、EPC/ETH交易市场，用户可提前充值准备。 Electronic PK Chain，中文名为电竞链，其目的是利用区块链技术并结合区块链技术特性，建设一个公平、公开的综合性电子竞技网络。解决电子竞技行业目前所面临的信任问题及公平问题，使整个电子竞技行业更加公平、公开、高效。"
            ],//摘要
            "article_events": [],
            "content": "尊敬的EXX用户：\n      您好！\n      根据市场的情况及用户的建议，EXX于北京时间2018年1月22日全球首发上线Electronic PK Chain（简称EPC，发行量：5亿），目前已开放充值，并计划于北京时间2018年1月24日14时开放EPC/QC、EPC/BTC、EPC/ETH交易市场，用户可提前充值准备。\n      Electronic PK Chain，中文名为电竞链，其目的是利用区块链技术并结合区块链技术特性，建设一个公平、公开的综合性电子竞技网络。解决电子竞技行业目前所面临的信任问题及公平问题，使整个电子竞技行业更加公平、公开、高效。\n\n电竞链的设计初衷是构建一个多维度的电子竞技区块平台，通过区块链底层技术，构建出一套完善的方案搭载在电竞链上，使用区块链技术产出的统一数字货币进行奖励。官方地址：http://epc.im/\n      EXX以更好的用户体验为目标不断提升服务，感谢您的支持与信任！ \nEXX TEAM",//内容
            "host": "www.exx.com",//地址
            "html": "<div class=\"blog-info\"><p>尊敬的EXX用户：</p><p>      您好！</p><p>      根据市场的情况及用户的建议，EXX于北京时间2018年1月22日全球首发上线Electronic PK Chain（简称EPC，发行量：5亿），目前已开放充值，并计划于北京时间2018年1月24日14时开放EPC/QC、EPC/BTC、EPC/ETH交易市场，用户可提前充值准备。</p><p>      Electronic PK Chain，中文名为电竞链，其目的是利用区块链技术并结合区块链技术特性，建设一个公平、公开的综合性电子竞技网络。解决电子竞技行业目前所面临的信任问题及公平问题，使整个电子竞技行业更加公平、公开、高效。\n\n电竞链的设计初衷是构建一个多维度的电子竞技区块平台，通过区块链底层技术，构建出一套完善的方案搭载在电竞链上，使用区块链技术产出的统一数字货币进行奖励。官方地址：<u><a href=\"http://epc.im/\" target=\"_blank\">http://epc.im/</a></u></p><p>      EXX以更好的用户体验为目标不断提升服务，感谢您的支持与信任！ </p><p>EXX TEAM</p></div>",//网页原文
            "publish_time": 1516550400000,//发布时间
            "rank": 0.0498136840760708,//重要性
            "relevance": [],
            "sentiment": {
                "error": 0,
                "prob": 0.8,
                "type": "pos"//pos是利好，neg是利空
            },//利好利空
            "site": "Exx",//爬取站点
            "tags": [
                "区块链",
                "区块链技术",
                "数字货币"
            ],//文章标签
            "title": "关于首发上线Electronic PK Chain（EPC）及开放交易的公告 发布时间：2018-01-22 20:05:38",//文章标题
            "url": "https://www.exx.com/blog/display?type=102&id=380"//文章地址
        }
    ],
    "msg": "Succeed"
}
```

获取最新公告
---
|接口|版本|描述|
|---|---|---|
|[/v1/notice](#获取最新公告)||获取最新公告|
#### 参数列表

|参数名|参数类型|描述|是否必选|
|---|---|---|---|
|limit|number|数量最大为100|必选|

#### 请求举例

```shell
$ curl -XGET http://api.bizhihui.info/v1/notice?token={token}&limit=1
```

#### 返回结果

```shell
{
    "code": 200,
    "data": [
        {
            "_id": "u2zIkxSXR",
            "abstract": [
                "美国商品期货交易委员会（CFTC）的比特币投机部位显示..."
            ],//摘要
            "article_events": [
                {
                    "bson": 9,
                    "start": 5,
                    "type": "time",
                    "word": " 1 月"
                },
                {
                    "bson": 27,
                    "start": 16,
                    "type": "org_name",
                    "word": "美国商品期货交易委员会"
                },
                ...
            ],//文章事件
            "content": "虚拟货币在 1 月暴跌早有预兆？美国商品期...",//文章内容
            "publish_time": 1516604400000,//文章发布时间
            "rank": 0.482599765062332,
            "relevance": [
                {
                    "abstract": {
                        "indexes": [
                            {
                                "end": 27,
                                "start": 24
                            },
                            {
                                "end": 56,
                                "start": 53
                            }
                        ],
                        "similarity": 0.252766869510956,
                        "string": "尽管这回空方大胜... "
                    },
                    "score": 0.875,
                    "type": "coin",
                    "word": "BTC"
                }          
            ],//文章相关性
            "sentiment": {
                "error": 0,
                "prob": 0.689312875270844,
                "type": "neg"//pos是利好，neg是利空
            },//利好利空
            "site": "TechNews",//爬取站点
            "tags": [
                "比特币"
            ],//文章tag
            "title": "比特币空单周周飙太一面倒？当心轧空引爆涨势",//文章标题
            "url": "http://technews.cn/2018/01/22/as-the-bitcoin-short-quietly-grows-is-a-short-squeeze-imminent"//文章url地址
        }
    ],
    "msg": "Succeed"
}
```

获取最新快讯
---
|接口|版本|描述|
|---|---|---|
|[/v1/message](#获取最新快讯)||获取最新快讯|
#### 参数列表

|参数名|参数类型|描述|是否必选|
|---|---|---|---|
|limit|number|数量最大为100|必选|

#### 请求举例

```shell
$ curl -XGET http://api.bizhihui.info/v1/message?token={token}&limit=1
```

#### 返回结果

```shell
{
    "code": 200,
    "data": [
        {
            "_id": "5acb97d1245bd80001e44dbf",
            "abstract": [
                "比特币作为数字货币的龙头老大，在价格上一骑绝尘，价格接连突破了13000美元、14000美元整数关口，有零星交易网站一度冲破20000美元大关，一再刷新价格记录。如此看来分叉币在实用上的优势不比BTC差，也正是如此分叉币的社区也在慢慢扩大，众多投资者和机构也都纷纷入场。不过没上车的也不要担心，据了解近日又有一只海外基金会BTN FOUNDATION宣布成立，该基金会已经组建开发团队分叉出Bitcoin New，官网btn.kim也正式上线。"
            ],//摘要
            "created_at": 1523292113000,//创建时间
            "sentiment": {
                "error": 0,
                "prob": 0.84687656,
                "type": "pos"//pos利好，neg利空
            },//利好利空分析
            "site": "全景网",//爬取站点
            "text": "不过没上车的也不要担心，据了解近日又有一只海外基金会BTN FOUNDATION宣布成立，该基金会已经组建开发团队分叉出Bitcoin New，官网btn.kim也正式上线。将推动新比特币 (BTN)更大范围的普及和应用，让更多的用户和开发者参与到数字货币的浪潮中来。"//内容
        }
    ],
    "msg": "Succeed"
}
```

获取最新资讯
---
|接口|版本|描述|
|---|---|---|
|[/v1/news](#获取最新资讯)||获取最新资讯|
#### 参数列表

|参数名|参数类型|描述|是否必选|
|---|---|---|---|
|limit|number|数量最大为100|必选|

#### 请求举例

```shell
$ curl -XGET http://api.bizhihui.info/v1/news?token={token}&limit=1
```

#### 返回结果

```shell
{
    "code": 200,
    "data": [
        {
            "_id": "jdnPKTpvl2",
            "abstract": null,
            "article_events": [
                {
                    "end": 3,
                    "start": 0,
                    "type": "product_name",
                    "word": "比特币"
                }
            ],//文章事件
            "content": "比特币也好，莱特币",//内容
            "host": "www.chinanews.com",//爬取网站
            "html": "服务。因此，盲目“炒币”有风险，投资需要警惕跟风。</p><div id=\"function_code_page\"></div>  \n\n      </div>",//html内容
            "publish_time": 214996867200000,//发布时间
            "relevance": [
                {
                    "abstract": {
                        "indexes": [
                            {
                                "end": 9,
                                "start": 6
                            }
                        ],
                        "similarity": 0.06980396906720632,
                        "string": "比特币也好，莱特币、元宝币也罢，在国内市场上经过一段时间的狂热炒作后，在监管加强后，价格都出现大幅波动。"
                    },
                    "score": 0.05,
                    "type": "coin",
                    "word": "LTC"
                },
                {
                    "abstract": {
                        "indexes": [
                            {
                                "end": 25,
                                "start": 22
                            },
                            {
                                "end": 58,
                                "start": 55
                            }
                        ],
                        "similarity": 0.3139055961260575,
                        "string": "　　据新华社电 曾一年间疯涨80倍的虚拟货币比特币正遭遇尴尬：一方面，交易平台遭遇银行及支付机构“设限”，导致比特币行情单月跳水近40%；另一方面，虚拟货币热也催生国内数十种“山寨币”，投资均不乏本金难保风险。"
                    },
                    "score": 0.75,
                    "type": "coin",
                    "word": "BTC"
                },
                {
                    "abstract": {
                        "indexes": [
                            {
                                "end": 102,
                                "start": 99
                            }
                        ],
                        "similarity": 0.19114485617774707,
                        "string": "　　比如，据中文虚拟币行情网站“聚币网”报价，2014年1月至今，已有16款线上国产虚拟货币宣布“发行”，目前在国内可交易的虚拟货币已达数十种。仅2月2日及3日，两天内就有“企鹅币”、“大象币”、“蜗牛币”三款国内虚拟货币宣布上线。"
                    },
                    "score": 0.05,
                    "type": "coin",
                    "word": "RDD"
                }
            ],//文章相关性
            "sentiment": {
                "error": 0,
                "prob": 1,
                "type": "neg"//pos是利好，neg是利空
            },//利好利空
            "site": "中国新闻网",//站点
            "tags": [
                "比特币",
                "莱特币"
            ],//文章tag
            "title": "比特币报价单月跳水近40% 虚拟货币热催生风险",//标题
            "url": "http://www.chinanews.com/it/2014/04-07/6035171.shtml"//爬取网站
        }
    ],
    "msg": "Succeed"
}
```

获取入门资讯
---
|接口|版本|描述|
|---|---|---|
|[/v1/intro_news](#获取入门资讯)||获取入门资讯|
#### 参数列表

|参数名|参数类型|描述|是否必选|
|---|---|---|---|
|limit|number|数量最大为100|必选|

 请求示例和返回示例同[/v1/news](#获取最新资讯)

获取精选资讯
---
|接口|版本|描述|
|---|---|---|
|[/v1/essence_news](#获取精选资讯)||获取精选资讯|
#### 参数列表

|参数名|参数类型|描述|是否必选|
|---|---|---|---|
|limit|number|数量最大为100|必选|

 请求示例和返回示例同[/v1/news](#获取最新资讯)


获取ticker
---
|接口|版本|描述|
|---|---|---|
|[/v1/ticker](#获取ticker)||获取ticker|

#### 参数列表
|参数名|参数类型|描述|是否必选|
|---|---|---|---|
|quote|string|币种|必选|
|base|string|对应现实的货币|必选|
|platform|string|选择不同的交易市场|必选|

#### 请求举例

```shell
$ curl -XGET http://api.bizhihui.info/v1/ticker?quote=btc&base=usdt&platform=huobipro&token={token}
```

#### 返回结果

```shell
$ {

    "code":200,
    "data": {
        "Buy": 0,   //买一价
        "Sell": 0.076379,  //卖一价
        "Last": 0.076273,  //最新成交价
        "Low": 0.0743,     //最低价
        "High": 0.077463,  //最高价
        "Vol": 1478.5294659496, //成交量
        "PriceChangePercent":-6.78 //24小时涨跌幅 百分比
    },
    "msg":"succeed"
}

```
获取K线
---
|接口|版本|描述|
|---|---|---|
|[/v1/records](#获取K线)||获取K线|

#### 参数列表
|参数名|参数类型|描述|是否必选|
|---|---|---|---|
|quote|string|币种|必选|
|base|string|对应现实的货币|必选|
|platform|string|选择不同的交易市场|必选|
|type|string|时间段,1h:小时 1d:天 1w:周|必选|
|since|string|从这个时间戳之后的  单位:秒|必选|
|size|string|返回数量 最大1000|必选|

#### 请求举例

```shell
$ curl -XGET http://api.bizhihui.info/v1/records?quote=btc&base=usdt&platform=huobipro&type=1h&since=123123123&size=60&token={token}
```

#### 返回结果

```shell
$ {

    "code":200,
    "data":  [
        {
            "Open": 0.07561841,  //开盘价
            "High": 0.07561841,  //最高价
            "Low": 0.07555555,   //最低价
            "Close": 0.07555555, //收盘价
            "Vol": 29.80180156,  //24小时交易量
            "Ktime":"156767899",//时间 秒级时间戳

        }],
   "msg":"succeed",
}

```


获取交易对接口
---
|接口|版本|描述|
|---|---|---|
|[/v1/getexchangepair](#获取交易对接口)||获取交易对接口|

#### 参数列表
|参数名|参数类型|描述|是否必选|
|---|---|---|---|
|platform|string|选择不同的交易市场|必选|

#### 请求举例

```shell
$ curl -XGET http://api.bizhihui.info/v1/getexchangepair?platform=binance&token={token}
```

#### 返回结果

```shell
$ {
    "code": 200,
    "data": [
        {
            "pair": "SMART/BTC",  //币种
            "pair_base": "BTC",    //对应现实的货币
            "name": "SmartCash"   //名字
        },
    "msg":"succeed"
}

```


获取币种列表
---
|接口|版本|描述|
|---|---|---|
|[/v1/getcoinlist](#获取币种列表)||获取币种列表|

#### 参数列表
|参数名|参数类型|描述|是否必选|
|---|---|---|---|

#### 请求举例

```shell
$ curl -XGET http://api.bizhihui.info/v1/getcoinlist?token={token}
```

#### 返回结果

```shell
$ {
    "code": 200,
    "data": [
       {
          "_id": "bitcoin",//名称
          "symbol": "BTC"//种类
               },
    "msg":"succeed"
}

```

接口错误码
---

|错误码|描述信息|
|----|----|
|`500`|参数错误|
|`200`|请求成功|

platform支持
---

|platform|参数|
|----|----|
|`binance`|binance|
|`huobipro`|huobipro|
|`okex`|okex|
|`zb`|zb|
|`bit-z`|bit-z|
|`bittrex`|bittrex|
|`gdax`|gdax|
|`zaif`|zaif|
|`coinegg`|coinegg|
|`lhang`|lhang|
|`coincheck`|coincheck|
|`allcoin`|allcoin|
|`okcoin-intl`|okcoin-intl|



获取异动资讯
---
|接口|版本|描述|
|---|---|---|
|[/v1/getchangemsg](#获取异动资讯)||获取异动资讯|

#### 参数列表
|参数名|参数类型|描述|是否必选|
|---|---|---|---|

#### 请求举例

```shell
$ curl -XGET http://api.bizhihui.info/v1/getchangemsg?token={token}
```

#### 返回结果

```shell
$ {
  "code": 200,
  "data": [
  {
  "title": "【异动监测：BNB媒体热度异动】",//标题
  "content": "据币智慧异动监测显示，北京时间10月24日 09:00，BNB发生媒体热度异动，媒体热度环比昨日环比+83.23%",//内容
  "update_time": 1540342801000  //更新时间，毫秒级别
  }
  ],
    "msg": "succeed"
    }

```

接口错误码
---

|错误码|描述信息|
|----|----|
|`500`|参数错误|
|`200`|请求成功|



获取异动指数
---
|接口|版本|描述|
|---|---|---|
|[/v1/getchangeindex](#获取异动指数)||获取异动指数|

#### 参数列表
|参数名|参数类型|描述|是否必选|
|---|---|---|---|

#### 请求举例

```shell
$ curl -XGET http://api.bizhihui.info/v1/getchangeindex?token={token}
```

#### 返回结果

```shell
{
    "data": {
        "error": 0, // 错误码，0表示无错误
        "result": {
            "index": "100", // 异动指数
            "text": "当前市场交易波动高，成交额异动明显高于历史数据，多空、涨跌异动较明显，建议关注。" // 异动文案
        }
    }
}
```



获取异动事件列表
---
|接口|版本|描述|
|---|---|---|
|[/v1/getchangeevent](#获取异动事件列表)||获取异动事件列表|

#### 参数列表
|参数名|参数类型|描述|是否必选|
|---|---|---|---|

#### 请求举例

```shell
$ curl -XGET http://api.bizhihui.info/v1/getchangeevent?token={token}
```

#### 返回结果

```json
{
    "data": {
        "error": 0, // 错误码，0表示无错误
        "items": [
            {
                "changes": [ // 异动列表的表格数据
                    {
                        "_id": "5becc5124b0b27fde08d7c54",
                        "change": 7.828494095691138, // 异动值的增量，即对比上一次计算时的value值的增减量
                        "change_abs": 7.828494095691138, // 异动的增量绝对值
                        "change_fmt": "+782.85%", // 异动值的增量格式化后的字符串
                        "cn": "卡西诺币", // 币种中文名
                        "name": "volume", // 异动类型
                        "name_cn": "成交额异动", // 异动类型中文名
                        "percent_change_8am": -1.0918158292770386, // 币种当日涨跌（数据基于Coinmarketcap计算，早上8am开盘）
                        "percent_change_8am_str": "-1.09%", // 币种当日涨跌格式化后的字符串
                        "price_cny_str": "¥ 0.002", // 币种价格，人民币，格式化后的字符串
                        "price_line": "https://s2.coinmarketcap.com/generated/sparklines/web/7d/usd/45.png?_t=1542268020290", // 币种价格最近7日曲线
                        "price_local_str": "0.002", // 币种价格，本地化货币单位，默认人民币
                        "symbol": "CSC", // 币种symbol，来源Coinmarketcap
                        "symbol_id": "casinocoin", // 币种id，来源Coinmarketcap
                        "update_time": 1542243600004, // 数据计算时间
                        "value": 218679.28125, // 异动值
                        "value_fmt": "21.87万" // 异动值格式化后的字符串
                    }
                ],
                "cn": "成交额异动", // 异动类型中文名
                "enable": 1,
                "event_name": "bzh_unusual_volume",
                "format": {
                    "change": "percent",
                    "value": "number"
                },
                "frequency": "1h", // 数据计算间隔
                "length": 10, // changes数组的长度
                "menus": [ // 异动列表的表头菜单
                    {
                        "cn": "币种",
                        "name": "name"
                    },
                    {
                        "cn": "24h成交额(CNY)", // changes数组中value值的含义
                        "name": "volume"
                    },
                    {
                        "cn": "7天价格趋势/当日涨跌",
                        "name": "trend"
                    }
                ],
                "name": "volume", // 异动类型
                "open": 1,
                "size": 10,
                "update_time": 1542243600004,
                "update_time_str": "11.15 09:00"
            }
        ]
    }
}
```
