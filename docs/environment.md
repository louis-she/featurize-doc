---
layout: page
title: 开发环境
permalink: /开发环境
nav_order: 5
---

# 开发环境

Featurize 预装了常用的机器学习/深度学习框架，通常你不需要进行任何配置就可以直接使用。如果机器没有你所需要的包，你也完全可以自行安装。

你也可以在用户群中提预装包的需求，我们很乐意采纳这些意见。
{: .fe-success-block}

## Python 环境

服务器所使用的 Python 版本是 `3.7.4`，安装在 `/home/jovyan/.pyenv/versions/3.7.4` 目录中。我们预先安装了大多数常用的 Python 包，如果你需要的包没有预装，你也可以使用下面的命令直接安装

```shell
pip install --user some-awesome-package
```

注意，如果不加 `--user` 参数，则退还实例后你所安装的包将丢失；加上 `--user` 参数会将包安装至 `work` 目录中，这样会永久保存。
{: .fe-warning-block}

## CUDA 版本和预装的框架

目前针对 `TensorFlow 1` 和 `TensorFlow 2` 提供了两种环境，你可以使用右下角的快速按钮来切换环境。

![](/asset/environment-switch.png)

不同环境预装框架的版本参见下表

|   CUDA 版本        |  TensorFlow 版本         | PyTorch 版本 | Caffe 版本 |
|:-------------:  |:------------------:|:------:|:------:
|    10.1        |  2.2  |  1.6  | 1.0.0   |
|    10.0        |  1.15  |  N/A  | N/A   |
