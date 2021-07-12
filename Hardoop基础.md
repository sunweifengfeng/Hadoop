## Day1 开篇
**1.学习知识点**
Yarn Hadoop源码解析 入门 HDFS MapReduce 生产调优手册

从搭建集群开始

基础:java maven idea linux 常用命令

---

## Day2 大数据的概念
**1.大数据概念**
无法在一定时间范围内用常规软件进行捕捉、管理和处理的数据集合，需要用新处理模式才能有更强的决策力。
例如电脑磁盘只有1T，我有5T的数据需要存储，因此要用大数据。

按顺序给出不数据存储单位：bit Byte KB MB GB TB PB EB ZB YB BB NB DB 

**2. 大数据解决**
海量数据的采集、存储和分析计算问题

---

## Day3 大数据的特点
1. 大量 Volume 1PB = 1024TB：企业级数据已经将近EB 需要海量的数据集群进行存储：
**用海量数据的存储解决**
2. 高速 Velocity 
**用大数据快速计算解决**
3. 多样 海量数据的采集问题 
结构化数据：mysql
非结构化数据：网页
**用海量数据的采集解决**
4. 低价值密度 Value 价值密度高度与数据总量的大小成反比
快速对有价值的数据提纯

**对大数据采集后的清洗**

---

## Day4 大数据的应用场景
1. 抖音推荐
2. 电商广告推荐
3. 零售 分析用户消费习惯 为用户购买商品提供方便
4. 物流仓储：京东物流次日到达 哪个地点的物流存什么物品
5. 保险 
6. 金融：帮助金融机构推荐优质客户 
7. 房产
8. 人工智能+5G+互联网+虚拟与现实

---

## Day5 大数据发展场景
互联网 大数据 人工智能与实体经济融合

---

## Day6 大数据未来的工作内容
产品人员提需求-->数据部门搭建数据平台、分析数据指标--->数据可视化

大数据部门：
平台组（平台的搭建、集群性能监控、集群性能调优）
数据仓库组（数据清洗、ETL数据清洗、数据分析数据仓库建模）
实时组（实时分析性能调优）
数据挖掘组（算法组、推荐系统工程师、用户画像工程师）
报表开发组（JavaEE、前端工程师）

---

## Day7 Hadoop入门
1. 概念：Hadoop是什么 发展历史 三大发行版本 优势 组成 大数据技术生态体系 推荐系统案例
2. 环境准备： 模板虚拟机准备 克隆 安装JDK、Hadoop
3. Hadoop生产集群搭建 ：本地模式（测试） **完全分布式集群（开发面试的重点）**
4. 常见错误解决方案

---

## Day8 Hadoop是什么
1. Apache基金会开发的分布式系统基础架构
分布式：一个资料用多台服务器来处理或存储

**2. 主要解决海量数据的存储和海量数据的分析计算**

3. Hadoop生态圈

## Day9 Hadoop发展历史
三个框架
HDFS 
MR
HBase

---

## Day10 Hadoop三大发行版本
Apache 
Cloudera 
Hortonworks

---

## Day11 Hadoop优势
高可靠性
高扩展性（动态增加、删除服务器）
高效性（Hadoop并行工作）
高容错性：可自动将失败的任务重新分配

---

## Day12 Hadoop的组成
资源调度：分配那个服务器、内存
![](./img/Hadoop组成.png)

---

## Day13 HDFS概述 Hadoop分布式文件系统
NameNode：数据存储在什么位置 目录
DataNode（服务器）：具体存储的数据 根据NameNode去寻找
2NN：NameNode的备份 防止目录丢失错误

---

## Day14 YARN架构概述
资源管理器：ResourceManager：
![](./img/Yarn架构.png)

其中Container容器就是将大的服务器NodeManager虚构出来，当做一个服务器。不需要的时候就将其释放到NodeManger。如阿里云。

ApplicationMaster的任务可以跨节点，跨NodeManger服务器。

Container容器默认1-8G。

---

## Day15 MapReduce架构概述
1. MapReduce将计算过程分为两个阶段：MaP和Reduce
>Map结算并行处理输入数据。
Reduce阶段对Map结果进行汇总

2. 任务分给每个Hadoop（Map）->每个Hadoop计算结果->返回结果（reduce）

---

## Day16 HDFS、Yarn、MapReduce三者之间的关系
![](./img/HDFS_YARN_MAPreduce.png)

---

## Day17 大数据技术生态体系
结构化数据：数据库 二维表格  -->用sqoop数据传递
半结构化数据：文件日志 可以导入到数据库 -->用Flume日志收集
非结构化数据：视频 ppt -->用Kafka消息队列处理（同时kafka也可以处理上述两种）

任务调度：集群中100多个任务，不一定同时跑，一部分执行完，下一批执行
任务调度的方法：Oozie任务调度 Azkaban任务调度

![大数据技术生态体系](./img/大数据技术生态体系.png)

大数据闭环：首先根据浏览网页的，然后收集日志，存入文件日志，通过Flume日志收集，然后给Kalfka消息队列，通过Spark Streaming或Flink实时计算，下一次推荐给他什么东西。然后存入数据库，通过JavaEE后台进行后端操作，左后显示在前端推荐页面上。

![推荐项目系统架构](./img/推荐项目系统架构.png)

---

## Day18 模板虚拟机准备
模板虚拟机的作用是为了生成多台服务器
配置内存4g\硬盘50g\IP\主机名称

软件、硬件、主机名称

## Day20 Hadoop Ip和主机名称的配置
Hadoop100
VMWare
Windows
上述三种配置ip地址

**VMWare Ip地址配置：**
![](./img/VMwareIp配置.png)

**进行Windows IP地址配置**
![](./img/WindowsIp地址配置.png)

