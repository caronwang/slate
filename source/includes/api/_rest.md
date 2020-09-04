# REST API

## 账户

### 获取账户余额


> 返回结果如下:

```json
{
    "code":"0",
    "msg":"",
    "data":[
       {
            "uTime":"1597026383085",
            "totalEq":"41624.32",
            "isoEq":"3624.32",
            "adjEq":"41624.32",
            "imr":"4162.33",
            "mmr":"4",
            "mgnRatio":"41624.32",
            "details":[
                {
                    "ccy":"BTC",
                    "eq":"123",
                    "availEq":"1234",
                    "availBal":"1415",
                    "frozenBal":"14",
                    "upl":"124",
                    "mgnRatio":"124",
                    "interest":"12",
                    "liab":"1"
                },
                {
                    "ccy":"ETH",
                    "eq":"223",
                    "availEq":"2234",
                    "availBal":"415",
                    "frozenBal":"141",
                    "upl":"124",
                    "mgnRatio":"124",
                    "interest":"0",
                    "liab":"0"
                }
            ]
        }
    ]
}
```

获取账户中资金余额信息。

#### 限速  20次/2s 

#### HTTP请求

`GET /api/v5/account/balance?ccy=BTC,ETH`

#### 请求参数

| 参数名 | 参数类型 | 是否必须 | 描述                                     |
| :----- | :------- | :------- | :--------------------------------------- |
| ccy    | String   | 否       | 币种<br>支持多币种查询，币种之间逗号分隔 |

#### 返回参数

| **参数名** | **类型** | **描述**                                                     |
| :--------- | :------- | :----------------------------------------------------------- |
| uTime      | String   | 账户更新时间 Unix时间戳的毫秒数格式,如:1597026383085。       |
| totalEq    | String   | 美金层面权益（交易账户，单币种保证金账户，跨币种保证金账户） |
| isoEq      | String   | 美金层面逐仓仓位权益 （单币种保证金账户，跨币种保证金账户）  |
| adjEq      | String   | 美金层面有效保证金（跨币种保证金账户）                       |
| imr        | String   | 美金层面占用保证金（跨币种保证金账户）                       |
| mmr        | String   | 美金层面维持保证金（跨币种保证金账户）                       |
| mgnRatio   | String   | 美金层面保证金率（跨币种保证金账户）                         |
| details    | Array    | 各币种资产详细信息                                           |
| ccy        | String   | 币种                                                         |
| eq         | String   | 币种总权益                                                   |
| availEq    | String   | 可用保证金                                                   |
| availBal   | String   | 可用余额                                                     |
| frozenBal  | String   | 币种占用金额                                                 |
| liab       | String   | 币种负债额                                                   |
| upl        | String   | 未实现盈亏                                                   |
| mgnRatio   | String   | 保证金率                                                     |
| interest   | String   | 计息                                                         |

<aside class="notice">
免息额度和折算率都是公共数据，不在账户接口内展示
</aside>

## 资金

### 获取充值地址信息

> 返回结果如下:

```json
{
    "code":"0",
    "msg":"",
    "data":[
       {
            "uTime":"1597026383085",
            "totalEq":"41624.32",
            "isoEq":"3624.32",
            "adjEq":"41624.32",
            "imr":"4162.33",
            "mmr":"4",
            "mgnRatio":"41624.32",
            "details":[
                {
                    "ccy":"BTC",
                    "eq":"123",
                    "availEq":"1234",
                    "availBal":"1415",
                    "frozenBal":"14",
                    "upl":"124",
                    "mgnRatio":"124",
                    "interest":"12",
                    "liab":"1"
                },
                {
                    "ccy":"ETH",
                    "eq":"223",
                    "availEq":"2234",
                    "availBal":"415",
                    "frozenBal":"141",
                    "upl":"124",
                    "mgnRatio":"124",
                    "interest":"0",
                    "liab":"0"
                }
            ]
        }
    ]
}
```

获取账户中资金余额信息。

#### 限速  20次/2s 

#### HTTP请求

`GET /api/v5/account/balance?ccy=BTC,ETH`

#### 请求参数

| 参数名 | 参数类型 | 是否必须 | 描述                                     |
| :----- | :------- | :------- | :--------------------------------------- |
| ccy    | String   | 否       | 币种<br>支持多币种查询，币种之间逗号分隔 |

#### 返回参数

