**软件系统中高性能带来的复杂度主要体现在两方面， 一方面是单台计算机内部为了高性能带来的复杂度：另一方面是多台计算机集群为了高性能带来的复杂度。高性能架构设计主要集中在这两方面，除了以上两点，最终系统能否实现高性能，还和具体的实现及编码相关。但架构设计是高性能的基础，如果架构设计没有做到高性能，则后面的具体实现和编码能提升的空间是有限的。形象地说，架构设计决定了系统性能的上限，实现细节决定了系统性能的下限。**

# 要编写高性能的Spring Boot CRUD程序，可以采取以下几个步骤：

数据库设计：为了支持高性能，必须考虑数据库的性能和扩展性。可以使用索引、分区等技术来优化数据库性能。同时，应该根据具体业务场景来选择适合的数据库类型和版本，例如MySQL或PostgreSQL等。

编写DAO层：在DAO层，可以使用MyBatis或Hibernate等ORM框架来访问数据库。为了提高性能，可以使用批量操作、预编译语句等技术，减少数据库访问的次数和开销。另外，应该考虑使用数据库连接池技术，例如HikariCP或Druid等，来管理数据库连接，提高性能和稳定性。

编写Service层：在Service层，可以对DAO层的数据进行逻辑处理，并进行事务管理。为了提高性能，应该尽量避免重复计算和重复查询。可以使用缓存技术，例如Redis或Ehcache等，缓存热点数据，减少数据库访问。

编写Controller层：在Controller层，可以将请求路由到对应的Service层处理。为了提高性能，应该使用异步处理技术，例如Spring的@Async注解或Java的CompletableFuture类。另外，可以考虑使用响应式编程技术，例如Spring WebFlux或Reactor等，提高系统的吞吐量和响应速度。

配置服务器：在部署程序时，应该配置服务器来支持高性能。例如，可以优化JVM参数、调整线程池大小、增加服务器硬件资源等。另外，应该选择合适的Web服务器，例如Tomcat或Undertow等，来提高系统的性能和稳定性。

监控和调优：为了保持高性能，应该定期监控系统的性能，并进行调优。可以使用监控工具，例如JVisualVM或Grafana等来检测CPU使用、内存使用、GC情况等指标。根据监控结果，可以进行针对性的优化，例如调整缓存策略、优化SQL语句、增加服务器硬件资源等。

综上所述，要编写高性能的Spring Boot CRUD程序，需要综合使用多种技术和工具，包括数据库设计、ORM框架、缓存技术、异步处理、响应式编程和服务器配置等。同时，需要定期监控系统的性能，并进行调优，从而保持系统的高性能和稳定性。


