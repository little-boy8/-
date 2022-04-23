
## 接口说明


## 状态说明

| _状态码_ | _含义_              | _说明_                                              |
| -------- | ------------------- | --------------------------------------------------- |
| 200      | OK                  | 请求成功                                            |
| 201      | CREATED             | 创建成功                                            |
| 204      | DELETED             | 删除成功                                            |
| 400      | BAD REQUEST         | 请求的地址不存在或者包含不支持的参数                |
| 401      | UNAUTHORIZED        | 未授权                                              |
| 403      | FORBIDDEN           | 被禁止访问                                          |
| 404      | NOT FOUND           | 请求的资源不存在                                    |
| 422      | Unprocesable entity | [POST/PUT/PATCH] 当创建一个对象时，发生一个验证错误 |
| 500      | INTERNAL SERVER ERROR | 内部错误   


## 前台接口

#### 1、login (登录)

请求地址：https://api.it120.cc/xiaochengxu/user/m/login

请求方式：post

请求参数：

|  名称   |  类型  | 说明                                       |
| :-----: | :----: | ----------------------------------------- |
|  mobile   | string | 账号/手机号 必填                         |
|  pwd   | string | 密码 必填                                   |
|  deviceId  | string | 用户设备id 16503594199396246947 必填    |
|  deviceName  | string | 用户设备名称 Nexus 5 必填              |
|  token  | string | 用户登录标识 非必填                         |

返回数据：

| 名称  |  类型  | 说明                                                         |
| :---: | :----: | ------------------------------------------------------------ |
| code | number | 状态码                                     |
| msg  | number | 状态描述                                    |
| data  | object  | 用户标识  包含： token:string       uid:number    |



#### 2、index banner (轮播图片)

请求地址：https://api.it120.cc/xiaochengxu/banner/list

请求方式：get

请求参数：

|  名称   |  类型  | 说明                                         |
| :-----: | :----: | -------------------------------------------- |
|  type   | string | 图片类型 传indexBanner即可，为空返回所有类型   |
|  token  | string | 用户登录标识 非必填                        |

返回数据：

| 名称  |  类型  | 说明                                                         |
| :---: | :----: | ------------------------------------------------------------ |
| code | number | 状态码                                     |
| msg  | number | 状态描述                                    |
| data  | array  | 轮播图数据数组                           |

返回数据结构示例：

```json
{
    "code":0,
    "msg":"success",
    "data":[
        {
            "businessId": 0,
            "dateAdd": "2022-02-02 16:04:11",
            "dateUpdate": "2022-02-02 16:19:17",
            "id": 204167,
            "linkUrl": "https://github.com/JoeshuTT/v-shop",
            "paixu": 0,
            "picUrl": "https://dcdn.it120.cc/2022/02/02/d0442c95-cd44-435a-888d-2539c5399334.png",
            "remark": "跳转github v-shop",
            "status": 0,
            "statusStr": "显示",
            "title": "首页banner3",
            "type": "indexBanner",
            "userId": 1605
        },
        {
            ......
        },
        {
            ......
        }
        ......
    ]
}
```



#### 3、goods list (商品列表)

请求地址：https://api.it120.cc/xiaochengxu/shop/goods/list/v2

请求方式：post

请求参数：

|  名称   |  类型  | 说明                                         |
| :-----: | :----: | -------------------------------------------- |
|  categoryId  | number | 商品类别，为空返回所有类型商品   |
|  page   | number | 商品列表页码，必填 1                 |
|  pageSize  | number | 每页显示条数，必填 10      |
|  token   | string | 用户登录标识 非必填                |

返回数据：

| 名称  |  类型  | 说明                                                         |
| :---: | :----: | ------------------------------------------------------------ |
| code | number | 状态码                                     |
| msg  | number | 状态描述                                    |
| data  | array  | 商品列表数据数组                           |

返回数据结构示例：