| **参数名** | **类型** | **描述**                                                     |
| :--------- | :------- | :----------------------------------------------------------- |
| uTime      | String   | 账户更新时间 Unix时间戳的毫秒数格式,如:1597026383085。       |
| totalEq    | String   | 美金层面权益（交易账户，单币种保证金账户，跨币种保证金账户） |
| isoEq      | String   | 美金层面逐仓仓位权益 （单币种保证金账户，跨币种保证金账户）  |
| adjEq      | String   | 美金层面有效保证金（跨币种保证金账户）                       |
| imr        | String   | 美金层面占用保证金（跨币种保证金账户）                       |
| mmr        | String   | 美金层面维持保证金（跨币种保证金账户）                       |
| mgnRatio   | String   | 美金层面保证金率（跨币种保证金账户）                         |
| details    | Array    | 各币种资产详细信息                                           |
| ccy        | String   | 币种                                                         |
| eq         | String   | 币种总权益                                                   |
| availEq    | String   | 可用保证金                                                   |
| availBal   | String   | 可用余额                                                     |
| frozenBal  | String   | 币种占用金额                                                 |
| liab       | String   | 币种负债额                                                   |
| upl        | String   | 未实现盈亏                                                   |
| mgnRatio   | String   | 保证金率                                                     |
| interest   | String   | 计息                                                         |

<aside class="notice">
免息额度和折算率都是公共数据，不在账户接口内展示
</aside>


## 交易

### 下单


> 返回结果如下:

```json
{
    "code":"0",
    "msg":"",
    "data":[
       {
            "uTime":"1597026383085",
            "totalEq":"41624.32",
            "isoEq":"3624.32",
            "adjEq":"41624.32",
            "imr":"4162.33",
            "mmr":"4",
            "mgnRatio":"41624.32",
            "details":[
                {
                    "ccy":"BTC",
                    "eq":"123",
                    "availEq":"1234",
                    "availBal":"1415",
                    "frozenBal":"14",
                    "upl":"124",
                    "mgnRatio":"124",
                    "interest":"12",
                    "liab":"1"
                },
                {
                    "ccy":"ETH",
                    "eq":"223",
                    "availEq":"2234",
                    "availBal":"415",
                    "frozenBal":"141",
                    "upl":"124",
                    "mgnRatio":"124",
                    "interest":"0",
                    "liab":"0"
                }
            ]
        }
    ]
}
```

获取账户中资金余额信息。

#### 限速  20次/2s 

#### HTTP请求

`GET /api/v5/account/balance?ccy=BTC,ETH`

#### 请求参数

| 参数名 | 参数类型 | 是否必须 | 描述                                     |
| :----- | :------- | :------- | :--------------------------------------- |
| ccy    | String   | 否       | 币种<br>支持多币种查询，币种之间逗号分隔 |

#### 返回参数

| **参数名** | **类型** | **描述**                                                     |
| :--------- | :------- | :----------------------------------------------------------- |
| uTime      | String   | 账户更新时间 Unix时间戳的毫秒数格式,如:1597026383085。       |
| totalEq    | String   | 美金层面权益（交易账户，单币种保证金账户，跨币种保证金账户） |
| isoEq      | String   | 美金层面逐仓仓位权益 （单币种保证金账户，跨币种保证金账户）  |
| adjEq      | String   | 美金层面有效保证金（跨币种保证金账户）                       |
| imr        | String   | 美金层面占用保证金（跨币种保证金账户）                       |
| mmr        | String   | 美金层面维持保证金（跨币种保证金账户）                       |
| mgnRatio   | String   | 美金层面保证金率（跨币种保证金账户）                         |
| details    | Array    | 各币种资产详细信息                                           |
| ccy        | String   | 币种                                                         |
| eq         | String   | 币种总权益                                                   |
| availEq    | String   | 可用保证金                                                   |
| availBal   | String   | 可用余额                                                     |
| frozenBal  | String   | 币种占用金额                                                 |
| liab       | String   | 币种负债额                                                   |
| upl        | String   | 未实现盈亏                                                   |
| mgnRatio   | String   | 保证金率                                                     |
| interest   | String   | 计息                                                         |

<aside class="notice">
免息额度和折算率都是公共数据，不在账户接口内展示
</aside>

## 行情数据

### 获取ticker基础信息


> 返回结果如下:

```json
{
    "code":"0",
    "msg":"",
    "data":[
       {
            "uTime":"1597026383085",
            "totalEq":"41624.32",
            "isoEq":"3624.32",
            "adjEq":"41624.32",
            "imr":"4162.33",
            "mmr":"4",
            "mgnRatio":"41624.32",
            "details":[
                {
                    "ccy":"BTC",
                    "eq":"123",
                    "availEq":"1234",
                    "availBal":"1415",
                    "frozenBal":"14",
                    "upl":"124",
                    "mgnRatio":"124",
                    "interest":"12",
                    "liab":"1"
                },
                {
                    "ccy":"ETH",
                    "eq":"223",
                    "availEq":"2234",
                    "availBal":"415",
                    "frozenBal":"141",
                    "upl":"124",
                    "mgnRatio":"124",
                    "interest":"0",
                    "liab":"0"
                }
            ]
        }
    ]
}
```