# 在线书籍
* []()
* [高性能JAVA架构： 核心原理与案例实战](https://weread.qq.com/web/reader/6ba32c40726e7c066bad7ed)
* [MySQL管理之道：性能调优、高可用与监控（第2版）](https://weread.qq.com/web/reader/f5f329a05cd1a9f5f081b67)
* [千金良方：MySQL性能优化金字塔法则](https://weread.qq.com/web/reader/4aa3250071a74c1d4aacade)
----

[互联网“三高”架构实践：高可用 , 高性能 , 高并发](https://www.youtube.com/watch?v=IYsyRtHv_Is&t=4597s)|
---|


[系统接口 QPS 能达到多少? 轻量级性能测试工具 wrk](https://www.cnblogs.com/quanxiaoha/p/10661650.html)|
---|


# 前端高性能
  * 参考资料
    * 高性能网站建设指南--前端工程师技能精髓 对web前端架构做了非常好的讲解。注意此处的前端不只是 JS,CSS,HTML，是指业务逻辑层之前的部分。包括缓存，DNS等

# 后端高性能

  * 单台计算机内部为了高性能带来的复杂度
    * 单机操作系统
      * [进程](https://github.com/stevenli91748/JAVA-Architecture/tree/master/Java%20Advanced/Mutilthreading)
        * 多进程通信
          * 管道
          * 消息队列
          * 信号量
          * 共享存储
      * [线程](https://github.com/stevenli91748/JAVA-Architecture/tree/master/Java%20Advanced/Mutilthreading)
        * 多线程并发
        * 多线程通信
  * [多台计算机集群为了高性能带来的复杂度--让多台机器配合起来达到高性能的目的，是一个复杂的负载均衡任务](https://github.com/stevenli91748/System-Design/blob/master/Load%20%20Balance/README.md)
    * 任务分配---如何把任务分发到多台计算机
    * 任务分解---如何把大任务分解成小任务
    

# 性能测试
  * 不同视角下的架构性能
    * 开发视角
      * 响应延迟---使用缓存加速数据读取解决
      * 系统吞吐量---使用集群提高吞吐力解决
      * 并发处理能力---使用异步消息加快并发请求的响应及削峰解决
      * 系统稳定性---使用代码优化改善系统性能解决
    * 运维视角
      * 
  
  * 架构性能测试指标
    * 系统响应时间指标
    * 系统并发数指标
    * 系统吞吐量指标
      * TPS(每秒事务数)
      * HPS(每秒HTTP请求数)
      * QPS(每秒查询数)
      * 页面数/秒
      * 处理的业务数/小时
      * 请求数/秒
    * 性能计数器
      * System load
      * 对象与线程数
      * 内存使用
      * CPU使用
      * 磁盘与网络I/O
    
  * 架构性能测试方法
  * 架构性能测试报告
  * 架构性能优化策略

# 存储高性能
  * [关系数据库集群](https://github.com/stevenli91748/System-Design/blob/master/High%20performance%20architecture/关系数据库集群.md)
    * 读写分离
    * 分库分表
  * [NoSQL数据库集群](https://github.com/stevenli91748/Database/tree/master/NoSQL)
  * [缓存](https://github.com/stevenli91748/Database/blob/master/缓存系统/README.md)
    * 缓存穿透
    * 缓存雪崩
    * 缓存热点

# 计算高性能
  * 单服务器性能
    * [服务器采取的网络编程模型](https://github.com/stevenli91748/Network/blob/master/README.md)  
      * 服务器如何管理连接---操作系统的I/O 模型
        * 阻塞
        * 非阻塞
        * 同步
        * 异步
      * 服务器如何处理请求---操作系统的进程模型
        * 单进程
        * 多进程
        * 单线程
        * 多线程
    * [PPC](#PPC)
    * Prefork
    * TPC
    * Prethread
    * Reactor
    * Proactor
    
  * [集群高性能---负载均衡](https://github.com/stevenli91748/System-Design/blob/master/Load%20%20Balance/README.md)
  
    * 集群的分类
      * 运算系统集群
      * 存储系统集群
      * 缓存系统集群

    * 集群的复杂度

      **单个任务负载均衡分配器复杂度     **

     <a href="https://ibb.co/F0cP8VQ"><img src="https://i.ibb.co/nn4WQCX/2018-09-01-3.png" alt="2018-09-01-3" border="0"></a>


      **N个任务负载均衡分配器的复杂度**

      <a href="https://ibb.co/VSsDXpY"><img src="https://i.ibb.co/Z80Ky1z/1-2018-09-01-2.png" alt="1-2018-09-01-2" border="0"></a>
   
       

# 性能优化
  * WEB前端性能优化方法
    * 优化页面HTML
    * 利用浏览器端的并发和异步特性
    * 调整浏览器缓存策略
    * CDN加速
    * 反向代理
    * 浏览器优化
  * 应用服务器性能优化
    * 分布式缓存
    * 异步操作
    * 使用集群
    * 代码优化
  * 存储性能优化
    * B+树 vs LSM树

## PPC

   PPC 是Process per Connection 的缩写，其含义是指每次有新的连接就新建一个进程去专门处理这个连接的请求，这是传统的UNIX 网络服务器所采用的模型。


---


# 有用的参考

* 从零开始学架构：照着做，你也能成为架构师.pdf
* 从零开始学架构--系列文集（李运华）.pdf
* 大型网站技术核心原理与案例分析.pdf
* 亿级流量网站架构核心技术+跟开涛学搭建高可用高并发系统.pdf
* 软件架构设计：大型网站技术架构与业务架构融合之道.pdf
* 架构宝典架构.pdf
* 聊聊架构.pdf
* 架构真经-互联网技术架构的设计原则.pdf
* 高性能网站构建实战.pdf
* 高性能服务系统构建与实战.pdf



* [高性能Web架构](https://blog.csdn.net/rdhj5566/article/details/54906005)

* [高性能网络编程(一)：单台服务器并发TCP连接数到底可以有多少](http://www.52im.net/thread-561-1-1.html)
* [高性能网络编程(二)：上一个10年，著名的C10K并发连接问题](http://www.52im.net/thread-566-1-1.html)
* [高性能网络编程(三)：下一个10年，是时候考虑C10M并发问题了](http://www.52im.net/thread-568-1-1.html)
* [高性能网络编程(四)：从C10K到C10M高性能网络应用的理论探索](http://www.52im.net/thread-578-1-1.html)
* [高性能网络编程(五)：一文读懂高性能网络编程中的I/O模型](http://www.52im.net/thread-1935-1-1.html)
* [高性能网络编程(六)：一文读懂高性能网络编程中的线程模型](http://www.52im.net/thread-1939-1-1.html)

* [如何处理10000 TCP连接 ](https://www.oschina.net/translate/c10k)