```json
{
    "code":0,
    "msg":"success",
    "data":{
        "result": [
            {
                "afterSale": "0",
                "categoryId": 272693,
                "characteristic": "本商城所有商品，都是测试商品，仅限线上调试，模拟交易流程",
                "commission": 0,
                "commissionSettleType": 0,
                "commissionType": 0,
                "commissionUserType": 0,
                "dateAdd": "2022-02-04 12:14:12",
                "dateUpdate": "2022-04-19 15:30:39",
                "fxType": 2,
                "gotScore": 500,
                "gotScoreType": 0,
                "hasAddition": false,
                "hasTourJourney": false,
                "hidden": 0,
                "id": 1052000,
                "kanjia": false,
                "kanjiaPrice": 0,
                "limitation": false,
                "logisticsId": 4727,
                "maxCoupons": 1,
                "miaosha": false,
                "minBuyNumber": 1,
                "minPrice": 1,
                "minScore": 0,
                "name": "实物商品（购买时需填写收货地址，支持售后）",
                "numberFav": 1,
                "numberGoodReputation": 5,
                "numberOrders": 21,
                "numberReputation": 5,
                "numberSells": 32,
                "originalPrice": 199,
                "overseas": false,
                "paixu": 0,
                "persion": 0,
                "pic": "https://dcdn.it120.cc/2022/02/04/fa78ff5e-553f-40f2-8c78-b7ab8ed8bd39.png",
                "pingtuan": false,
                "pingtuanPrice": 0,
                "priceShopSell": 0,
                "recommendStatus": 1,
                "recommendStatusStr": "推荐",
                "seckillBuyNumber": 0,
                "sellEnd": false,
                "sellStart": true,
                "shopId": 0,
                "status": 0,
                "statusStr": "上架",
                "storeAlert": false,
                "stores": 9967,
                "stores0Unsale": false,
                "type": 0,
                "unit": "件",
                "unusefulNumber": 0,
                "usefulNumber": 0,
                "userId": 1605,
                "vetStatus": 1,
                "views": 4613,
                "weight": 0,
            },
            {
                .....
            }
            ......
        ],
        "totalPage": 1,
        "totalRow": 12
    }
}
```



#### 4、category (商品类别)

请求地址：https://api.it120.cc/xiaochengxu/shop/goods/category/all

请求方式：get

请求参数：

| 名称      | 类型   | 说明     |
| --------- | ------ | -------- |
| token    | string | 用户标识 非必填 |

返回数据：

| 名称   | 类型    | 说明           |
| ------ | ------ | -------------- |
| code   | number | 状态码         |
| msg    | string | 状态信息       |
| data   | array  | 类别数据       |

返回数据结构示例：

```json
{
    "code":0,
    "msg":"success",
    "data":[
        {
            "id": 37962,
            "isUse": true,
            "level": 1,
            "name": "手机",
            "paixu": 1,
            "pid": 0,
            "shopId": 0,
            "userId": 1605
        },
        {
            .....
        }
        ......
    ]
    
}
```


-------- ↑以上接口都没有登录要求，↓以下接口都有登录要求 ----------
13382019200 a335006012A


#### 5、Shopping Cart (购物车)

请求地址：https://api.it120.cc/xiaochengxu/shopping-cart/info

请求方式：get

请求参数：

| 名称  | 类型       | 说明            |
| ----- | --------- | --------------- |
| token | string    | 登录标识，必填   |

返回数据：

| 名称  | 类型      | 说明     |
| ----- | -------- | -------- |
| code  | number   | 状态码   |
| msg   | string   | 状态信息 |
| data  | array    | 列表数据 |

返回数据结构示例：

```json
{
    "code":0,
    "msg":"success",
    "data":{
        "goodsStatus":[
            {
                "id": 1052000,
                "sellEnd": false,
                "sellStart": true,
                "status": 0,
                "statusStr": "上架",
                "stores": 9967
            }
            .....
        ],
        "items": [
            {
                "categoryId": 272693,
                "goodsId": 1052000,
                "key": "8949691c5df24eda0b040dea1698b170",
                "logisticsId": 4727,
                "minBuyNumber": 1,
                "name": "实物商品（购买时需填写收货地址，支持售后）",
                "number": 3,
                "pic": "https://dcdn.it120.cc/2022/02/04/fa78ff5e-553f-40f2-8c78-b7ab8ed8bd39.png",
                "price": 1,
                "score": 0,
                "selected": true,
                "shopId": 0,
                "status": 0,
                "statusStr": "上架",
                "stores": 9967,
                "weight": 0
            },
            .....
        ],
        "number": 6,
        "price": 7700,
        "score": 0,
        "shopList":[
            {
                "id": 0,
                "name": "其他",
                "serviceDistance": 99999999
            }
        ]
    }
}
```


#### 6、Shopping Cart Remove (购物车删除单个)

