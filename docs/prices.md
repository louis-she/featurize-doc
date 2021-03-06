---
layout: page
title: 计费
permalink: /计费
nav_order: 7
---

# 计费

Featurize 的机器提供两种租用方式：**按量使用** 和 **长租**。

## 按量使用

按量使用会以实例每小时的单价从代金券或余额中进行扣费，如果用户有代金券，会优先使用代金券。

当代金券和余额同时为 0 时，系统会自动收回实例，所以在按量使用的过程中，请保证自己的余额充足。
{: .fe-warning-block }

## 长租

Featurize 提供三种时长的长租：1 天、7 天、30 天。在长期租用前你需要支付固定的费用，然后就可以获取机器指定时长的使用权，使用期间你不能提前退还实例。

**关于机器退还方式**

长租机器到期后有两种收回方式：

1. 系统自动退还：机器到期后由系统直接释放机器，不需要用户手动处理。
2. 用户手动退还：机器到期后将不自动退还机器，而是以**按量计费**继续运行，用户此时可以自行退还实例。

**续租**

长租期间可以进行续租，可延长机器的使用时间。续租得方式和价格跟长租一样。

## 价格表

|   实例配置        | 每小时单价          | 日租（1天） | 周租（7天） |  月租（30天） |
|:-------------:  |:------------------:|:------:|:------: |:------: |
|    P106 常规机型        |  0.7 元  |  9 元  | 48 元   | 180 元 |
|    1660 常规机型        |  0.9 元  |  12 元 | 60 元   | 225 元 |
|    1080 Ti 常规机型     |  1.2 元  |  23 元 | 140 元   | 520 元 |
|    2080 Ti 常规机型     |  2.0 元  |  38 元 | 230 元  | 860 元 |
|    3080 常规机型        |  2.4 元  |  46 元 | 280 元  | 1040 元 |
|    3090 常规机型        |  3.6 元  |  70 元 | 420 元  | 1500 元 |
|    V100 常规机型        |  4.5 元  |  90 元 | 550 元  | 2000 元 |
|    A6000 常规机型        |  8 元  |  150 元 | 950 元  | 3500 元 |


## 存储计费

每个用户的 work 目录默认有 20G 的免费存储额度，超过部分按照 0.01元/G/小时 进行扣费，建议用户管理好自己的代码存储，可以使用 `du -sh /cloud` 来查看自己的使用空间。

用户数据集存储空间目前免费，只要大家不滥用我们会一直免费。

## 退款

退款走线下流程，可直接微信群联系管理员。可退款公式如下：

```
可退余额 = 总充值金额 - 总使用金额（含代金券）
```

退款后清空代金券和余额。

## 发票

满 200 元充值以后，于当周的周三 20:00之前，将用户名、发票抬头、税号以及接收发票的邮箱发送到 invoice@featurize.ai，发票将于次日（当周周四）开具，逾期申请将顺延到下一周进行开具，请悉知。发票内容是：技术服务费，无法开具维修费用、采购费用、服务器费用等等非营业范围内容。
