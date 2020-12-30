---
layout: page
title: 远程开发
permalink: /远程开发
nav_order: 10
---

# 远程开发

由于 Featurize 支持 SSH 连接（具体方法参考[工作区]({% link docs/workspace.md %})），所以你可以使用各类 IDE 的远程开发、调试功能。

## 预设置

因为 Featurize 的 SSH 功能使用了跳板机，所以你需要对 `10.0.0.0/16` 地址段添加跳转设置，请在你本机的 `~/.ssh/config` 文件中添加下面的配置（如果没有该文件请自行创建）：

```
Host 10.0.*
  ProxyJump featurize@featurize.cn
  User featurize
  Port 2222
```

Windows 用户设置请参考 https://zhuanlan.zhihu.com/p/103578899
{:.fe-success-block}

如果你本机的网络环境已经在用 `10.0.0.0/16` 的地址段，这项配置添加后会导致你不能 ssh 到局域网中的其他机器。
{:.fe-warning-block}

然后，测试连接是否正常：

```bash
ssh featurize@10.0.xx.xx -p 2222  # 请将 xx.xx 更换为你使用机器的 ip 段
```

如果连接正常，你就可以参考各个 IDE 的远程开发文档进行 IDE 的配置了，IDE 的配置中：

User 填写：featurize

Server 填写：10.0.xx.xx，同样 xx.xx 替换成你申请机器的 ip 段

Port 填写：2222

-----------

## IDE 配置参考

[PyCharm 传送门](https://www.jetbrains.com/help/pycharm/configuring-remote-interpreters-via-ssh.html)

[Visual Studio Code 传送门](https://code.visualstudio.com/docs/remote/ssh-tutorial)

## 视频教程

[VS Code 远程开发 - Windows 篇](https://www.bilibili.com/video/BV1np4y1B7S7)

[VS Code 远程开发 - Mac 篇](https://www.bilibili.com/video/BV19X4y1u7vv)