请求地址：https://api.it120.cc/xiaochengxu/shopping-cart/remove

请求方式：post

请求参数：

| 名称     | 类型    | 说明                 |
| -------- | ------ | -------------------- |
| key      | string | 列表商品标识，必填     |
| token    | string | 用户标识，必填         |

返回数据：

| 名称     | 类型       | 说明             |
| -------- | ---------- | --------------- |
| code     | number | 状态码               |
| msg      | string | 状态信息             |
| data     | object | 新的购物车列表数据    |

返回数据结构示例：

```json
{
    "code":0,
    "msg":"success",
    "data":{
        "goodsStatus":[
            {
                "id": 1052000,
                "sellEnd": false,
                "sellStart": true,
                "status": 0,
                "statusStr": "上架",
                "stores": 9967
            }
            .....
        ],
        "items": [
            {
                "categoryId": 272693,
                "goodsId": 1052000,
                "key": "8949691c5df24eda0b040dea1698b170",
                "logisticsId": 4727,
                "minBuyNumber": 1,
                "name": "实物商品（购买时需填写收货地址，支持售后）",
                "number": 3,
                "pic": "https://dcdn.it120.cc/2022/02/04/fa78ff5e-553f-40f2-8c78-b7ab8ed8bd39.png",
                "price": 1,
                "score": 0,
                "selected": true,
                "shopId": 0,
                "status": 0,
                "statusStr": "上架",
                "stores": 9967,
                "weight": 0
            },
            .....
        ],
        "number": 5,
        "price": 5101,
        "score": 0,
        "shopList":[
            {
                "id": 0,
                "name": "其他",
                "serviceDistance": 99999999
            }
        ]
    }
}
```

#### 6、Shopping Cart empty (购物车删除全部)

请求地址：https://api.it120.cc/xiaochengxu/shopping-cart/empty

请求方式：post

请求参数：

| 名称     | 类型    | 说明                 |
| -------- | ------ | -------------------- |
| token    | string | 用户标识，必填         |

返回数据：

| 名称     | 类型       | 说明             |
| -------- | ---------- | --------------- |
| code     | number | 状态码               |
| msg      | string | 状态信息             |



#### 7、modify number (修改购物车数量)

请求地址：https://api.it120.cc/xiaochengxu/shopping-cart/modifyNumber

请求方式：post

请求参数：

| 名称     | 类型    | 说明                 |
| -------- | ------ | -------------------- |
| number   | number | 新的商品数量          |
| key      | string | 列表商品标识，必填     |
| token    | string | 用户标识，必填         |

返回数据：

| 名称     | 类型       | 说明             |
| -------- | ---------- | --------------- |
| code     | number | 状态码               |
| msg      | string | 状态信息             |
| data     | object | 新的购物车列表数据    |

返回数据结构示例：

```json
{
    "code":0,
    "msg":"success",
    "data":{
        "goodsStatus":[
            {
                "id": 1052000,
                "sellEnd": false,
                "sellStart": true,
                "status": 0,
                "statusStr": "上架",
                "stores": 9967
            }
            .....
        ],
        "items": [
            {
                "categoryId": 272693,
                "goodsId": 1052000,
                "key": "8949691c5df24eda0b040dea1698b170",
                "logisticsId": 4727,
                "minBuyNumber": 1,
                "name": "实物商品（购买时需填写收货地址，支持售后）",
                "number": 3,
                "pic": "https://dcdn.it120.cc/2022/02/04/fa78ff5e-553f-40f2-8c78-b7ab8ed8bd39.png",
                "price": 1,
                "score": 0,
                "selected": true,
                "shopId": 0,
                "status": 0,
                "statusStr": "上架",
                "stores": 9967,
                "weight": 0
            },
            .....
        ],
        "number": 5,
        "price": 5101,
        "score": 0,
        "shopList":[
            {
                "id": 0,
                "name": "其他",
                "serviceDistance": 99999999
            }
        ]
    }
}
```



#### 8、 detail (商品详情)

请求地址：https://api.it120.cc/xiaochengxu/shop/goods/detail

请求方式：get

请求参数：

| 名称 | 类型   | 说明          |
| ---- | ------ | ------------ |
| id   | string | 商品id       |
| token | string | 用户登录标识 |

返回数据：

| 名称     | 类型       | 说明             |
| -------- | ---------- | --------------- |
| code     | number | 状态码               |
| msg      | string | 状态信息             |
| data     | object | 商品详情数据         |

