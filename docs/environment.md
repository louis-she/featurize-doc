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

由于我们使用了 Conda 的虚拟环境，请不要在 Notebook 中通过 `!` 来使用 `pip` 或 `python`，因为这里所使用的 Python 并不是虚拟环境中的 Python，正确的做法是打开一个终端去执行 `python` 或 `pip`。
{: .fe-warning-block}

## 目录及作用

|   目录名        |  路径         |  IO 性能  | 说明  |
|:-------------:  | :------------------: | :------------------: | :------------------ |
|    家目录        |  /home/featurize  |  快  | 家目录中的数据在用户手动退还或重置实例后销毁（实例出现故障重启不会导致家目录中的数据丢失） |
|    同步盘目录   |  /cloud  | 慢 | 软连至 /home/featurize/work，云同步盘中的数据会一直跟随用户，不会随实例退还或重启被销毁。由于使用了软连接，所以不要在 /home/featurize/work 中以相对路径的方式访问外部数据 |
|    JupyterLab 启动目录   |  /home/featurize  | 快 |  工作区中左侧目录树的根目录，跟家目录相同 |
|    数据集下载目录   |  /home/featurize/data  | 快 | 添加的数据集会下载到这个目录中 |
|    非家目录/同步盘目录   |  N/A  | 快 | 实例一旦发送重启会重置这部分目录得数据，所以尽量不要把代码或数据保存在这部分区域  |

## Python 环境

服务器使用 conda 来管理环境，我们预装了两个环境：

|   环境名称        |  TensorFlow 版本         |  PyTorch 版本  |
|:-------------:  | :------------------: | :------------------: |
|  base（默认）     |  2.4.1  | 1.7.1 |
|  tf1.15     |  1.15  | 无 |

你如果需要其他的软件版本，可以使用 conda 来创建新的虚拟环境。

## CUDA 环境

**非 3080/90 机器**

Conda 的 base 环境预装了 cudatoolkit 10.1，由于是在虚拟环境（base）中安装的，所以 CUDA 的位置位于 Conda 的虚拟环境的目录中，具体的：

CUDA 库文件地址: `/environment/python/versions/miniconda3-4.7.12/lib`

CUDA 头文件地址：`/environment/python/versions/miniconda3-4.7.12/include`

nvcc 地址：`/environment/python/versions/miniconda3-4.7.12/bin`

如果你需要手动编译一些使用 CUDA 的 C++ 项目，需要正确设置**相应的环境变量**或修改**编译参数**。

当然你可以自己通过 `sudo apt-get install cuda-toolkit-x-x` 来安装所需要的 CUDA 版本。

**3080/90 机器**

由于 Conda 的软件包更新速度较慢，这部分机器平台使用官方的 apt 源安装了 CUDA，所以 CUDA 位于默认目录 `/usr/local/cuda` 中。

## 自建环境的持久化

充分利用`同步盘目录`，我们可以将**安装的包**或是**虚拟环境**保存至同步盘中。下面提供两种方法：

1. 安装包使用 `pip install --user xxx`，通过添加 `--user` 参数，可以使所安装的 Python 包放置在同步盘中，从而退还机器使用其他机器也不会丢失环境。需要注意的是，如果你创建了多个虚拟环境，则不太推荐使用这种方式来安装包，因为多个环境之间会共享 `--user` 所安装的包，违背了虚拟环境隔离性的原则。

2. 创建虚拟环境，`conda create --prefix /cloud/myenv python=3.9`，通过 `--prefix` 将虚拟环境安装至同步盘目录，这样你在该环境所安装的所有包都会被同步。但这种做法会占用比较大的同步盘空间，为了避免同步盘超过 20G 而产生费用，最好在退还机器之前使用 `du -sh /cloud` 命令来检查一次同步盘的使用量。
