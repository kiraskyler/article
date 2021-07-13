# 中标麒麟linux笔试题学习篇一

V0.0.1.20210705

------

## 项目简介

> 朋友参加中标麒麟面试白嫖试卷，仅供研究，涉及侵权请联系作者删除
>
> 下面内容并非答案，仅仅是自我学习得到的结果，如果有错误麻烦请指正，交流使我们共同进步

## 试卷图片

[![RhMK4P.jpg](https://z3.ax1x.com/2021/07/05/RhMK4P.jpg)](https://imgtu.com/i/RhMK4P)

[![RhM3jg.jpg](https://z3.ax1x.com/2021/07/05/RhM3jg.jpg)](https://imgtu.com/i/RhM3jg)

## 图片1

### 1、D

### 2、C

```
[kira@kira-virtual-machine ~]$ uname -a
Linux kira-virtual-machine 4.15.0-112-generic #113-Ubuntu SMP Thu Jul 9 23:41:39 UTC 2020 x86_64 x86_64 x86_64 GNU/Linux
```

### 3、A

> 当前网段ip段全是1的是广播，即(ip & mask) || (mask ^= 0xFFFFFFFF)

### 4、BC

> 集群文件系统词典
>
>
> GFS：全局文件系统
>
>
> GFS是应用最广泛的集群文件系统。它是由红帽公司开发出来的，允许所有集群节点并行访问。元数据通常会保存在共享存储设备或复制存储设备的一个分区里。
>
>
> OCFS:甲骨文集群文件系统
>
>
> 从概念上来说，OCFS与GFS非常相似，现在OCFS 2已经被应用于Linux系统之中。
>
>
> VMFS:VMware的虚拟计算机文件系统
>
>
> VMFS是ESX服务器用来允许多个服务器访问同一个共享存储设备的集群文件系统。这样就可以实现虚拟机在不同服务器之间的无缝迁移，因为源服务器和目标服务器都可以访问同一个存储设备。日志是分布式的，ESX服务器之间也不会出现单节点故障。
>
>
> Lustre：Sun的集群分布式文件系统。
>
>
> Lustre是专门用于包含数千个节点的大型集群的分布式文件系统。Lustre已经支持Linux系统，但是高速计算环境之外的应用程序是有限的。
>
>
> Hadoop:一个象谷歌那样使用的分布式文件系统。
>
>
> 这不是一个集群文件系统，但是却是一个分布式文件系统。我们将Hadoop收录进来是因为它的应用越来越广泛，而且利用Hadoop的存储架构设计决策的组合很多。但是默认配置下，你会在3个不同的节点上拥有3个数据副本。一旦数据发生变化，每个数据副本都会更新，因此，从某种意义上来说，它也可以被看做是集群文件系统。然而，Hadoop存在一个故障点隐患，即跟踪记录所有文件系统级数据的命名节点。
>
>
> 做出最好选择
>
> 有太多选择并不是坏事。你可以根据执行目标选择使用合适的集群文件系统以及存储架构。 只要有计划地使用，所有这些文件系统都可以发挥出应有的作用。
> ————————————————
> 原文链接：https://blog.csdn.net/enweitech/article/details/16799935

### 5、AB

> /dev/hda2 扩展分区，用来容纳逻辑分区。主分区编号并不一定是从1开始
> /dev/hda5 第一个逻辑分区
> /dev/hda6 第二个逻辑分区
> /dev/hda7 第三个逻辑分区
>
> 原文链接： https://blog.csdn.net/kehanxin/article/details/50424804

> ​	不确定hda+num分区类型是否强制，如果不是强制，网络上的大部分资料也是这么描述。那么以上的说法是建立在mbr分区表的情况下的，mbr分区表由历史遗留问题，分区表容量有限，最大只能有4个主分区，才会有以上的划分，但如果是gpt分区，主分区的数量就会很可观，hda6就可能是主分区了。

## 图片2

### 6、CE

> E的翻译就是C

> MBR 参考：https://blog.csdn.net/weixin_35223524/article/details/116783569

![](https://img-blog.csdnimg.cn/img_convert/ebc678dc6383bf0d276edd527db8d397.png)

> GPT参考： https://zh.wikipedia.org/wiki/GUID%E7%A3%81%E7%A2%9F%E5%88%86%E5%89%B2%E8%A1%A8
>
> 链接是个表格，不方便粘贴源格式

```
分区表头的格式
起始字节	长度	内容
0	8字节	签名（"EFI PART", 45 46 49 20 50 41 52 54）
8	4字节	修订（在1.0版中，值是00 00 01 00）
12	4字节	分区表头的大小（单位是字节，通常是92字节，即5C 00 00 00）
16	4字节	分区表头（第0－91字节）的CRC32校验，在计算时，把这个字段作为0处理，需要计算出分区序列的CRC32校验后再计算本字段
20	4字节	保留，必须是0
24	8字节	当前LBA（这个分区表头的位置）
32	8字节	备份LBA（另一个分区表头的位置）
40	8字节	第一个可用于分区的LBA（主分区表的最后一个LBA + 1）
48	8字节	最后一个可用于分区的LBA（备份分区表的第一个LBA − 1）
56	16字节	硬盘GUID（在类UNIX系统中也叫UUID）
72	8字节	分区表项的起始LBA（在主分区表中是2）
80	4字节	分区表项的数量
84	4字节	一个分区表项的大小（通常是128）
88	4字节	分区序列的CRC32校验
92	*	保留，剩余的字节必须是0（对于512字节LBA的硬盘即是420个字节）
```

### 7、A

> 参考：https://wenku.baidu.com/view/409c178b52ea551811a6870d.html

### 8、B

> [kira@kira-virtual-machine ~]$ echo  $PATH
> /home/kira/bin:/home/kira/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
> [kira@kira-virtual-machine ~]$ 

### 9、C

> 参考：https://www.runoob.com/linux/linux-comm-insmod.html

> lsmod是显示
>
> rmmod是删除
>
> insmod 载入模块
>
> depmod will output a dependency list suitable for the modprobe utility.
>
> modprobe 自动加载

### 10、（1）B 、（2）D

[![RhMa40.png](https://z3.ax1x.com/2021/07/05/RhMa40.png)](https://imgtu.com/i/RhMa40)

### 11、D

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