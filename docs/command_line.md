---
layout: page
title: 命令行工具
permalink: /命令行工具
nav_order: 8
---

# 命令行工具

使用 `featurize` 命令行工具，可以自动化得获取实例信息，占用/退还实例。

## 安装

通过下面的命令可以在任何地方安装 Featurize 的命令行工具。当然，你也可以直接在工作区中使用。

```shell
pip install --upgrade featurize
```

在使用命令行工具之前，请先到**控制台**中的「设置」->「开发者」中生成一个令牌；如果你在工作区中使用，则无需手动传入令牌；如果在外部使用，则需要通过 `-t` 参数来手动传入令牌。
{: .fe-info-block}

## 使用

目前提供了对实例操作相关的功能。

**查看所有实例状态**

```
>>> featurize instance ls
id                                    name    gpu                    price  idle
------------------------------------  ------  -------------------  -------  ------
4b6e2b1e-1e0e-4dda-b4b2-ca0fa6e083e3  大冰箱  GeForce GTX 1080 Ti      0.7  True
d28509ba-e2cd-4491-a136-d5de5cafe818  测试    GeForce GTX 1080 Ti      0.7  False
```

对于编程环境可使用 `featurize instance ls --raw` 来返回更详细的 JSON 格式的结果。
{: .fe-info-block}

**占用实例**

```
>>> featurize instance request 4b6e2b1e-1e0e-4dda-b4b2-ca0fa6e083e3
Successfully requested instance.
```

**退还实例**

```
>>> featurize instance release 4b6e2b1e-1e0e-4dda-b4b2-ca0fa6e083e3
Successfully released instance.
```

Tip：如果你在工作区内使用命令，可以直接通过环境变量 `$UUID` 得到当前实例的 ID 号。
{: .fe-info-block}

## 常见使用场景

1. **训练完毕后自动退还实例** 只需要在训练代码的最后加上 `featurize instance release xxxx` 的命令即可。
2. **自动抢占实例** 在平台实例满载的时候，你可以在本机定时使用 `featurize instance ls -r` 来遍历实例信息，当获取到可用实例时，通过 `featurize instance request xxxx` 来占用实例即可。

如果你对返回字段有任何疑问，可以直接在用户群中提出。
{: .fe-info-block}

