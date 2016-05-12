---
title: 使用ShadowSocks协助Eclipse下载插件及依赖包
date: 2016-05-06 09:00:00
post_link: shadowsocks_eclipse_proxy
author: zsh
date_format_archive: MM-DD
tags:
- 工作
---

因为长城防火墙的原因，Eclipse的MarketPlace时好时不灵光，如果构建的是maven工程，那么极有可能部分的dependencies是下不了的。
程序员不能因此而束手无策，有很多种方法能够绕开防火墙，今天就跟大家介绍使用免费的ShadowSocks代理来突破这一限制。

![shadowsocks](/images/2016-05-06_09_00_00/shadowsocks.jpg)
<!-- more -->
<hr>
首先，你得保证你有一个ShadowSocks账号，并且本地开启了ShadowSocks客户端，像这样

![shadowsocks 本地客户端窗口](/images/2016-05-06_09_00_00/shadowsocks-config.jpg)

之后，启动Eclipse，选择 Window -> Preferences，在弹出的全局配置窗口中搜索 proxy

![Eclipse 网络代理设置](/images/2016-05-06_09_00_00/eclipse-preferences_1.jpg)

配置HTTP代理地址及端口，默认配置下，ShadowSocks客户端运行在localhost:1080端口，因此将HTTP，HTTPS，SOCKS的代理地址都设置成localhost并且设置端口为1080，然后点击应用。

![Eclipse 网络代理设置](/images/2016-05-06_09_00_00/eclipse-preferences_2.jpg)

接下来，打开Eclipse MarketPlace，或者加入一段maven依赖，检验下是否成功吧 :-) 这样的配置可以同样适用在其他的IDE(如：JetBrain系列的IDE)或者命令行。