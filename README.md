
# [系统设计面试](https://github.com/stevenli91748/System-Design/blob/master/Interview/README.md)

# [服务器软件大盘点](https://mp.weixin.qq.com/s/J1XjIwtEKjaltqWH-0qmgw)

# 目录

#  System-Design
 * [技术架构汇总---详细描述了系统架构的方方面面  非常好](https://zhuanlan.zhihu.com/p/114876283?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656&utm_content=first)
 * [近二十年技术发展：从集中式架构到云原生架构](https://blog.csdn.net/weixin_44326589/article/details/93894615)
 
 <a href="https://ibb.co/M53YF64"><img src="https://i.ibb.co/DgSx0py/6ee62597-6d98-4af5-93b4-bc54f97c7936.png" alt="6ee62597-6d98-4af5-93b4-bc54f97c7936" border="0"></a>
 
 * [网站架构演变过程之传统架构](https://www.bilibili.com/video/av37162103?p=2)
 * [网站架构演变过程之分布式架构模式](https://www.bilibili.com/video/av37162103?p=3)
 * [网站架构演变过程之SOA架构模式](https://www.bilibili.com/video/av37162103?p=4)
 * [网站架构演变过程之微服务架构模式](https://www.bilibili.com/video/av37162103?p=5)
 
* [集中式架构与分布式架构比较](https://blog.csdn.net/qq_27384769/article/details/80223473) 
* [单体式架构和分布式架构有什么区别？](https://github.com/stevenli91748/System-Design/blob/master/单体架构基础/README.md)
* [服务器虚拟化技术简介](https://www.cnblogs.com/yogurtwu/p/9989200.html)
* [软件架构的演进 单体应用架构 VS 垂直应用架构 VS SOA架构 VS 微服务架构](https://blog.csdn.net/weixin_33446857/article/details/104170471?depth_1-utm_source=distribute.pc_relevant.none-task&utm_source=distribute.pc_relevant.none-task)
* [Restful架构和RPC架构浅析](https://blog.csdn.net/AlbenXie/article/details/104736868)
* [SOA架构是什么？](https://blog.csdn.net/u013343616/article/details/79460398)
* [SOA架构与微服务架构区别](https://www.bilibili.com/video/av37162103?from=search&seid=16399121196147863362)
* [Docker容器化组件架构](https://www.jdon.com/artichect/docker-containerization.html)
* [云原生技术和架构概述](https://blog.csdn.net/BtB5e6Nsu1g511Eg5XEg/article/details/86326182)

--- 

# 系统设计中的组件

类型|||||||项目中流行|
---|---|---|---|---|---|---|---|
API网关|Soul|Spring Cloud Gateway|Zuul|Apisix|Kong|Nginx|Kong|
服务调用|Dubbo|Ribbon+Feign|gRPC|SOFARPC|Motan|||
消息队列|RocketMQ|Kafka|RabbitMQ|ActiveMQ||||
作业调度|Elastic Job lite|Elastic job Cloud|Quartz|XXL-Job||||
注册中心|Eureka|Nacos|Zookeeper|Consul|Etcd|||
---|---|---|---|---|---|---|---|
配置中心|Apollo|Nacos|Spring Cloud Config|Disconf||||
---|---|---|---|---|---|---|---|
链路追踪|SkyWalking|Zipkin|CAT|Pinpoint||||
---|---|---|---|---|---|---|---|
服务器|Netty|Tomcat|Jetty|Nginx||||
---|---|---|---|---|---|---|---|
JAVA|JDK源码|JAVA并发|JVM|||||
---|---|---|---|---|---|---|---|
J2EE|Spring|Spring Boot|Spring Cloud|Spring Cloud Alibaba||||
---|---|---|---|---|---|---|---|
Web框架|Spring MVC|Spring Webflux|WebSocket|Web Service||||
---|---|---|---|---|---|---|---|
安全框架|Spring Security|Shiro|OAuth 2.0|||||
---|---|---|---|---|---|---|---|
ORM框架|MyBatis|Hibernate|Spring Data JPA|||||
---|---|---|---|---|---|---|---|
数据库连接池|HikariCP|Druid|多数据源|读写分离||||
---|---|---|---|---|---|---|---|
数据库中间件|Sharding JDBC|Sharding Sphere|MyCAT|Canal||||
---|---|---|---|---|---|---|---|
分布式事务|TCC Transaction|Seata|Fescar|Happylifeplat TCC||||
---|---|---|---|---|---|---|---|
数据库|MySQL|Redis|MongoDB|TiDB||||
---|---|---|---|---|---|---|---|
搜索引擎|Elasticsearch|Solr|Lucene|||||
---|---|---|---|---|---|---|---|
容器服务|Linux|Docker|Kubernetes|Swarm||||
---|---|---|---|---|---|---|---|
自我修养|设计模式|数据结构|算法|性能测试||||
---|---|---|---|---|---|---|---|
开发工具|Github|Maven|Jenkis|Intellij IDEA||||
---|---|---|---|---|---|---|---|
工具类|RXJava|Guava||||||
---|---|---|---|---|---|---|---|
监控体系|ELK|Prometheus|Spring Boot Admin|CAT|Sentry|||
---|---|---|---|---|---|---|---|
前端框架|React|Vue|Angular|||||
---|---|---|---|---|---|---|---|
大数据|HBase|Hive|Spark|Flink||||
---|---|---|---|---|---|---|---|




软件架构是软件系统的顶层结构，架构设计目的就是**解决软件系统复杂度（高性能 高可用 可扩展）**
 
 
**软件领域的复杂性体现在以下两个方面**

**1. 结构的复杂性**

      结构复杂的系统几乎毫无例外地具备两个特点： 组成复杂系统的组件数量更多，同时这些组件之间的关系也更加复杂
      
      结构上的复杂性存在的第一个问题是： 组件越多，就越有可能其中某个组件出现故障，从而导致系统故障
      
      结构上的复杂性存在的第二个问题是：某个组件改动，会影响关联的所有组件，这些被影响的组件同样会继续递归影响更多的组件
      
      结构上的复杂性存在的第三个问题是： 定位一个复杂系统中的问题总是比简单系统更加困难
      
**2. 逻辑的复杂性**

      逻辑复杂的组件一个典型特征就是单个组件承担了太多的功能
      
      功能复杂的组件另外一个典型特征就是采用了复杂的算法，复杂算法导致的问题主要是难以理解，进而导致难以实现、难以修改，井且出了问题难以快速解决。

**设计架构的套路**

**1. 有的放矢一一识别复杂度**

     架构设计的本质目的是为了解决软件系统的复杂性，所以在我们设计架构时，首先就要分析系统的复杂性。只有正确分析出了系统的复杂性，后续的架构设计方案
     才不会偏离方向；否则如果对系统的复杂性进行了错误的判断，即使后续的架构设计方案再完美再先进，都是南辗北辙，做得越好，错得越多、越离谱。 

     架构的复杂度主要来源于“高性能”“高可用”“可扩展”等几个方面，但架构师在具体判断复杂性的时候，不能生搬硬套，认为任何时候都从这三个方面进行复杂度
     分析就可以了。实际上绝大部分场景下，复杂度只是其中的某一个，少数情况下包含其中两个，如果真的出现同时需要解决三个或三个以上的复杂度，要么说明
     这个系统之前做得实在是太烂了，要么架构师的判断出现了严重失误。
   
     如果运气真的不好，接手了一个每个复杂度都存在问题的系统，那应该怎么办呢？正确的做法是将主要的复杂度问题列出来，然后根据业务、技术、团队等综合情
     况进行排序，优先解决当前面临的最主要的复杂度问题,对于按照复杂度优先级解决的这种方式有一个普遍的担忧：如果按照优先级来解决复杂度，可能会出现解
     决了优先级排在前面的复杂度后，解决后续复杂度的方案需要将已经落地的方案推倒重来。这个担忧理论上是可能的，但现实中几乎是不可能出现的，原因在于软
     件系统的可塑性和易变性：对于同一个复杂度问题，软件系统的方案可以有多个，总是可以挑出综合来看性价比最高的方案。即使架构师决定要推倒重来，这个新
     的方案也必须能够同时解决己经被解决的复杂度问题，一般来说能够达到这种理想状态的方案基本都是依靠新技术的引入。

**2. 按图索骥一一设计备选方案**

     确定了系统面临的主要复杂度问题后，方案设计就有了明确的目标，我们就可以开始真正进行架构方案设计了。成熟的架构师首先对已经存在的技术非常熟悉，对
     己经经过验证的架构模式烂熟于心，然后根据自己对业务的理解，挑选合适的架构模式进行组合，再对组合后的方案进行修改和调整。
     
**2.1 各种场景验证过的成熟技术方案**

      高可用的主备方案
      集群方案
      高性能的负载均衡方案
      多路复用方案
      可扩展的分层方案
      插件化方案

**3. 深思熟虑一一评估和选择备选万案**


 
 没有设计的思想，你就不能成为一名架构师。架构师是一个能撸的了一手好代码，画的了一个漂亮的UML/原型，写的了一篇技术文档，更加能解决好项目关键技术的综合人才。架构师=前端工程师+后端程序员+系统分析师+关键技术解决+各种技术搭配+设计模式+部署调优+其他，可见架构师是多面手，在项目当中起到连接管理与项目成员的重要角色。因此，在通往大神级的架构师的道路上，**你需要懂需求、设计、代码、部署、架构、服务器、运维、调优等等。**
 
 
 
--- 
 
 一个能担负起企业级应用的架构师，脑海里常出现的词会是这些：**负载均衡、集群、分布式、高并发、高可用、易管理等等**，粗略说来，应具备以下知识技能：

（1）数据层：重点在于集群方案的选择，比如MySQL集群，集群方案很多，需要选择符合业务的方案，比如多主，主备，读写分离等等，是否还需要做高可用，是用lvs，还是zookeeper，是否需要例如mycat类中间件来管理数据库或者做数据分片等等。

（2）服务层：时髦一点，选择dubbo，微服务让团队开发耦合度没有那么高，各自关心各自的模块，都以服务方式发布出去。传统一点用springmvc+restful，在我看来，对于并发不高的系统，没有必要用dubbo。缓存的选择，涉及到文件缓存、数据库缓存，可以用memcached、ehcache、redis。

（3）应用层：框架太多，ssh,ssm,jfinal等等，选择适合项目团队的框架；UI界面，h5很美观，但对于浏览器的兼容就把开发人员搞哭了，可以选择成熟的ext或者easyui。

（4）网络层：多数开发人员都不用涉及，能了解下f5之类的就好。

（5）部署：是否需要用docker来部署，开源docker容器让部署轻量化，很容易就可以扩展一个节点，对于高并发、伸缩性要求高的场景可以使用。docker的出现，完全可以实现一键部署。是否需要负载均衡，可以选择硬负载（就是前面说的f5），也可以用软负载（nginx）。软负载的方案简单一点可以是apache+tomcat，需要考虑session复制，复杂一点选择lvs+haproxy。打包发布，熟练使用maven，能建立自己的maven私服，能指导项目成员使用maven打包发布。

（6）安全：大多数安全在网络层就解决了，但应用的安全不容忽视，比如需要考虑SQL注入，授权认证，这些目前框架都能解决，重点的安全问题来自框架本身，大多数应用选择框架都是开源的，如果团队没有能力修复漏洞只能等更新。

（7）其它方面：测试（自动化测试），版本管理（git or svn)，大数据（奇热无比），人工智能（高大上）等等。

有人问，架构师为什么还要写代码？我认为，需要一如既往的写，但写的目标不一样，理论水平和动手能力需要同时提高。深度方面，注重的设计思想和模式；广度方面，对于前沿技术，要不懈的追求和钻研，这样才能在未来技术架构选型做出合理的决策。

这里为大家分享一个学习路线：

**依次是开源框架解析专题---架构师筑基专题----高性能架构专题----微服务架构专题----团队协作开发专题----B2C商城实战专题**


# 1. 需求

### [1.1 软件需求规划](https://github.com/stevenli91748/Software-Architecture-Design/blob/master/软件需求规划/README.md)
  
### [1.2 软件需求开发](https://github.com/stevenli91748/Software-Architecture-Design/blob/master/软件需求开发/README.md)

### [1.3 邻域建模](https://github.com/stevenli91748/Software-Architecture-Design/blob/master/邻域建模/README.md)

### [1.4 确定关键需求](https://github.com/stevenli91748/Software-Architecture-Design/blob/master/确定关键需求/README.md)

 
# 2. 设计

**架构设计6个原则：**

**1. 看透需求**

    需求要全(功能需求 质量需求【性能 可用性 伸缩性 可展性，安全性】  约束需求)，需求间的矛盾关系要清楚(例如 性能最重要 可用性折衷)。
   
    通过熟悉理解需求，识别系统复杂性所在的地方，然后针对这些复杂点进行架构设计。
   
**2. 架构大方向正确**

    设计好概念架构，这是决定系统成败的关健。
   
    理解每个架构方案背后所需要解决的复杂点，然后才能对比自己的业务复杂点，参考复杂点相似的方案。

**3. 设计好架构的各个方面**

    运用多视图设计方法设计系统的不同方面
   
    架构设计并不是要面面俱到，不需要每个架构都具备高性能、高可用、高扩展等特点， 而是要识别出复杂点，然后有针对性地解决问题。
   
    为了满足系统功能等方面的功能性需求，必须运用逻辑架构视图制定分层 分层细化 功能模块 细化功能模块，通用模块 通用框架的设计决策
   
    为了满足性能，可用性等方面的质量性需求，必须运用运行架构视图制定相应的并行 分时 排队 缓存的设计决策。
   
    为了满足可展性，可重用性等方面的质量性需求，必须运用开发架构视图深入研究软件系统开发期间的代码文件组织和框架使用，制定相应的设计决策。
   
    为了满足约束等方面的约束需求, 必须运用物理架构视图制定物理拓朴的设计决策。

    下面以一个最简单的网站系统为例：

    假设我们要做一个学生信息管理系统，这个系统从逻辑的角度来拆分，可以分为登录注册模块,个人信息模块,个人成绩模块：从物理的角度来拆分，可以拆分为Nginx 、Web 服务器、MySQL .


**4. 合适原则**

     合适优于业界领先
     
**5. 简单原则**     
     
     简单优于复杂
     
     无论结构的复杂性，还是逻辑的复杂性，都会存在各种问题，所以架构设计时如果简单的方案和复杂的方案都可以满足需求，一定要选择简单的方案
     
**6. 演化原则**

     “演化优于一步到位”
     
     架构师在进行架构设计时需要牢记这个原则，时刻提醒自己不要贪大求全，或者盲目照搬大公司的做法，而是应该认真分析当前业务的特点，明确业务面临的主要问题，设计合理的架构，快速落地以满足业务需要，然后在运行过程中不断完善架构，不断随着业务演化架构。

## [2.1  概念架构设计](https://github.com/stevenli91748/Software-Architecture-Design/blob/master/概念架构设计/README.md)

  * 2.1.1 功能性设计
  
       * 功能的复杂度--功能越来越多，导致系统复杂度指数级上升
        
  * 2.1.2 非功能性设计
  
    系统非功能性设计的6个复杂度
    
    * 2.1.2.1.  [高性能架构](https://github.com/stevenli91748/System-Design/blob/master/High%20performance%20architecture/README.md)
    * 2.1.2.2.  [高可用性架构](https://github.com/stevenli91748/System-Design/blob/master/High%20availability%20architecture/README.md)
    * 2.1.2.3.  [高伸缩性架构](https://github.com/stevenli91748/System-Design/blob/master/Highly%20scalable%20architecture/README.md)
    * 2.1.2.4.  [高櫎展性架构](https://github.com/stevenli91748/System-Design/blob/master/高櫎展性架构/README.md)
    * 2.1.2.5.  [高安全性架构](https://github.com/stevenli91748/System-Design/blob/master/高安全性架构/README.md)
    * 2.1.2.6.  [高并发架构](https://github.com/stevenli91748/System-Design/blob/master/High%20concurrency%20architecture/README.md)


## [2.2  细化架构设计](https://github.com/stevenli91748/Software-Architecture-Design/blob/master/细化架构设计/README.md)

---

## 互联网系统架构模板

<a href="https://ibb.co/RCmqnhQ"><img src="https://i.ibb.co/XzgqByF/1-2.png" alt="1-2" border="0"></a>

### 采用RESTful API 技术
<p align="center">
  <img src="http://i.imgur.com/jj3A5N8.png">
  <br/>
</p>

---

### 采用微服务技术 + RESTful API 技术

![Imgur](http://i.imgur.com/jrUBAF7.png)

### 2.2.1. 前端架构
   * [DNS (Domain Name System)  ](https://github.com/stevenli91748/System-Design/blob/master/DNS/README.md)
     * DNS轮询
     * 智能DNS
   * 动静分离--静态资源独立部署
   * 图片服务
   * [CDN (Content Delivery Network)](https://github.com/stevenli91748/System-Design/blob/master/CDN/README.md)
      * [Push CDNs]
      * [Pull CDNs]
   * [反向代理](https://github.com/stevenli91748/System-Design/blob/master/Reverse%20Proxy/README.md)
   * GSLB全局负载均衡

### 2.2.2. 应用层架构
   * 开发框架
     * [从 MVC 到前后端分离 ](https://my.oschina.net/huangyong/blog/521891)
   * 用户层技术
     * 用户管理
       * SSO---单点登录
         * cookie
         * token
         * CAS
       * OAuth2.0---授登录  
     * 消息推送
       * 短信
       * 邮件
       * 站内信
       * App 推送
     * 图片云
     * 存储云
   * 业务层技术
     * 搜索引擎
     * 推荐系统
   * 页面渲染--API Gateway
       * [API Gateway](https://github.com/stevenli91748/System-Design/blob/master/APIGateWay/README.md)
       * [Writing API]
       * [Reading API]
       * [Searching API]
   * [负载均衡](https://github.com/stevenli91748/System-Design/blob/master/Load%20%20Balance/README.md)
   * Session管理
   * 动态页面静态化
   * 业务拆分
   * 虚拟化服务器

#### 2.2.3. [服务层架构](https://github.com/stevenli91748/System-Design/blob/master/Cache/README.md "时髦一点，选择dubbo，微服务让团队开发耦合度没有那么高，各自关心各自的模块，都以服务方式发布出去。传统一点用springmvc+restful，在我看来，对于并发不高的系统，没有必要用dubbo。缓存的选择，涉及到文件缓存、数据库缓存，可以用memcached、ehcache、redis")
   * 配置中心
   * 服务中心   
     * 服务名字系统
     * 服务总线系统
   * 分布式消息
     * 消息队列
       * RocketMQ
       * Kafka
       * ActiveMQ
     * 任务队列
     * 背压机制  
   * 分布式缓存
     * [缓存系统](https://github.com/stevenli91748/Database/blob/master/缓存系统/README.md)
       * [Client caching]
       * [HTTP  Caching]  
         * [HTTP----HTTP缓存机制](https://juejin.im/post/5a1d4e546fb9a0450f21af23)
       * [CDN caching]
       * [Web server caching ]
       * [Database caching]
       * [Application caching]
       * [Caching at database query level]
       * [Caching at object level]
       * [When to update the cache]
         * [Cache aside]
         * [Write through]
         * [Write behind]
         * [Refresh ahead]
   * [分布式session](https://github.com/stevenli91748/System-Design/blob/master/Session/README.md)
   * [分布式服务](https://github.com/stevenli91748/Distributed-System)
     * [Microservice](https://github.com/stevenli91748/MicroService)
     * [Service Discovery]
   

   
### 2.2.4. 存储层架构
   * 分布式文件
      * 小文件存储
        * [HBase](https://github.com/stevenli91748/Database/blob/master/HBase/README.md)
        * Hadoop
        * Hypertable
        * FastDFS
        * TFS(taobao)
        * JFS(JD)
        * Haystack(facebook)
      * 大文件存储
        * Hadoop
        * [HBase](https://github.com/stevenli91748/Database/blob/master/HBase/README.md)
        * Storm
        * Hive
   * [关系数据库](https://github.com/stevenli91748/Database/blob/master/关系数据库/README.md)
     * [Master slave replication]
     * [Master master replication]
     * [Federation]
     * [Sharding]
     * [Denormalization]
     * [SQL tuning]
   * [非关系数据库NoSQL](https://github.com/stevenli91748/System-Design/blob/master/High%20performance%20architecture/NoSQL数据库集群.md)
     * [key-value store]
     * [Document store]
     * [Wide column store ]
     * [Graph database]
   * 数据同步
   
### 2.2.5 开发层架构
   * 开发框架
     * JAVA
       * 主流的java web框架
         * 以servlet为标准的框架
           * SSM
           * Spring
           * SpringMVC
           * SpringBoot
           * SpringCloud
         * 无servlet的框架
           * Netty
           * Playframework
           * Actframework
       * PC客户端应用开发
         * javaFX 
       * Android应用开发
       * 服务端程序开发
         * RPC
         * MQ
       * 大数据技术开发
         * HBase
         * Accumulo
         * ElasticSearchas
     * 非Java
       * Node.js
       * 
   * WEB服务器
     * Tomcat
     * Nginx
     * JBoss
     * Resin
   * 容器
     * [Docker](https://github.com/stevenli91748/Engineering-special/blob/master/Docker/README.md)
     
### 2.2.6 网络层架构
   * 负载均衡
     * [DNS (Domain Name System)---用于实现地理级别的负载均衡  ](https://github.com/stevenli91748/System-Design/blob/master/DNS/README.md)
     * Nginx & LVS & F5----用于同一地点内机器级别的负载均衡
     * [CDN (Content Delivery Network)](https://github.com/stevenli91748/System-Design/blob/master/CDN/README.md)
       * [Push CDNs]
       * [Pull CDNs]
     * 分布式存储
     * 全局负载均衡
     * 网络重定向
     * 流量控制
   * [网络通信](https://github.com/stevenli91748/Network/blob/master/README.md)
   * 多机房
   * 多中心

### 2.2.7 后台架构
   * 运维平台架构
     * 配置
     * 部署
     * 监控
     * 应急
   * [测试平台架构](https://github.com/stevenli91748/Testing/blob/master/README.md)
     * 单元测试
     * 集成测试
     * 接口测试
     * 性能测试
   * 数据平台架构
     * 数据管理
     * 数据分析
     * 数据应用
       * 数据采集与监控架构
         * 浏览器数据采集
         * 服务器业务数据采集
         * 服务器性能数据采集
         * 系统监控
         * 系统报警

   * 管理平台架构
     * 权限管理
       * 身份认证
       * 权限控制
     
 ---  

# 3. 代码开发步骤

  * [系统分析]
  * [数据库准备和逆向工程]
    * [代码生成器---在数据库设计完毕，准备搭建项目框架的时候，是非常有用的，可一定程度上加快项目开发速度](https://my.oschina.net/huangyong/blog/162138)
    * [直接运行SQL脚本]
    * [使用逆向工程生成 mapper 和 POJO]
  * [搭建maven环境--nexus私服]
  * []()  

---

# 4. 部署

 * [java项目部署服务器，云服务器部署的学习](https://www.bilibili.com/video/av66317648?from=search&seid=51472329364734361)
 * [gitlab前后端项目部署集成](https://www.bilibili.com/video/av67379275?from=search&seid=51472329364734361)
 * [腾讯云项目部署](https://www.bilibili.com/video/av66600923?from=search&seid=51472329364734361)
 * [一个完整实操演示揭露Jenkins项目部署发布过程](https://www.bilibili.com/video/av49707383?from=search&seid=51472329364734361)
 
---

# 5. 服务器

---

# 6. 运维

---

# 7. 调优

---






# 参考书籍
 * 从零开始学架构：照着做，你也能成为架构师.pdf
 * 从零开始学架构--系列文集.pdf
 * 人人都是架构师  分布式系统架构落地与瓶颈突破.pdf
 * 大型网站技术核心原理与案例分析.pdf
 * 大型网站技术架构演进与性能优化.pdf
 * 软件架构设计：大型网站技术架构与业务架构融合之道.pdf
 * 架构解密.从分布式到微服务.pdf
 * 亿级流量网站架构核心技术+跟开涛学搭建高可用高并发系统.pdf
 * 架构宝典架构.pdf
 * 聊聊架构.pdf
 * 架构真经-互联网技术架构的设计原则.pdf
 
 * [大型网站架构系列：20本技术书籍推荐](https://blog.csdn.net/zdy0_2004/article/details/50513152)
 
# 架构视频
  * [节日红包雨，高并发下的架构解决方案](https://www.bilibili.com/video/BV1Kt4y197G5?from=search&seid=3541957352485293330)
  * [容器化+分布式+实战](https://www.bilibili.com/video/BV1Dz411q7Xi/?spm_id_from=333.788.videocard.2)
  * [架构难？也许只是你的思路不对](https://www.bilibili.com/video/BV11g4y1i7RH?from=search&seid=3541957352485293330)
  * [【阿里P8推荐】进阶架构师课程全集](https://www.bilibili.com/video/BV16J411g7zH/?spm_id_from=333.788.videocard.1)
  * [系统设计系列讲解](https://www.youtube.com/watch?v=8F0ckuArL1w&list=PLbhaS_83B97vSWVslD63vjIi5OTYmSVrk&index=103)
  * [系统设计系列讲解 Design Twitter](https://1o24bbs.com/t/topic/19573)
  * [【系统设计班】走进系统设计与新鲜事系统](https://www.youtube.com/watch?v=9dLMfcptD08)
  * [如何设计一个推荐系统](https://www.youtube.com/watch?v=MZkxusQ6GNo&t=9s)
  * [顶尖架构师：如何设计一个Uber](https://www.youtube.com/watch?v=oLmAEsMZZP0&t=2257s)
  * [ System Design](https://www.youtube.com/watch?v=quLrc3PbuIw&list=PLMCXHnjXnTnvo6alSjVkgxV-VH6EPyvoX)
  * [Systems Design Interview Concepts (for software engineers / full-stack web)](https://www.youtube.com/watch?v=REB_eGHK_P4)
  * [2020年【千锋】JavaEE+微服务架构开发课程框架应用（强烈推荐）](https://www.bilibili.com/video/av83887117?from=search&seid=10204331567303013188)
  * [千锋Java：容灾项目从入门到实战](https://www.bilibili.com/video/av45606377?from=search&seid=15013736168332447863)
  * [名师带你打造年薪千万Java架构师（完）](https://www.bilibili.com/video/av45612966?from=search&seid=12415339682838728596)
  * [阿里P8推荐:进阶架构师课程全集](https://www.bilibili.com/video/av68678454/?spm_id_from=333.788.videocard.1)
  * [阿里P8架构师细谈：最实用的系统架构技术，看架构设计的套路](https://www.bilibili.com/video/av54611735/?spm_id_from=333.788.videocard.3)
  * [携程的架构师-杨波]()
    * [第一章：课程介绍和案例需求 (5讲)](https://www.bilibili.com/video/av68179639)
    * [第二章：系统架构设计和技术栈选型 (8讲)](https://www.bilibili.com/video/av68179794)
    * [第三章：服务开发框架设计和实现 (10讲)](https://www.bilibili.com/video/av68184057)
    * [第四章：可编程网关设计和实践 (9讲)](https://www.bilibili.com/video/av68184287)
    * [第五章：安全框架设计和实践 (10讲)](https://www.bilibili.com/video/av69043943)
    * [第六章：服务测试设计和实践 (7讲)](https://www.bilibili.com/video/av69044240)
    * [第七章：可运维架构设计和实践 (8讲)](https://www.bilibili.com/video/av69044490)
  * [美团架构师-高质量api网关接口设计（实战精品合集）](https://www.bilibili.com/video/av59601665/?spm_id_from=333.788.videocard.2)
  * [java架构知识——大型互联网公司必备之高质量API网关组件实现](https://www.bilibili.com/video/av53757089/?spm_id_from=333.788.videocard.7)
  * [Java高级架构师课程全套学习视频（2000分钟干货讲解](https://www.bilibili.com/video/av62954343/?spm_id_from=333.788.videocard.1)
  * [尚学堂-分布式亿级高并发电商项目教程](https://www.bilibili.com/video/av47984582/?spm_id_from=333.788.videocard.1)
  * [千锋Linux：大型网站高并发之集群教程](https://www.bilibili.com/video/av46476180?from=search&seid=9370548204597669311)
  * [Java分布式架构一线互联网公司分布式框架源码分析全集 --分库分表, 分布式缓存Flasher, 线程安全， 数据库中间件Sphere ](https://www.bilibili.com/video/av64434093)
  * [一小时高效搭建大规模集群环境session共享](https://www.bilibili.com/video/av61321932?from=search&seid=6662233512601703949)
  * [大并发服务器开发（实战）](https://www.bilibili.com/video/av45560719/?spm_id_from=333.788.videocard.0)
# 有用的参考
 * [烟囱式到SOA再到微服务](https://www.jianshu.com/p/a095c59baf31)
 * [分布式缓存架构设计](https://www.jianshu.com/p/39c9a48bd704)
 * [学完这100多技术，能当架构师么](http://www.imooc.com/article/details/id/291107)
 * [高并发服务端分布式系统设计概要](https://blog.csdn.net/liu136313/article/details/50530289?depth_1-utm_source=distribute.pc_relevant_right.none-task&utm_source=distribute.pc_relevant_right.none-task)
 * [不用找了，大厂在用的分库分表方案，都在这里！](https://www.jianshu.com/p/5b2bb76d26d6)
 * [如何设计一个高并发系统？](https://blog.csdn.net/A_BlackMoon/article/details/86286705?depth_1-utm_source=distribute.pc_relevant.none-task&utm_source=distribute.pc_relevant.none-task)
 * [老板让你抗住千万级流量，如何做架构设计](https://mp.weixin.qq.com/s?__biz=MzI3ODcxMzQzMw==&mid=2247487713&idx=1&sn=a59c4fbf67ec11da63c25064c5e21bb4&chksm=eb5395d7dc241cc1a1fc80fcfa65c58064560ecb8880387a9f21a575f66490b69dc238fad844&scene=21#wechat_redirect)
 * [MVC架构、RPC架构、SOA架构、微服务架构区别](https://blog.csdn.net/lmaosheng/article/details/88337678?depth_1-utm_source=distribute.pc_relevant.none-task&utm_source=distribute.pc_relevant.none-task)
 * [学会了这些技术，你离BAT大厂不远了---技术架构路径图](https://blog.csdn.net/z694644032/article/details/100084287)
 * [学完这100多技术，能当架构师么？](http://www.imooc.com/article/details/id/291107)
 * [从新手到架构师，一篇就够：从100到1000万高并发的架构演进之路](http://www.52im.net/thread-2665-1-1.html)
 * [关于一个大型web系统架构设计和技术选型的讨论摘录](https://blog.csdn.net/zhang_yingliang/article/details/50585343)
 * [大型web系统架构详解](https://blog.csdn.net/zhulongxi/article/details/73549028)
 * [服务端-高并发高可用设计原则/分布式架构演进过程](https://blog.csdn.net/hemin1003/article/details/95163321)
 * [打造互联网企业架构相关技术（实战干货）](https://blog.csdn.net/qq_27384769/article/details/79439922)
 * [如何规划学习步骤](https://blog.csdn.net/weixin_44135121/article/details/93226590)
 * [近二十年技术发展：从集中式架构到云原生架构](https://blog.csdn.net/weixin_44326589/article/details/93894615)
 * [分享一篇牛人的工作总结,让大家感受一下什么叫优秀的架构师](https://blog.csdn.net/smooth00/article/details/92803798)
 * [一个程序员如何能成为一名资深阿里P7架构师？](https://yq.aliyun.com/articles/660334)
 * [IT技术精华网关注搜索、分布式系统、云计算、系统架构设计、性能调优、Web开发、数据挖掘、推荐系统](http://www.chepoo.com)
 * [你是主流架构师吗](http://www.10tiao.com/html/158/201903/2649826500/1.html)
 * [程序员一般喜欢浏览哪些网站呢？](https://www.zhihu.com/question/283272958/answer/598956527?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656)
  * [最牛Java架构师进阶路线](https://blog.csdn.net/hang1995/article/details/79371268)
  * [石杉的架构笔记](https://juejin.im/user/5be0588ae51d452b0255727d)
  * [软件开发工作过程中的一些总结](http://www.youmeek.com/java-sofaware-engineer/)
  * [架构设计和技术选型的思路总结](https://blog.csdn.net/yl2isoft/article/details/53217833)
  * [后台服务程序框架技术选型方案](https://blog.csdn.net/coloriy/article/details/66969756)
  * [组件化、模块化、集中式、分布式、服务化、面向服务的架构、微服务架构](https://blog.csdn.net/AlbenXie/article/details/73478162)
  * [web前端技术框架选型参考](https://blog.csdn.net/aaa333qwe/article/details/78416211)
  * [几种后端开发技术的选型调研](https://blog.csdn.net/dipolar/article/details/51804192)
  * [后台服务程序框架技术选型方案](https://blog.csdn.net/coloriy/article/details/66969756)
  * [传统架构到分布式架构](https://blog.csdn.net/samjustin1/article/details/81073845)
  * [个人开发web应用，从需求设计，界面设计，数据库设计，API设计等，好的开发流程是怎么样的？](https://www.zhihu.com/question/24976128)
  * [一个比较不错的大型分布式网站架构技术总结，可做参考](https://blog.csdn.net/hjm4702192/article/details/79612611)
  * [大型分布式网站架构实战项目分析](https://blog.csdn.net/yunzhaji3762/article/details/80113693)
  * [大型网站架构演化](https://www.jianshu.com/p/526df44a11f1)
  * [技术方案设计](https://blog.csdn.net/my201110lc/article/details/82229611#_Toc512435238)
  * [架构师之路-创业互联网公司如何搭建自己的技术架构](https://blog.csdn.net/zhaorui2017/article/details/78133686)
  * [从 MVC 到前后端分离 ](https://my.oschina.net/huangyong/blog/521891)  
  
 ### 大型网站架构 
  * [深入解析java应用程序的一般架构（好文）](https://blog.csdn.net/hliq5399/article/details/51584622)
  * [LMAX架构](http://ifeve.com/lmax/)
  * [从 0 到 1，Java Web 网站架构搭建的技术演进](https://blog.csdn.net/qq_40267706/article/details/78628352)
  * [1千用户与1千万用户的网站系统架构区别？](https://blog.csdn.net/zqftisson/article/details/51777042)
  * [大型分布式电商系统架构是如何从0开始演进的？](https://blog.csdn.net/jianai0602/article/details/80346837)
  * [电商系统学习笔记之一系统架构](https://blog.csdn.net/hanruikai/article/details/79928211)
  * [百万级别网站架构思路](https://blog.csdn.net/ahjxhy2010/article/details/79854980)
  * [大型电商网站千万级别架构案例和技术架构【推荐】](https://blog.csdn.net/jianai0602/article/details/80346837)
  * [结合实例谈项目架构设计](https://blog.csdn.net/javayujiafeng/article/details/79086710)
  * [吃透这套架构演化图，从零搭建Web网站也不难！](https://mp.weixin.qq.com/s?__biz=MzI4NTA1MDEwNg==&mid=2650763749&idx=1&sn=74b4fea08061fde4e5cee4dca47246ce&chksm=f3f9c470c48e4d665e15ee6e156ca2a42d18a71cacefd0d07acba4e85259b65b34631a641628&scene=21#wechat_redirect)
  * [3分钟读懂何为分布式、微服务和集群](https://juejin.im/entry/59fa91225188255851320783)
  * [消息中间件如何实现每秒几十万的高并发写入？](https://juejin.im/post/5c7bd09b6fb9a049ba424c15)
  * [线上服务宕机时，如何保证数据100%不丢失](https://juejin.im/post/5c190f02518825046c2f6a5c)
  * [阿里 P9 级面试官是如何 360° 无死角考察候选人的？](https://blog.csdn.net/csdnnews/article/details/89702195)
  * [设计扛住千万级流量架构](https://blog.csdn.net/qq_35394891/article/details/80992999)
  
### 亿级流量系统架构

* [亿级流量系统架构之如何支撑百亿级数据的存储与计算](https://juejin.im/post/5bfab59fe51d4551584c7bcf)
* [亿级流量系统架构之如何设计高容错分布式计算系统](https://juejin.im/post/5bfbeeb9f265da61407e9679)
* [亿级流量系统架构之如何设计承载百亿流量的高性能架构](https://juejin.im/post/5bfd2df1e51d4574b133dd3a)
* [亿级流量系统架构之如何设计每秒十万查询的高并发架构](https://juejin.im/post/5bfe771251882509a7681b3a)
* [亿级流量系统架构之如何设计全链路99.99%高可用架构](https://juejin.im/post/5bffab686fb9a04a102f0022)
* [亿级流量系统架构之如何在上万并发场景下设计可扩展架构（上）](https://juejin.im/post/5c221654e51d45229f76e647)
* [亿级流量系统架构之如何保证百亿流量下的数据一致性（中）](https://juejin.im/post/5c3362dcf265da6134389321)
* [亿级流量系统架构之如何在上万并发场景下设计可扩展架构（下）](https://juejin.im/post/5c242848f265da615a41de2c)
* [亿级流量架构第二弹：你的系统真的无懈可击吗](https://juejin.im/post/5c2e07df6fb9a049c30b5f28)
* [亿级流量系统架构之如何保证百亿流量下的数据一致性（上）](https://juejin.im/post/5c321143f265da615304eb6b)
* [亿级流量系统架构之如何保证百亿流量下的数据一致性（中）](https://juejin.im/post/5c3362dcf265da6134389321)
* [亿级流量系统架构之如何保证百亿流量下的数据一致性（下）](https://juejin.im/post/5c34a74be51d4557db5a03fc)


### 项目经验
 * [一个经典面试题：如何保证缓存与数据库的双写一致性？](https://blog.csdn.net/devcloud/article/details/90440921)


# 项目实战

<a href="https://ibb.co/yfFwVxw"><img src="https://i.ibb.co/znVyNty/along.jpg" alt="along" border="0"></a>

* [项目实战1—LNMP的搭建、nginx的ssl加密、身份验证的实现](https://www.cnblogs.com/along21/p/7822228.html)
* [项目详解2—LVS负载均衡详解](https://www.cnblogs.com/along21/p/7784394.html)
* [项目实战2—实现基于LVS负载均衡集群的电商网站架构](https://www.cnblogs.com/along21/p/7833261.html)
* [项目实战2.1—nginx 反向代理负载均衡、动静分离和缓存的实现](https://www.cnblogs.com/along21/p/7842729.html)
* [项目实战3—实现基于Keepalived+LVS的高可用集群网站架构](https://www.cnblogs.com/along21/p/7841132.html)
* [项目实战4—HAProxy实现高级负载均衡实战和ACL控制](https://www.cnblogs.com/along21/p/7873998.html)
* [项目详解4—haproxy 反向代理负载均衡](https://www.cnblogs.com/along21/p/7899771.html)
* [项目实战5—企业级缓存系统varnish应用与实战](https://www.cnblogs.com/along21/p/7911628.html)
* [项目实战6—Mysql实现企业级日志管理、备份与恢复实战](https://www.cnblogs.com/along21/p/8005775.html)
* [项目实战7—Mysql实现企业级数据库主从复制架构实战](https://www.cnblogs.com/along21/p/8011596.html)
* [项目实战8—tomcat企业级Web应用服务器配置与会话保持](https://www.cnblogs.com/along21/p/8024719.html)
* [项目实战8.1-Linux下Tomcat开启查看GC信息](https://www.cnblogs.com/along21/p/9177578.html)
* [项目实战9—企业级分布式存储应用与实战MogileFS、FastDFS](https://www.cnblogs.com/along21/p/7911676.html)
* [项目实战10.1—企业级自动化运维工具应用实战-ansible](https://www.cnblogs.com/along21/p/8241542.html)
* [项目实战10.2--企业级自动化运维工具---puppet详解](https://www.cnblogs.com/along21/p/10369858.html)
* []()
* [项目实战11—企业级nosql数据库应用与实战-redis的主从和集群](https://www.cnblogs.com/along21/p/8027206.html)
* [项目实战12.1—企业级监控工具应用实战-zabbix安装与基础操作](https://www.cnblogs.com/along21/p/8118609.html)
* [项目实战12.2—企业级监控工具应用实战-zabbix操作进阶](https://www.cnblogs.com/along21/p/8119088.html)
* [项目实战13—企业级虚拟化Virtualization - KVM技术](https://www.cnblogs.com/along21/p/8116509.html)
* [项目实战14.1—ELK 企业内部日志分析系统](https://www.cnblogs.com/along21/p/8509123.html)
* [项目实战14.2--ELK 经典用法—企业自定义日志收集切割和mysql模块](https://www.cnblogs.com/along21/p/8513420.html)
* [项目实战14.3--ELK重难点总结和整体优化配置](https://www.cnblogs.com/along21/p/8613115.html)
* [项目实战15.1—企业级堡垒机 jumpserver一步一步搭建](https://www.cnblogs.com/along21/p/8795907.html)
* [项目实战15.2—企业级堡垒机 jumpserver快速入门](https://www.cnblogs.com/along21/p/8965968.html)
* [项目实战16.1--Jenkins持续集成01—Jenkins服务搭建和部署](https://www.cnblogs.com/along21/p/9724036.html)
* [项目实战16.2--Jenkins+Maven+Gitlab+Tomcat 自动化构建打包、部署](https://www.cnblogs.com/along21/p/10172855.html)
* [项目实战17--超详细“零”基础kafka入门篇](https://www.cnblogs.com/along21/p/10278100.html)
* [项目实战18--Hadoop+Hbase分布式集群架构“完全篇”](https://www.cnblogs.com/along21/p/10496468.html)














