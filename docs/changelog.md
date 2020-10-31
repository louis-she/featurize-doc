---
layout: page
title: 更新日志
permalink: /更新日志
nav_order: 20
---

# 更新日志

Featurize 平台功能、工作区环境的更新日志都在这里。

## 2020-10-31

更新工作区的默认环境，主要是为了升级 PyTorch 官方发布的 1.7 版本，PyTorch 1.7 支持 3080/3090，所以本次更新后 30 系列的 PyTorch 1.7 将从 Nightly Build 版切换为官方 release 的版本。

本次更新后你可以放心地在 3080/90 机器上使用 PyTorch。不过 TensorFlow 在 3080/90 机器上依然使用了 Nightly Build 版本，不推荐使用。另外，我们修复了 VS Code 远程开发的一些已知问题，现在你可以用 VS Code 连接到平台机器上进行接近本地化体验的 Python 开发。 本次更新还去掉了一些不常用的预装软件，如果你需要使用，可自行安装。

更新详情：

* 去掉了在线的 VS Code 编辑器，推荐使用 VS Code 的远程开发插件
* 修复 VS Code 远程开发无法安装 Python 扩展的问题
* 去掉了预装的 Bazel、Caffe、fastai

针对**非 30 series 主机**的工作区默认环境

* PyTorch 由 1.6 升级至 1.7
* TensorFlow 由 2.2.0 升级为 2.3.1

针对**30 series 主机**的工作区默认环境：

* PyTorch 1.7 Nightly Build 切换为官方的发布的 1.7 版本
* TensorFlow 从 2.4 Nightly Build 升级为 2.5 Nightly Build
