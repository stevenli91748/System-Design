
# 要编写高并发的Spring Boot CRUD程序，可以采取以下几个步骤：


[【高并发】学好并发编程的步骤，需要掌握这些核心知识体系。 重要！！ 重要！！ 重要！！  ](https://mp.weixin.qq.com/s?__biz=Mzg4MjU0OTM1OA==&mid=2247489161&idx=1&sn=4e5cb69ffd54e4bc083191dc44313d95&chksm=cf55a188f822289e0e2184932c3244bd3016c0011ce6b3865e219bdf372149cfc8d9a9653854&token=776659970&lang=zh_CN#rd)


**缓存带来的可见性问题、线程切换带来的原子性问题和编译优化带来的有序性问题，是导致并发编程频繁出现诡异问题的三个源头**

数据库设计：为了支持高并发，必须考虑数据库的性能和扩展性。可以使用分库分表、主从复制等技术来优化数据库性能。

编写DAO层：在DAO层，可以使用MyBatis或Hibernate等ORM框架来访问数据库。为了保证高并发，应该使用连接池技术来管理数据库连接，减少连接创建和销毁的开销。

编写Service层：在Service层，可以对DAO层的数据进行逻辑处理，并进行事务管理。为了提高并发性能，可以使用缓存技术，例如Redis或Memcached，减少数据库访问。

编写Controller层：在Controller层，可以将请求路由到对应的Service层处理。为了提高并发性能，可以使用异步处理技术，例如Spring的@Async注解或Java的CompletableFuture类。

配置服务器：在部署程序时，应该配置服务器来支持高并发。例如，可以使用Nginx或Apache等Web服务器作为反向代理，将请求分发到多个应用服务器上，从而提高并发性能。

监控和调优：为了保持高并发性能，应该定期监控系统的性能，并进行调优。可以使用监控工具，例如JConsole或VisualVM等来检测内存使用、线程数量等指标。

综上所述，要编写高并发的Spring Boot CRUD程序，需要综合使用多种技术和工具，包括数据库设计、ORM框架、缓存技术、异步处理、反向代理和监控调优等

# 在线书籍
* [Java高并发核心编程. 卷1, NIO、Netty、Redis、ZooKeeper](https://weread.qq.com/web/reader/e6d323b0723b6029e6d1c55)
* [Java高并发核心编程.卷2，多线程、锁、JMM、JUC、高并发设计模式](https://weread.qq.com/web/reader/9b93254072456ac19b9a176)
* [Netty、Redis、Zookeeper高并发实战](https://weread.qq.com/web/reader/1e732510718f63a11e7dee2)
* [Spring Cloud、Nginx高并发核心编程](https://weread.qq.com/web/reader/a2032080720a3143a204cce)
* [Java高并发与集合框架：JCF和JUC源码分析与实现](https://weread.qq.com/web/reader/a1d32580813ab6e8bg015744)
* [大数据高并发Redis一本通](https://weread.qq.com/web/reader/f2032c2072792dd3f200695)
* [基于Docker的Redis入门与实战](https://weread.qq.com/web/reader/f2932520725d0bbff2948bc)
* [Java高并发编程详解：深入理解并发核心库](https://weread.qq.com/web/reader/30b3225071eeefb430bb397)
* [实战Alibaba Sentinel：深度解析微服务高并发流量治理](https://weread.qq.com/web/reader/19132860813ab6d85g019c35)
* 深入理解高并发编程  核心原理与案例实战---冰河
* 深入理解高并发编程  JDK核心技术---冰河
* 深入理解高并发编程（第2版）---冰河
* 实战高并发设计模式---冰河
* 

# 博客

[字母哥---并发编程](https://mp.weixin.qq.com/mp/appmsgalbum?__biz=MzU0NDU5MTk1MQ==&action=getalbum&album_id=1576334194996232194#wechat_redirect)|
---|

---
# 视频
* [图灵--提升百倍吞吐量的多线程性能优化实战---一步一步教你怎样用多线程模式代码来开发高并发WEB程序](https://www.youtube.com/watch?v=_QQ3sxftM7A&t=509s)
* [2小时教你处理网站高并发问题](https://www.youtube.com/watch?v=hXlYe3yPo5g)
* [互联网“三高”架构实践：高可用 , 高性能 , 高并发](https://www.youtube.com/watch?v=IYsyRtHv_Is&t=4597s)
* [亿万级高并发分布式系统架构](https://www.youtube.com/@user-px5ls5xo6p/videos)


# 高并发目录
[【高并发】学好并发编程的步骤，需要掌握这些核心知识体系。 重要！！ 重要！！ 重要！！  ](https://mp.weixin.qq.com/s?__biz=Mzg4MjU0OTM1OA==&mid=2247489161&idx=1&sn=4e5cb69ffd54e4bc083191dc44313d95&chksm=cf55a188f822289e0e2184932c3244bd3016c0011ce6b3865e219bdf372149cfc8d9a9653854&token=776659970&lang=zh_CN#rd)
  * [1 【高并发】解密导致诡异并发问题的第一个幕后黑手——可见性问题](https://mp.weixin.qq.com/s?__biz=Mzg4MjU0OTM1OA==&mid=2247489365&idx=1&sn=f6b7b9f70b8653e7156fdf7c34c4a74d&source=41#wechat_redirect)
  * [2 【高并发】解密导致并发问题的第二个幕后黑手——原子性问题](https://mp.weixin.qq.com/s?__biz=Mzg4MjU0OTM1OA==&mid=2247489364&idx=1&sn=fdeca5407f03b9283bf7699b7882517b&source=41#wechat_redirect) 
  * [3 【高并发】解密导致并发问题的第三个幕后黑手——有序性问题](https://mp.weixin.qq.com/s?__biz=Mzg4MjU0OTM1OA==&mid=2247489363&idx=1&sn=247470d979a1180503a082e53259c5f5&source=41#wechat_redirect)
