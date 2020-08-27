---
layout: page
title: 常见问题汇总
permalink: /常见问题汇总
---

# 常见问题汇总

用户提出的常见问题会被整理到这里。

------

### Q：关闭浏览器，我的训练会被停掉吗？

A： 不会。

这里分两种情况：

1. 如果你用 `Jupyter Notebook` 在进行训练，那么当你刷新页面后，**Notebook 的状态**会丢失，但这不代表训练停止了。事实上，训练还在后台继续运行。

2. 如果你在命令行中用 `python xxx` 的方式进行训练，当你刷新页面或关闭 Terminal 的 Tab 后，训练依然是不会被停止的，甚至你可以通过左侧的 `session` 来恢复之前的状态。

![](/asset/session-terminal-recovery.png)

<div>
<div><strong>更好的实践</strong></div><div>不建议在 Notebook 中直接使用 print 或者 tqdm 等方式来监控你的训练进度。你应该用 logging 模块来将训练日志记录到文件中，这样无论你怎么刷新页面都不会影响，只需要看文件日志即可。</div>
</div>
{:.fe-success-block}

### Q：程序报错 CUDA out of memory？

A： 可能有以下两个原因：

1. 你程序要求的显存大于机器提供的显存，尝试减小 batch size 或减小输入再次尝试。
2. 你没有关闭之前训练的进程，请确保没有其他进程占用显存。

![](/asset/shutdown.png)

### Q：怎么用 Tensorflow 1？

A： 参考 [开发环境]({% link docs/environment.md %})
