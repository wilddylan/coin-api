# coin-api
主流币种、交易所、API 接口文档（自制稳定），如有特殊需求，提交 issue 即可



### 接口文档

HOST：http://95.179.153.66:8080

#### 获取币种列表

API 地址：/data/coinList

API 参数：无需，不分页，总共结果 700 个左右

API 请求样例：GET http://95.179.153.66:8080/data/coinList

```json
{
  "code": 1,
  "message": "成功",
  "data": Array[674][
    {
      "currency": "1",
      "fullName": "TrueChain",
      "fullNameZh": null,
      "introductionZh": "初链（TrueChain）是全球最早的PBFT-POW混合共识公链之一。PoW/PoS等单一共识公有链，目前遇到性能瓶颈的问题，而DPOS/DBFT等基于单一共识的改进型公有链，有中心化的问题。TRUE既具备高性能，也足够去中心化。众所周知，PoW及PBFT共识机制的规模化和安全性久经考验。初链混合共识将PBFT和PoW共识结合在一起，解决了公有链领域最重要的问题: 去中心化和性能之间的矛盾。PBFT协议保证价值流通和商业应用所需要的性能，而PBFT-PoW混合共识保证初链是一条公有链。",
      "circulation": "45000000",
      "totalCirculation": "100000000"
    }
  ]
}
```

#### 获取某一币种主流交易所价格

API 地址：/data/coinPrize
API 参数：国家（目前支持 zh、en，分别查 RMB、USD 价格）、币种名称（来自币种列表中的 currency 字段）

API 请求样例1：GET http://95.179.153.66:8080/data/coinPrize/zh/BTC

```json
// http://95.179.153.66:8080/data/coinPrize/zh/BTC

{
  "code": 1,
  "message": "成功",
  "data": Array[19][
    {
      "exchangeId": "2",
      "exchangeName": "bitfinex",
      "symbol": "tBTCUSD",
      "base": "BTC",
      "quote": "USD",
      "quotePrice": "11392",
      "price": "79744",
      "chg": "-0.0395"
    },
    {
      "exchangeId": "2",
      "exchangeName": "bitfinex",
      "symbol": "tBTCEUR",
      "base": "BTC",
      "quote": "EUR",
      "quotePrice": "10071",
      "price": "79531.8955",
      "chg": "-0.0398"
    },
    {
      "exchangeId": "2",
      "exchangeName": "bitfinex",
      "symbol": "tBTCGBP",
      "base": "BTC",
      "quote": "GBP",
      "quotePrice": "9459.2",
      "price": "83242.7572",
      "chg": "-0.0401"
    },
    {
      "exchangeId": "2",
      "exchangeName": "bitfinex",
      "symbol": "tBTCJPY",
      "base": "BTC",
      "quote": "JPY",
      "quotePrice": "1203700",
      "price": "78049.1117",
      "chg": "-0.0397"
    },
    {
      "exchangeId": "1",
      "exchangeName": "火币pro",
      "symbol": "btcusdt",
      "base": "BTC",
      "quote": "USDT",
      "quotePrice": "11910.3",
      "price": "83372.1",
      "chg": "0.0026"
    },
    {
      "exchangeId": "3",
      "exchangeName": "币安",
      "symbol": "BTCUSDT",
      "base": "BTC",
      "quote": "USDT",
      "quotePrice": "11383.8",
      "price": "79686.6",
      "chg": "-0.0361"
    },
    {
      "exchangeId": "5",
      "exchangeName": "OKEx",
      "symbol": "btc_usdt",
      "base": "BTC",
      "quote": "USDT",
      "quotePrice": "11386.6",
      "price": "79706.2",
      "chg": "-0.0358"
    },
    {
      "exchangeId": "6",
      "exchangeName": "Gate",
      "symbol": "BTC_USDT",
      "base": "BTC",
      "quote": "USDT",
      "quotePrice": "11381.1",
      "price": "79667.7",
      "chg": "-0.0366"
    },
    {
      "exchangeId": "8",
      "exchangeName": "ZB",
      "symbol": "btcusdt",
      "base": "BTC",
      "quote": "USDT",
      "quotePrice": "11386.7",
      "price": "79706.9",
      "chg": "0.0067"
    },
    {
      "exchangeId": "8",
      "exchangeName": "ZB",
      "symbol": "btcqc",
      "base": "BTC",
      "quote": "QC",
      "quotePrice": "80328.4",
      "price": "80328.3197",
      "chg": "0.0066"
    },
    {
      "exchangeId": "13",
      "exchangeName": "币蛋",
      "symbol": "btc_usdt",
      "base": "BTC",
      "quote": "USDT",
      "quotePrice": "11387.3",
      "price": "79711.1",
      "chg": "0.0013"
    },
    {
      "exchangeId": "9",
      "exchangeName": "Hitbtc",
      "symbol": "BTCUSD",
      "base": "BTC",
      "quote": "USD",
      "quotePrice": "11392.9",
      "price": "79750.3",
      "chg": "-0.0364"
    },
    {
      "exchangeId": "9",
      "exchangeName": "Hitbtc",
      "symbol": "BTCDAI",
      "base": "BTC",
      "quote": "DAI",
      "quotePrice": "11394.8",
      "price": "78782.5077",
      "chg": "-0.0336"
    },
    {
      "exchangeId": "9",
      "exchangeName": "Hitbtc",
      "symbol": "BTCEURS",
      "base": "BTC",
      "quote": "EURS",
      "quotePrice": "10204.7",
      "price": "79924.8432",
      "chg": "-0.0349"
    },
    {
      "exchangeId": "9",
      "exchangeName": "Hitbtc",
      "symbol": "BTCTUSD",
      "base": "BTC",
      "quote": "TUSD",
      "quotePrice": "11379",
      "price": "79613.1735",
      "chg": "-0.0388"
    },
    {
      "exchangeId": "11",
      "exchangeName": "CoinTiger",
      "symbol": "btcusdt",
      "base": "BTC",
      "quote": "USDT",
      "quotePrice": "11385.2",
      "price": "79696.4",
      "chg": "-0.0384"
    },
    {
      "exchangeId": "12",
      "exchangeName": "FCoin",
      "symbol": "btcusdt",
      "base": "BTC",
      "quote": "USDT",
      "quotePrice": "11385.9",
      "price": "79701.3",
      "chg": "-0.0359"
    },
    {
      "exchangeId": "10",
      "exchangeName": "CoinEx",
      "symbol": "BTCUSDT",
      "base": "BTC",
      "quote": "USDT",
      "quotePrice": "11385.1",
      "price": "79695.7",
      "chg": "-0.0362"
    },
    {
      "exchangeId": "10",
      "exchangeName": "CoinEx",
      "symbol": "BTCBCH",
      "base": "BTC",
      "quote": "BCH",
      "quotePrice": "22.32",
      "price": "68523.1142",
      "chg": "0.01"
    }
  ]
}
```

