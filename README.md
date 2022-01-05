# 长三角数据中心后台

[toc]

## 摘要

这项工作的主要目的是注册登录一些用户，用户能上传数据并进行管理，上传的数据可以和数据中心的数据之间能做出一些数据分析。

- 可能是海量异构数据
- 可能是计算密集型（但是可能性不大）
- 如何评判数据的价值

## 设计

海量异构数据：采用分布式文件系统和对象存储方式，初步考虑 [minIO](http://www.minio.org.cn/overview.shtml) 的框架

计算密集型：没有想法，不知道 minIO 和 Flink 的耦合度咋样，大数据计算没有任何基础,,,



目前工作：现在只考虑数据存放在单个服务器上的情况，数据利用系统自带的文件系统管理，数据元数据及用户信息存储在 Mongo 数据库中，数据库设计如下：

![数据管理](http://111.229.14.128:9001/wutian/1641384988_5pWw5o2u566h55CG.png)

<div align='center'>数据管理设计</div>