获取账户中资金余额信息。

#### 限速  20次/2s 

#### HTTP请求

`GET /api/v5/account/balance?ccy=BTC,ETH`

#### 请求参数

| 参数名 | 参数类型 | 是否必须 | 描述                                     |
| :----- | :------- | :------- | :--------------------------------------- |
| ccy    | String   | 否       | 币种<br>支持多币种查询，币种之间逗号分隔 |

#### 返回参数

| **参数名** | **类型** | **描述**                                                     |
| :--------- | :------- | :----------------------------------------------------------- |
| uTime      | String   | 账户更新时间 Unix时间戳的毫秒数格式,如:1597026383085。       |
| totalEq    | String   | 美金层面权益（交易账户，单币种保证金账户，跨币种保证金账户） |
| isoEq      | String   | 美金层面逐仓仓位权益 （单币种保证金账户，跨币种保证金账户）  |
| adjEq      | String   | 美金层面有效保证金（跨币种保证金账户）                       |
| imr        | String   | 美金层面占用保证金（跨币种保证金账户）                       |
| mmr        | String   | 美金层面维持保证金（跨币种保证金账户）                       |
| mgnRatio   | String   | 美金层面保证金率（跨币种保证金账户）                         |
| details    | Array    | 各币种资产详细信息                                           |
| ccy        | String   | 币种                                                         |
| eq         | String   | 币种总权益                                                   |
| availEq    | String   | 可用保证金                                                   |
| availBal   | String   | 可用余额                                                     |
| frozenBal  | String   | 币种占用金额                                                 |
| liab       | String   | 币种负债额                                                   |
| upl        | String   | 未实现盈亏                                                   |
| mgnRatio   | String   | 保证金率                                                     |
| interest   | String   | 计息                                                         |

<aside class="notice">
免息额度和折算率都是公共数据，不在账户接口内展示
</aside>

## 公共数据

### 获取交易产品基础信息


> 返回结果如下:

```json
{
    "code":"0",
    "msg":"",
    "data":[
       {
            "uTime":"1597026383085",
            "totalEq":"41624.32",
            "isoEq":"3624.32",
            "adjEq":"41624.32",
            "imr":"4162.33",
            "mmr":"4",
            "mgnRatio":"41624.32",
            "details":[
                {
                    "ccy":"BTC",
                    "eq":"123",
                    "availEq":"1234",
                    "availBal":"1415",
                    "frozenBal":"14",
                    "upl":"124",
                    "mgnRatio":"124",
                    "interest":"12",
                    "liab":"1"
                },
                {
                    "ccy":"ETH",
                    "eq":"223",
                    "availEq":"2234",
                    "availBal":"415",
                    "frozenBal":"141",
                    "upl":"124",
                    "mgnRatio":"124",
                    "interest":"0",
                    "liab":"0"
                }
            ]
        }
    ]
}
```

获取账户中资金余额信息。

#### 限速  20次/2s 

#### HTTP请求

`GET /api/v5/account/balance?ccy=BTC,ETH`

#### 请求参数

| 参数名 | 参数类型 | 是否必须 | 描述                                     |
| :----- | :------- | :------- | :--------------------------------------- |
| ccy    | String   | 否       | 币种<br>支持多币种查询，币种之间逗号分隔 |

#### 返回参数

| **参数名** | **类型** | **描述**                                                     |
| :--------- | :------- | :----------------------------------------------------------- |
| uTime      | String   | 账户更新时间 Unix时间戳的毫秒数格式,如:1597026383085。       |
| totalEq    | String   | 美金层面权益（交易账户，单币种保证金账户，跨币种保证金账户） |
| isoEq      | String   | 美金层面逐仓仓位权益 （单币种保证金账户，跨币种保证金账户）  |
| adjEq      | String   | 美金层面有效保证金（跨币种保证金账户）                       |
| imr        | String   | 美金层面占用保证金（跨币种保证金账户）                       |
| mmr        | String   | 美金层面维持保证金（跨币种保证金账户）                       |
| mgnRatio   | String   | 美金层面保证金率（跨币种保证金账户）                         |
| details    | Array    | 各币种资产详细信息                                           |
| ccy        | String   | 币种                                                         |
| eq         | String   | 币种总权益                                                   |
| availEq    | String   | 可用保证金                                                   |
| availBal   | String   | 可用余额                                                     |
| frozenBal  | String   | 币种占用金额                                                 |
| liab       | String   | 币种负债额                                                   |
| upl        | String   | 未实现盈亏                                                   |
| mgnRatio   | String   | 保证金率                                                     |
| interest   | String   | 计息                                                         |

<aside class="notice">
免息额度和折算率都是公共数据，不在账户接口内展示
</aside>


