
所谓的system design是要做一个能够在现实世界中运行的系统的设计，所以说system design可以cover任何topic，从建大桥到做手机到做网站，而局限到软件，尤其是面试的scenario，大体局限于以下几种：

    1. Web application，典型例子：设计一个e-commerce商品的detail page(参考Amazon商品detail page)。设计一个online小游戏。设计一个论坛。
    2. 简单的Web Service，典型例子：设计一个short url service。
    3. 实时／半实时的消息update，典型例子：messenger，news feed。
    4. 数据系统，典型例子：top url hits, unique url hits
    5. 内容分发系统，典型例子：设计Netflix CDN
    6. 专业知识，典型例子：推荐系统，分布式系统基础架构，搜索。。

        基础知识的准备：
        1. 数据库 —— 了解relational数据库(Oracle/postgres)的基本知识，了解数据库的partition，了解查询，了解数据库的replication；了解现在流行的NoSQL databases: key-value database (Riak/DynamoDB)，document based(mongodb)，graph based, big table(or column based - HBase)...这里DynamoDB有个paper，关于eventually consistence需要明白CAP定理。
        2. 队列服务—— 了解Kafka或者Kinesis，明白队列服务的应用场景
        3. Web层，了解MVC，具体技术可以了解Spring，Nodejs
        4. 前端，了解Javascript，Html
        5. 了解SOAP和RESTful
        6. 理解cache——如何以及在何种情况下运用cache降低latency
        7. 理解现代分布式系统需要大量monitor以及log analysis
        8. 理解系统中不能有single point of failure，从failure的角度出发设计系统，运用Write Ahead Log进行故障恢复，充分replicate你的service所以任何一个机器、集群、机房的灾难都不会对你的整体服务造成不可挽回的影响
        9. 处理高并发，明白资源共享是影响并发的主要原因之一（另一个原因是进程间通信）——如何decouple共享资源，提高并发效率
        10. 明白基本的效率评定标准，如TPS。。。
        11. 理解一些分布式系统的基本概念，如上面提到的CAP，以及Consistent Hashing，Vector Clock
        12. 读一些paper，如Akamai的CDN，Amazon的Dynamo，Google的Map-reduce（很老嗯）等等
        13. 亲手实现一个简单的网站，从前端到数据库都接触一些
        14. 了解Hadoop的基本功能，如HDFS，Map-Reduce。
        15. 了解Apache Storm的基本功能。
        16. 结合所学的基础知识，考虑你所设计的系统的Availability，Scalability和Performance.


[系统设计学习资料](https://www.1point3acres.com/bbs/portal.php?mod=list&catid=8)|
---|


[Grokking System Design Interview](https://github.com/lei-hsia/grokking-system-design)|
---|

# 架构设计基础知识点

<details>
<summary>单体架构</summary>
* [单体架构,SOA架构,微服务架构,分布式架构,集群架构](https://www.jianshu.com/p/92ca0bfbd52f)
</details>|
---|

<details>
<summary>SOA架构</summary>
  
* [单体架构,SOA架构,微服务架构,分布式架构,集群架构](https://www.jianshu.com/p/92ca0bfbd52f)

</details>  

<details>
<summary>微服务架构</summary>
  
* [单体架构,SOA架构,微服务架构,分布式架构,集群架构](https://www.jianshu.com/p/92ca0bfbd52f)

<details>
<summary>架构是什麽？架构设计目的是什麽？</summary>

</details> 


</details>  

<details>
<summary>分布式架构</summary>
  
* [单体架构,SOA架构,微服务架构,分布式架构,集群架构](https://www.jianshu.com/p/92ca0bfbd52f)

</details>  

<details>
<summary>集群架构</summary>
  
* [单体架构,SOA架构,微服务架构,分布式架构,集群架构](https://www.jianshu.com/p/92ca0bfbd52f)

</details>  

<details>
<summary>系统与子系统</summary>

系统泛指由一群高关联的个体组成，根据某种规则运作，能完成个别元件不能单独完成的工作的群体。它的意思是“总体”“整体”或“联盟”。子系统的定义其实和系统的定义是一样的，只是观察的角度有差异，

</details>  

<details>
<summary>模块与组件</summary>
  
**软件模块（ Modu le ）**是一套一致且互相有紧密关联的软件组织， 包含程序和数据结构两部分。现代软件开发往往利用模块作为合成的单位。

模块的接口表达了由该模块提供的功能和调用时所需的元素。

模块是可能分开被编写的单位，这使得他们可再用，并允许开发人员同时协作、编写及研究不同的模块。

**软件组件**定义为自包含的、可编程的、可重用的、与语言无关的软件单元， 软件组件可以很容易地被用于组装应用程序。

**从逻辑的角度来拆分后得到的单元就是“模块”，从物理的角度来拆分系统得到的单元就是“组件”；划分模块的主要目的是职责分离，划分组件的主要目的是单元复用**

下面以一个最简单的网站系统为例，假设我们要做一个学生信息管理系统，这个系统从逻辑的角度来拆分，可以分为“登录注册模块” “个人信息模块” “个人成绩模块”：从物理的角度来拆分，可以拆分为Nginx 、Web 服务器、MySQL 。

</details>  

<details>
<summary>框架与架构</summary>
  
**软件框架（ Software Framework ）**通常指的是为了实现某个业界标准或完成特定基本任务的软件组件规范，也指为了实现某个软件组件规范肘， 提供规范所要求之基础功能的软件产晶。

**框架关注的是“规范”**

框架种类：
*  MVC框架
*  J2EE框架
*  MVP框架
*  MVVM框架

**软件架构指软件系统的顶层结构！**




</details>  

---

# 高性能架构知识点

---

# 高可用架构知识点

---

# 高櫎展性架构知识点

---

# 高并发架构知识点

---