API 请求样例2：GET http://95.179.153.66:8080/data/coinPrize/en/BTC

```json
// 20190811111338
// http://95.179.153.66:8080/data/coinPrize/en/BTC

{
  "code": 1,
  "message": "成功",
  "data": Array[19][
    {
      "exchangeId": "2",
      "exchangeName": "bitfinex",
      "symbol": "tBTCUSD",
      "base": "BTC",
      "quote": "USD",
      "quotePrice": "11395",
      "price": "11395",
      "chg": "-0.0392"
    },
    {
      "exchangeId": "2",
      "exchangeName": "bitfinex",
      "symbol": "tBTCEUR",
      "base": "BTC",
      "quote": "EUR",
      "quotePrice": "10072",
      "price": "11362.8275",
      "chg": "-0.0397"
    },
    {
      "exchangeId": "2",
      "exchangeName": "bitfinex",
      "symbol": "tBTCGBP",
      "base": "BTC",
      "quote": "GBP",
      "quotePrice": "9459.2",
      "price": "11891.8225",
      "chg": "-0.0401"
    },
    {
      "exchangeId": "2",
      "exchangeName": "bitfinex",
      "symbol": "tBTCJPY",
      "base": "BTC",
      "quote": "JPY",
      "quotePrice": "1203700",
      "price": "11149.8731",
      "chg": "-0.0397"
    },
    {
      "exchangeId": "1",
      "exchangeName": "火币pro",
      "symbol": "btcusdt",
      "base": "BTC",
      "quote": "USDT",
      "quotePrice": "11900",
      "price": "11900",
      "chg": "0.0017"
    },
    {
      "exchangeId": "3",
      "exchangeName": "币安",
      "symbol": "BTCUSDT",
      "base": "BTC",
      "quote": "USDT",
      "quotePrice": "11387.8",
      "price": "11387.8",
      "chg": "-0.0354"
    },
    {
      "exchangeId": "5",
      "exchangeName": "OKEx",
      "symbol": "btc_usdt",
      "base": "BTC",
      "quote": "USDT",
      "quotePrice": "11388",
      "price": "11388",
      "chg": "-0.035"
    },
    {
      "exchangeId": "6",
      "exchangeName": "Gate",
      "symbol": "BTC_USDT",
      "base": "BTC",
      "quote": "USDT",
      "quotePrice": "11381.1",
      "price": "11381.1",
      "chg": "-0.0363"
    },
    {
      "exchangeId": "8",
      "exchangeName": "ZB",
      "symbol": "btcusdt",
      "base": "BTC",
      "quote": "USDT",
      "quotePrice": "11388.5",
      "price": "11388.5",
      "chg": "0.0069"
    },
    {
      "exchangeId": "8",
      "exchangeName": "ZB",
      "symbol": "btcqc",
      "base": "BTC",
      "quote": "QC",
      "quotePrice": "80355.6",
      "price": "11479.3599",
      "chg": "0.007"
    },
    {
      "exchangeId": "13",
      "exchangeName": "币蛋",
      "symbol": "btc_usdt",
      "base": "BTC",
      "quote": "USDT",
      "quotePrice": "11387.3",
      "price": "11387.3",
      "chg": "0.0013"
    },
    {
      "exchangeId": "9",
      "exchangeName": "Hitbtc",
      "symbol": "BTCUSD",
      "base": "BTC",
      "quote": "USD",
      "quotePrice": "11391.3",
      "price": "11391.3",
      "chg": "-0.0361"
    },
    {
      "exchangeId": "9",
      "exchangeName": "Hitbtc",
      "symbol": "BTCDAI",
      "base": "BTC",
      "quote": "DAI",
      "quotePrice": "11394.8",
      "price": "11254.644",
      "chg": "-0.0336"
    },
    {
      "exchangeId": "9",
      "exchangeName": "Hitbtc",
      "symbol": "BTCEURS",
      "base": "BTC",
      "quote": "EURS",
      "quotePrice": "10204.7",
      "price": "11417.8347",
      "chg": "-0.0349"
    },
    {
      "exchangeId": "9",
      "exchangeName": "Hitbtc",
      "symbol": "BTCTUSD",
      "base": "BTC",
      "quote": "TUSD",
      "quotePrice": "11379",
      "price": "11373.3105",
      "chg": "-0.0388"
    },
    {
      "exchangeId": "11",
      "exchangeName": "CoinTiger",
      "symbol": "btcusdt",
      "base": "BTC",
      "quote": "USDT",
      "quotePrice": "11390.1",
      "price": "11390.1",
      "chg": "-0.0379"
    },
    {
      "exchangeId": "12",
      "exchangeName": "FCoin",
      "symbol": "btcusdt",
      "base": "BTC",
      "quote": "USDT",
      "quotePrice": "11389.7",
      "price": "11389.7",
      "chg": "-0.035"
    },
    {
      "exchangeId": "10",
      "exchangeName": "CoinEx",
      "symbol": "BTCUSDT",
      "base": "BTC",
      "quote": "USDT",
      "quotePrice": "11391",
      "price": "11391",
      "chg": "-0.0346"
    },
    {
      "exchangeId": "10",
      "exchangeName": "CoinEx",
      "symbol": "BTCBCH",
      "base": "BTC",
      "quote": "BCH",
      "quotePrice": "22.32",
      "price": "9789.0163",
      "chg": "0.01"
    }
  ]
}
```

