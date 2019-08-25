
* [关系数据库的缺点](#关系数据库的缺点)
* [4种NoSQL方案](#4种NoSQL方案)
  * [K-V存储---解决关系数据库无法存储数据结构的问题，以Redis 为代表](#K-V存储解决关系数据库无法存储数据结构的问题)
  * [文档数据库---解决关系数据库强schema 约束的问题，以MongoDB 为代表](#文档数据库解决关系数据库强schema约束的问题)
  * [列式数据库： 解决关系数据库大数据场景下的I/O 问题，以HBase 为代表](#列式数据库解决关系数据库大数据场景下的输入输出问题)
  * [全文搜索引擎：解决关系数据库的全文搜索性能问题，以Elasticsearch 为代表](#全文搜索引擎解决关系数据库的全文搜索性能问题)




# 关系数据库的缺点

     (1）关系数据库存储的是行记录，无法存储数据结构。以微博的关注为例，“我关注的人”是一个用户ID 列表，使用关系数据库存储只能将列表拆成多行，然后
         再查询出来组装，无法直接存储一个列表。

     (2）关系数据库的schema 扩展很不方便。关系数据库的表结构schema 是强约束，操作不存在的列会报错，业务变化时扩充列也比较麻烦，需要执行DDL 
         ( data definition l anguage ，如CREATE 、ALTER、DROP 等）语句修改，而且修改时可能会长时间锁表（例如， MySQL 可能将表锁住l 个小时）。
          
     (3）关系数据库在大数据场景下I/O 较高,例如，对一些大量数据的表进行统计之类的运算，关系数据库的I/O 会很高，因为即使只针对其中某一列进行运算，
         关系数据库也会将整行数据读取。

     (4）关系数据库的全文搜索功能比较弱。关系数据库的全文搜索只能使用like 进行整表扫描匹配，性能非常低，在互联网这种搜索复杂的场景下无法满足
         业务要求。

# 4种NoSQL方案

## K-V存储解决关系数据库无法存储数据结构的问题

     K-V 存储的全称是Key-Value 存储，其中Key 是数据的标识，和关系数据库中的主键含义一样， Value 就是具体的数据。

     Red is 是K-V 存储的典型代表，它是一款开源（基于BSD 许可）的高性能K-V 缓存和存储系统。Redi s 的Value 是具体的数据结构，包括stri ng 、
     hash 、li st 、set 、sorted set 、bitmap 和hyperloglog, 所以常常被称为数据结构服务器

   * [Redis](https://github.com/stevenli91748/Database/blob/master/Redis/README.md)


## 文档数据库解决关系数据库强schema约束的问题

   * [MongoDB](https://github.com/stevenli91748/Database/blob/master/MongoDB/README.md)  
   

## 列式数据库解决关系数据库大数据场景下的输入输出问题

   * [HBase](https://github.com/stevenli91748/Database/blob/master/HBase/README.md)

## 全文搜索引擎解决关系数据库的全文搜索性能问题

   * [Elasticsearch](https://github.com/stevenli91748/Database/blob/master/Elasticsearch/README.md)
