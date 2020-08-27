---
layout: page
title: 工作区
permalink: /工作区
nav_order: 8
---

# 工作区

我们使用了原生的 [JupyterLab](https://jupyterlab.readthedocs.io/en/stable/){:target="_blank"} 作为的工作区的主界面。

![](/asset/workspace.png)

JupyterLab 原生提供的功能本文档不会覆盖，感兴趣的同学点击前文的链接即可查看，这里只介绍 Featurize 额外添加的功能。

## 快速操作按钮

工作区的右下角有一个快速操作按钮，提供以下功能：

* **添加数据集** 用于在工作区中下载事先上传好的数据集，你也可以下载其他人上传的公开数据集。关于数据集的详细用法请[戳这里]({% link docs/dataset.md %})。
* **退还实例** 在工作区中直接退还数据集。
* **切换环境** 切换工作区所使用的开发环境。关于环境的详细信息请[戳这里]({% link docs/environment.md %})。
* **帮助** 跳转至本文档页面。

## 底部状态栏

底部状态栏显示三个信息：

* **用户信息** 当前使用实例的用户名称。
* **用量信息** 对于按量使用的实例，这里会显示「使用时长」；对于包天/周/月的实例，这里将显示「剩余时间」。
* **后台任务** 一些和平台相关的任务会在这里显示进度。例如上传数据集的进度，下载数据集的进度等。注意这里不会显示你的后台进程。

## 应用

Featurize 为工作区添加了一些应用：

![](/asset/featurize-app.png)

### 本地 Web 应用

你可以在工作区的命令行中开启一些 Web 应用（例如 `Tensorboard` 和 `Microsoft NNI`）。然后通过这个按钮去访问这些 Web 应用的界面，直接输入对应的端口号即可。

如果你有其他的 Web 应用，并且使用该功能访问时出现白屏或样式丢失，请联系微信管理员。
{: .fe-info-block}

### SSH 连接

如果你希望通过本地的 SSH 客户端连接到你所占用的机器，可以使用此功能。平台禁止用户名密码登录方式，仅允许使用公钥登录的方式。

![](/asset/ssh.png)

由于 SSH 连接使用了跳板机，所以请确保你的 SSH 客户端开启了 `Agent Forwarding` 功能。
{: .fe-warning-block}

该 SSH 隧道支持 VS Code 等开发工具的**远程开发功能**。
{: .fe-success-block}

### VS Code

一个在线的 VS Code 开发环境。

![](/asset/online-vscode.png)
