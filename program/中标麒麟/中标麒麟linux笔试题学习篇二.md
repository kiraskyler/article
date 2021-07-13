# 中标麒麟linux笔试题学习篇二

V0.0.1.20210712

------

## 项目简介

> 朋友参加中标麒麟面试白嫖试卷，仅供研究，涉及侵权请联系作者删除
>
> 下面内容并非答案，仅仅是自我学习得到的结果，如果有错误麻烦请指正，交流使我们共同进步

## 提示

> 部分图片摘抄自外网，自行确保你的互联网访问

## 试卷图片

[![RhJqOK.jpg](https://z3.ax1x.com/2021/07/05/RhJqOK.jpg)](https://imgtu.com/i/RhJqOK)

## 图片1

### 12、A

[![Rha2a8.png](https://z3.ax1x.com/2021/07/05/Rha2a8.png)](https://imgtu.com/i/Rha2a8)

### 13、A

* ifconfig add 好像并没有这个命令

```
pi@raspberrypi:~ $ ifconfig add eth0 192.168.69.50
eth0: 未知的主机
ifconfig: `--help' gives usage information.
pi@raspberrypi:~ $ 
```

### 14、A B D

> 参考 [Linux iptables 防火墙详解](https://www.cnblogs.com/linguoguo/p/5581087.html)

### 15、A

### 二

> 三个女人R、S、T，两个男人U、V，四个小孩子W、X、Y、Z分三组，其中所有性别的不可以放在同一个组（小孩子是什么性别？？？），W不和R一组，X和S或者U或者都同时在一个组（一家的吧）。

#### 1、E

> R是他们组里唯一的成年人，谁和R一组？？？

> W不和R在一个组，排除A、B
>
> 出现X必须有S或者U，排除C、D

## 图片2

[![WP9Gh8.jpg](https://z3.ax1x.com/2021/07/12/WP9Gh8.jpg)](https://imgtu.com/i/WP9Gh8)

#### 2、A、D

> R和U是一个三人组里的其中两个，另外两组是谁？

> B、X没有和S or U在一起
>
> C、两个男人在同一个组了
>
> E、X没有和S or U在一起

#### 3、A、B、C

> 谁可以和W在一起作为一个组合

> D、两个大男人在一起了（*——*）
>
> E、一个组里不可以三个小孩子在一起



### 三、

#### 1、

​	开放题目，很难有标准答案，把linux的架构图丢上去吧，内核外套个shell，内核包括硬件抽象层、任务、内存、等

![linux架构](https://upload.wikimedia.org/wikipedia/commons/thumb/7/7b/Free_and_open-source-software_display_servers_and_UI_toolkits.svg/1920px-Free_and_open-source-software_display_servers_and_UI_toolkits.svg.png)

2、

摘抄自维基百科

![网络拓扑](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c4/IP_stack_connections.svg/865px-IP_stack_connections.svg.png)

![](https://upload.wikimedia.org/wikipedia/commons/3/3b/UDP_encapsulation.svg)

> **TCP/IP参考模型**是一个抽象的分层模型，这个模型中，所有的[TCP/IP](https://zh.m.wikipedia.org/wiki/TCP/IP)系列[网络协议](https://zh.m.wikipedia.org/wiki/网络协议)都归类到4个抽象的“层”中。每一抽象层创建在低一层提供的服务上，并且为高一层提供服务。 完成一些特定的任务需要众多的协议协同工作，这些协议分布在参考模型的不同层中的，因此有时称它们为一个*协议栈*。 TCP/IP参考模型为[TCP/IP](https://zh.m.wikipedia.org/wiki/TCP/IP)协议栈订身制作。其中IP协议只关心如何使得数据能够跨越本地网络边界的问题，而不关心如何利用传输媒体，数据如何传输。整个[TCP/IP](https://zh.m.wikipedia.org/wiki/TCP/IP)协议栈则负责解决数据如何通过许许多多个点对点通路（一个点对点通路，也称为一“跳”, 1 hop）顺利传输，由此不同的网络成员能够在许多“跳”的基础上创建相互的数据通路。 如想分析更普遍的网络通信问题，ISO的[OSI模型](https://zh.m.wikipedia.org/wiki/OSI模型)也能起更好的帮助作用。 **因特网协议族**是一组实现支持[因特网](https://zh.m.wikipedia.org/wiki/因特网)和大多数商业网络运行的[协议栈](https://zh.m.wikipedia.org/wiki/协议栈)的[网络传输协议](https://zh.m.wikipedia.org/wiki/网络传输协议)。它有时也称为**TCP/IP协议组**，这个名称来源于其中两个最重要的协议：[传输控制协议](https://zh.m.wikipedia.org/wiki/传输控制协议)（[TCP](https://zh.m.wikipedia.org/wiki/传输控制协议)）和[因特网协议](https://zh.m.wikipedia.org/wiki/网际协议)（[IP](https://zh.m.wikipedia.org/wiki/网际协议)），它们也是最先定义的两个协议。 同许多其他协议一样[网络传输协议](https://zh.m.wikipedia.org/wiki/网络传输协议)也可以看作一个多层组合，每层解决数据传输中的一组问题并且向使用这些低层服务的高层提供定义好的服务。高层逻辑上与用户更为接近，所处理[数据](https://zh.m.wikipedia.org/wiki/数据)更为抽象，它们依赖于低层将数据转换成最终能够进行实体控制的形式。 [网络传输协议](https://zh.m.wikipedia.org/wiki/网络传输协议)能够大致匹配到一些厂商喜欢使用的固定7层的[OSI模型](https://zh.m.wikipedia.org/wiki/OSI模型)。然而这些层并非都能够很好地与基于IP的网络对应（根据应用的设计和支持网络的不同它们确实是涉及到不同的层）并且一些人认为试图将[因特网协议组](https://zh.m.wikipedia.org/w/index.php?title=因特网协议组&action=edit&redlink=1)对应到OSI会带来混淆而不是有所帮助。

## 使用说明

## 维护说明

## 注意

## 关于作者

>Autho: KiraSkyler
>Email: kiraskyler@outlook.com / kiraskyler@qq.com

## 贡献者/贡献组织

## 鸣谢

## 版权信息

> 该项目签署了GPL 授权许可，详情请参阅官网

>This program is free software: you can redistribute it and/or modify
>it under the terms of the GNU General Public License as published by
>the Free Software Foundation, either version 3 of the License, or
>(at your option) any later version.
>This program is distributed in the hope that it will be useful,
>but WITHOUT ANY WARRANTY; without even the implied warranty of
>MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
>GNU General Public License for more details.
>You should have received a copy of the GNU General Public License
>along with this program.  If not, see <https://www.gnu.org/licenses/>.

## 更新日志

* V0.0.0.20210101