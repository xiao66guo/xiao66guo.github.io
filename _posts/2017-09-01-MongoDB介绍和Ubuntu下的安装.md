---
layout: post
title: MongoDB介绍和Ubuntu下的安装
categories: MongoDB
description: MongoDB介绍和Ubuntu下的安装
keywords: MongoDB, Ubuntu
---
#### **MongoDB简介**

- MongoDB是一个基于分布式文件存储的NoSQL数据库。
- 由c++语言编写,运行稳定，性能高。
- 旨在为WEB应用提供可扩展的高性能数据存储解决方案

#### **专有名词**

| SQL术语/概念    | MongoDB术语/概念 | 解释/说明                   |
| ----------- | ------------ | ----------------------- |
| database    | database     | 数据库                     |
| table       | collection   | 数据库表/集合                 |
| row         | document     | 数据记录行/文档                |
| column      | field        | 数据字段/域                  |
| index       | index        | 索引                      |
| table joins |              | 表连接,MongoDB不支持          |
| primary key | primary key  | 主键,MongoDB自动将_id字段设置为主键 |

#### **MongoDB的特点**

- 模式自由 :可以把不同结构的文档存储在同一个数据库里
- 面向集合的存储：适合存储 JSON风格文件的形式
- 完整的索引支持：对任何属性可索引
- 复制和高可用性：支持服务器之间的数据复制，支持主-从模式及服务器之间的相互复制。复制的主要目的是提供冗余及自动故障转移
- 自动分片：支持云级别的伸缩性：自动分片功能支持水平的数据库集群，可动态添加额外的机器
- 丰富的查询：支持丰富的查询表达方式，查询指令使用JSON形式的标记，可轻易查询文档中的内嵌的对象及数组
- 快速就地更新：查询优化器会分析查询表达式，并生成一个高效的查询计划
- 高效的传统存储方式：支持二进制数据及大型对象（如照片或图片）

#### **MongoDB三元素**

- 三元素：**数据库、集合、文档**

- 集合就是关系型数据库中的表

- 文档对应着关系型数据库中的行

  - 文档，就是一个对象，有键值对构成，是json的扩展Bson形式

    ```mysql
    {name:'张三',age:18,gender:'男',address:'北京昌平'}
    ```

- 集合：类似于关系型数据库中的表，存储多个文档，结构不稳定。

- 数据库：是一个集合的物理容器,一个数据库中可以包含多个文档。

- 一个服务器通常有多个数据库

#### **Ubuntu下MongoDB的安装**

- 直接去MongoDB数据库官网(官网链接)下载Ubuntu对应的版本

  - **注意：**根据业界规则，偶数为稳定版，比如3.4.X，奇数为开发板3.5.X

- 下载好对应的MongoDB数据库压缩文件，对其进行解压：

  ```
  tar -zxvf mongodb-linux-x86_64-ubuntu1604-3.4.0.tgz
  ```

- 移动到/usr/local/目录下

  ```
  sudo mv -r mongodb-linux-x86_64-ubuntu1604-3.4.0/ /usr/local/mongodb
  ```

- 将可执行的文件添加到PATH路径中

  ```
  export PATH=/usr/local/mongodb/bin:$PATH
  ```

- 也可以直接在终端里安装：

  ```
  导入软件源的公钥
  sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv EA312927
  创建软件源
  echo "deb http://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list

  更新并安装软件
  sudo apt-get update
  sudo apt-get install -y mongodb-org
  sudo apt-get install  mongodb

  ```

#### **MongoDB服务端和客户端**

- 服务端的命令为mongod，可以通过help查看所有的参数

  ```
  mongod --help
  ```

- MongoDB默认的端口号为：27107

- **启动**

  ```
  sudo service mongod start
  ```

- **停止**

  ```
  sudo service mongod stop
  ```

- **重启**

  ```
  sudo service mongod restart
  ```

- **客户端的命令为mongo，默认的链接MongoDB服务端是不需要账号密码的**

- 也可以下载对应的可视化客户端 **robomongo**

  ​

  ​