返回数据结构示例：

```json
{
    "code":0,
    "msg":"success",
    "data":{
        "basicInfo":{
            "afterSale": "0,1,2",
            "categoryId": 37962,
            "commission": 0,
            "commissionSettleType": 0,
            "commissionType": 0,
            "commissionUserType": 0,
            "dateAdd": "2019-06-20 09:36:24",
            "dateUpdate": "2022-04-21 17:08:04",
            "fxType": 2,
            "gotScore": 0,
            "gotScoreType": 0,
            "hasAddition": false,
            "hasTourJourney": false,
            "hidden": 0,
            "id": 144614,
            "kanjia": false,
            "kanjiaPrice": 0,
            "limitation": false,
            "logisticsId": 4727,
            "maxCoupons": 1,
            "miaosha": false,
            "minBuyNumber": 1,
            "minPrice": 2099,
            "minPriceOriginal": 2099,
            "minScore": 0,
            "name": "Redmi K20[2种规格]",
            "numberFav": 28,
            "numberGoodReputation": 1,
            "numberOrders": 5,
            "numberReputation": 0,
            "numberSells": 5,
            "originalPrice": 2099,
            "overseas": false,
            "paixu": 0,
            "persion": 0,
            "pic": "https://cdn.it120.cc/apifactory/2019/06/20/b30cd900-8034-4a0d-88af-62f6cf042577.jpg",
            "pingtuan": false,
            "pingtuanPrice": 0,
            "propertyIds": ",13090,13093,",
            "recommendStatus": 0,
            "recommendStatusStr": "普通",
            "seckillBuyNumber": 0,
            "sellEnd": false,
            "sellStart": true,
            "shopId": 0,
            "status": 0,
            "statusStr": "上架",
            "storeAlert": false,
            "stores": 886,
            "stores0Unsale": false,
            "type": 0,
            "unusefulNumber": 0,
            "usefulNumber": 0,
            "userId": 1605,
            "vetStatus": 1,
            "views": 21369,
            "weight": 0
        },

    }
}
```



#### 9、coupons (优惠券)

请求地址：https://api.it120.cc/xiaochengxu/discounts/coupons

请求方式：get

请求参数：

| 名称 | 类型   | 说明   |
| ---- | ------ | ------ |
| token | string | 用户登录标识 |

返回数据：

| 名称     | 类型       | 说明             |
| -------- | ---------- | --------------- |
| code     | number | 状态码               |
| msg      | string | 状态信息             |
| data     | object | 优惠券列表数据       |

返回数据结构示例：

```json
{
    "code":0,
    "msg":"success",
    "data":[
        {
            "batchSendUid": -1,
            "dateEndDays": 7,
            "dateEndType": 1,
            "dateStartType": 1,
            "id": 10640,
            "moneyHreshold": 99,
            "moneyMax": 10,
            "moneyMin": 1,
            "moneyType": 0,
            "name": "满100元减1-10元",
            "needAmount": 0,
            "needScore": 1,
            "needSignedContinuous": 0,
            "numberGit": 77,
            "numberGitNumber": 70,
            "numberLeft": 929,
            "numberPersonMax": 999,
            "numberTotle": 999,
            "numberUsed": 0,
            "onlyFreight": false,
            "pwd": "Y",
            "sendBirthday": true,
            "sendInviteM": true,
            "sendInviteS": true,
            "sendRegister": true,
            "shopId": 0,
            "showInFront": true,
            "status": 0,
            "statusStr": "正常",
            "type": "随机金额券"
        },
        {
            ....
        }
    ]
}
```



------------------------------------------------
#### 9、发表评论

请求地址：/index/post_comment

请求方式：post

请求参数：

| 名称      | 类型   | 说明     |
| --------- | ------ | -------- |
| author    | string | 用户名称 |
| content   | string | 评论内容 |
| articleId | number | 文章id   |

返回数据：‘发表成功’   ‘发表失败’



#### 10、评论列表

请求地址：/index/get_comment

请求方式：get

请求参数：

| 名称      | 类型   | 说明   |
| --------- | ------ | ------ |
| articleId | string | 文章id |

返回数据：

|  名称   |  类型  | 说明         |
| :-----: | :----: | ------------ |
| author  | string | 用户名称     |
|  date   | string | 评论时间     |
| content | string | 评论完整内容 |