#### 字段模型

```java
@Data
public class Currency {
	/**
	 * 币种简称
	 */
	private String currency;
	/**
	 * 币种全称
	 */
	@JSONField(name = "fullname")
	private String fullName;
	/**
	 * 币种中文名
	 */
	@JSONField(name = "fullname_zh")
	private String fullNameZh;
	/**
	 * 币种介绍
	 */
	@JSONField(name = "introduction_zh")
	private String introductionZh;
	/**
	 * 流通量
	 */
	private String circulation;
	/**
	 * 发行量
	 */
	@JSONField(name = "total_circulation")
	private String totalCirculation;

}
```

```java
@Data
public class MarketCurrency {
	/**
	 * 交易所ID
	 */
	@JSONField(name = "exchange_id")
	private String exchangeId;
	/**
	 * 交易所名称
	 */
	@JSONField(name = "exchange_name")
	private String exchangeName;
	/**
	 * 交易对
	 */
	private String symbol;
	/**
	 * 交易货币
	 */
	private String base;
	/**
	 * 计量货币
	 */
	private String quote;
	/**
	 * 计量货币价格
	 */
	@JSONField(name = "quote_price")
	private String quotePrice;
	/**
	 * 币种价格
	 */
	private String price;
	/**
	 * 24H价格涨幅
	 */
	private String chg;

}
```
