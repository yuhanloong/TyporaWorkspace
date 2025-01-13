# 1.mac安装

官网下载后解压改名为 zookeeper，然后更改位置为：/usr/local/zookeeper

然后在该位置下创建 data 文件：/usr/local/zookeeper/data

进入 /usr/local/zookeeper/conf，复制 zoo_sample.cfg 为 zoo.cfg，并修改其内容：

```bash
# 配置 Zookeeper 数据存储目录
dataDir=/usr/local/zookeeper/data
```

启动

```bash
# 启动服务端
/usr/local/zookeeper/bin/zkServer.sh start
# 关闭服务端
/usr/local/zookeeper/bin/zkServer.sh stop
# 重启服务端
/usr/local/zookeeper/bin/zkServer.sh restart
# 查看服务端状态
/usr/local/zookeeper/bin/zkServer.sh status

# 客户端连接服务端
/usr/local/zookeeper/bin/zkCli.sh
/usr/local/zookeeper/bin/zkCli.sh -server 127.0.0.1:2181
```

# 2.简介

- Zookeeper 是 Apache Hadoop 项目下的一个子项目，是一个树形目录服务。
- Zookeeper 翻译过来就是动物园管理员，他是用来管理 Hadoop(大象)、Hive(蜜蜂)、Pig(小猪)的管理员。简称 zk
- Zookeeper 是一个分布式的、开源的分布式应用程序的协调服务。
- Zookeeper 提供的主要功能包括：
  - 配置管理
  - 分布式锁
  - 集群管理

# 3.命令操作

## 数据模型

- ZooKeeper 是一个树形目录服务，其数据模型和 Unix 的文件系统目录树很类似，拥有一个层次化结构。
- 这里面的每一个节点都被称为：ZNode，每个节点上都会保存自己的数据和节点信息。
- 节点可以拥有子节点，同时也允许少量（1MB）数据存储在该节点之下。
- 节点可以分为四大类：
  - PERSISTENT 持久化节点
  - EPHEMERAL 临时节点：-e
  - PERSISTENT_SEQUENTIAL 持久化顺序节点：-s
  - EPHEMERAL_SEQUENTIAL 临时顺序节点：-es

![](./images/zookeeper数据模型.jpg)

## 服务端常用命令

```bash
# 启动服务端
/usr/local/zookeeper/bin/zkServer.sh start
# 关闭服务端
/usr/local/zookeeper/bin/zkServer.sh stop
# 重启服务端
/usr/local/zookeeper/bin/zkServer.sh restart
# 查看服务端状态
/usr/local/zookeeper/bin/zkServer.sh status
# 查看 zookeeper 版本
/usr/local/zookeeper/bin/zkServer.sh version
```

## 客户端常用命令

```bash
# 客户端连接服务端
/usr/local/zookeeper/bin/zkCli.sh
/usr/local/zookeeper/bin/zkCli.sh -server 127.0.0.1:2181

# 查看所有命令
help

# 查看根节点下的所有节点
ls /
# 查看根节点下的 name 节点下的所有节点
ls /name
# 查看根节点详细信息
ls -s /

# 创建 name 持久化节点，值为 zhangsan，节点名不能重复
create /name zhangsan
# 创建 age 持久化节点，值为 null，节点名不能重复
create /age
# 创建 age 临时节点，客户端断开连接会删除，节点名不能重复
create -e /age
# 创建 age 持久化顺序节点，创建出来的节点名称后面会带自增编号，所以节点名可以重复
create -s /age
# 创建 age 临时顺序节点，客户端断开连接会删除，创建出来的节点名称后面会带自增编号，所以节点名可以重复
create -es /age

# 获取 name 节点的值
get /name

# 修改 age 节点的值为 18
set /age 18

# 删除 user 节点（节点下有子节点无法删除）
delete /user
# 删除 user 节点，包括其下面所有子节点
deleteall /user
```

# 4.JavaAPI操作

## CuratorAPI常用操作



## 分布式锁

# 5.集群搭建

# 6.核心理论