其中网关最后一位都为2

***Hadoop的Ip配置**
1. 进入到centos中：打开终端
`su root` 进入root账户 输入密码
2. 输入 `vim /etc/sysconfig/network-scripts/ifcfg-ens33`
3. 进入上述文件中
将：
```properties
TYPE=Ethernet
PROXY_METHOD=none
BROWSER_ONLY=no
BOOTPROTO=dhcp
DEFROUTE=yes
IPV4_FAILURE_FATAL=no
IPV6INIT=yes
IPV6_AUTOCONF=yes
IPV6_DEFROUTE=yes
IPV6_FAILURE_FATAL=no
IPV6_ADDR_GEN_MODE=stable-privacy
NAME=ens33
UUID=aedc6059-1892-4a2d-810e-45130f77a6db
DEVICE=ens33
ONBOOT=yes
```
其中的动态地址改为静态地址，并在下方加入IP地址、网关和域名解析器
```properties
#IP地址
IPADDR=192.168.10.100
#网关
GATEWAY=192.168.10.2
#域名
DNS1=192.168.10.2
```
4. 修改主机名称
运行：`vim /etc/hostname`
添加Hodoop100
5. 主机名称映射
将主机名称 映射为Hadoop100，防止ip地址更改后，重复更改ip地址。
运行 `vim /etc/hosts`  添加
```
192.168.10.100 hadoop100
192.168.10.101 hadoop101
192.168.10.102 hadoop102
192.168.10.103 hadoop103
192.168.10.104 hadoop104
192.168.10.105 hadoop105
192.168.10.106 hadoop106
192.168.10.107 hadoop107
192.168.10.108 hadoop108
```

6. reboot重启


---

## Day21 XShell 远程访问工具
![](./img/Xshell操作.png)
### 1.远程操作服务器的工具，因为我们和Hadoop在远端

安装失败的解决办法：[xsehll更新问题](https://blog.csdn.net/lookingatsky/article/details/103760372)  

### 2 安装成功后：
步骤1：
![](./img/新建xshell1.png)
步骤2：
![](./img/新建xshell2.png)

打开C:\Windows\System32\drivers\etc\hosts进行主机映射，添加下面内容：
```
192.168.10.100 hadoop100
192.168.10.101 hadoop101
192.168.10.102 hadoop102
192.168.10.103 hadoop103
192.168.10.104 hadoop104
192.168.10.105 hadoop105
192.168.10.106 hadoop106
192.168.10.107 hadoop107
192.168.10.108 hadoop108
```
就配置好了

再次创建的时候不用输入ip地址，只需要输入hadoop100/hadoop101就可以了。


### 3. 远程通过xshell将文件传输到vmware的hadoop服务器。
需要安装xftp

xftp操作使用：
![](./img/xftp操作.png)
点击1然后可以将windows的内容拖拽到 hadoop中

## Day22模板虚拟机准备完成
系统操作开始先在root用户下操作 搭建集群时再去swf用户下去操作

1. 到su root 用户中
2. cd 到根目录
3. ping www.baidu.com 测试链接
4. 安装补丁包 yum install -y epel-release
5. 防火墙一般在外网建立  不用每个hadoop都有一个防火墙 因此关闭防火墙
   关闭防火墙开机自启动
>systemctl stop firewalld
systemctl disable firewalld.service

6. 配置 atguigu 用户具有 root 权限， 方便后期加 sudo 执行 root 权限的命令
>[root@hadoop100 ~]# vim /etc/sudoers

修改/etc/sudoers 文件，在%wheel 这行下面添加一行，如下所示：
```xml
## Allow root to run any commands anywhere
root ALL=(ALL) ALL
## Allows people in group wheel to run all commands
%wheel ALL=(ALL) ALL
swf ALL=(ALL) NOPASSWD:ALL ##使得swf可以不输入密码就对root用户权限进行操作
```

>**注意**： atguigu 这一行不要直接放到 root 行下面，因为所有用户都属于 wheel 组，你先
配置了 atguigu 具有免密功能，但是程序执行到%wheel 行时， 该功能又被覆盖回需要
密码。所以 atguigu 要放到%wheel 这行下面。
保存并退出

6.0. `cd /opt/`切换到此目录
6.1 `exit` 退出到swf账户
6.2. `ll`列出此目录的文件
6.3. `cd /opt/`切换到swf的当前目录
6.4. `ll`列出文件
6.5 `sudo rm -rf rh/` swf账户下删除root用户权限的文件夹
6.6 `sudo mkdir module`
6.7 `sudo mkdir software`上述两个创建的文件夹权限都是root
6.8 `sudo chown swf:swf module/ software/`将当前文件夹权限由root给swf

7. 切换到root账号
卸载虚拟机自带的 JDK
注意：如果你的虚拟机是最小化安装不需要执行这一步。
[root@hadoop100 ~]# rpm -qa | grep -i java | xargs -n1 rpm -e
--nodeps
>rpm -qa： 查询所安装的所有 rpm 软件包
grep -i：忽略大小写
xargs -n1：表示每次只传递一个参数
rpm -e –nodeps：强制卸载软件
8. reboot

---

## Day23 克隆虚拟机
### 1.克隆三台虚拟机 修改IP地址 主机名称
Hadoop102 Hadoop103 Hadoop104
删除克隆的虚拟机 就右键 管理 从磁盘中删除
### 2. 修改ip地址 主机名称
`vim /etc/sysconfig/network-scripts/ifcfg-ens33`
`vim /etc/hostname`

修改102 103 104 
然后reboot
然后ping测试
`hostname`查看是否改了

### 3. 修改xshell
新建hadoop102 hadoop103 hadoop104
连接的时候 要打开虚拟机

---

## Day24 JDK安装

