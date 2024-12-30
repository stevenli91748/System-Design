
[【高并发】学好并发编程的步骤，需要掌握这些核心知识体系。 重要！！ 重要！！ 重要！！  ](https://mp.weixin.qq.com/s?__biz=Mzg4MjU0OTM1OA==&mid=2247489161&idx=1&sn=4e5cb69ffd54e4bc083191dc44313d95&chksm=cf55a188f822289e0e2184932c3244bd3016c0011ce6b3865e219bdf372149cfc8d9a9653854&token=776659970&lang=zh_CN#rd)

**并发编程总体上存在两大编程模型： 一种是内存共享模型，java中实现的并发编程主要为内存共享模型，稍不注意，就容易出现线程安全问题，另一种就是数据通信模型，Disruptor实现的并发编程
主要为数据通信模型，可以将Disruptor理解成高效的‘生产者-消费者’模型，并其性能远远高于传统的BlockingQueue等JDK中提供的容器**

**要实现高并发，一般有两个思路：异步和缓存。异步的策略可以按照如下方法来实施：梳理业务逻辑，将可以异步的流程都“异步”，可以保护下游的系统不受大流量的冲击。在操作系统中，我们学习了存储的多级存储结构，解决了CPU和内存速度不匹配的问题。同样在微服务系统中，不同的存储系统的访问速度也不相同，为了屏蔽这种差距，就需要使用缓存将常用的数据尽量前置，同样可以保护后端的系统。**

**并发编程可选择的方式有多进程、多线程和多协程。作者在另一本书《软件架构设计：大型网站技术架构与业务架构融合之道》中，曾对这三种方式进行了详细的比较。对于Java来说，它既不像C++那样，在运行中调用Linux的系统API去“fork”出多个进程；也不像Go那样，在语言层面原生提供多协程。在Java中，并发就是多线程模式。**

**缓存带来的可见性问题、线程切换带来的原子性问题和编译优化带来的有序性问题，是导致并发编程频繁出现诡异问题的三个源头**

# 要编写高并发的Spring Boot CRUD程序，可以采取以下几个步骤：

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
* Java高并发核心编程(卷3 加强版) -尼恩Java硬核架构班- 特供v21-release
* [Spring Cloud、Nginx高并发核心编程](https://weread.qq.com/web/reader/a2032080720a3143a204cce)
* [Java高并发与集合框架：JCF和JUC源码分析与实现](https://weread.qq.com/web/reader/a1d32580813ab6e8bg015744)
* [大数据高并发Redis一本通](https://weread.qq.com/web/reader/f2032c2072792dd3f200695)
* [基于Docker的Redis入门与实战](https://weread.qq.com/web/reader/f2932520725d0bbff2948bc)
* [Java高并发编程详解：深入理解并发核心库](https://weread.qq.com/web/reader/30b3225071eeefb430bb397)
* [实战Alibaba Sentinel：深度解析微服务高并发流量治理](https://weread.qq.com/web/reader/19132860813ab6d85g019c35)
* [java JUC 包](https://weread.qq.com/web/reader/810321a0721639f38103031k70532b302e3705f21728e67)
* [Netty、Redis、Zookeeper高并发实战------讲Netty 最好的书 是学分布式和并发的必备图书](https://weread.qq.com/web/reader/1e732510718f63a11e7dee2)
* [Spring Cloud、Nginx高并发核心编程---原理级”“思想级”经典图书 2020](https://weread.qq.com/web/reader/a2032080720a3143a204cce)
* [Java高并发编程详解-多线程与架构设计](https://weread.qq.com/web/reader/40632d70811e39a3ag018fbe)
* [java异步编程](https://weread.qq.com/web/reader/44332cc071a486a7443c539)
* [实战JAVA高并发程序设计（第2版）](https://weread.qq.com/web/reader/2b0326d0718487522b0092e)
* [JAVA并发原理： JDK源码剖析](https://weread.qq.com/web/reader/6de3271071dbddc06de1a75)
* [java并发编程之美](https://weread.qq.com/web/reader/81c32b507184869281c2a23)
* [大数据高并发 Redis一本通](https://weread.qq.com/web/reader/f2032c2072792dd3f200695)
* [web异步与实时交互](https://weread.qq.com/web/reader/de6324207159aca5de6e303)
* [java并发编程：核心方法与框架](https://weread.qq.com/web/reader/57532cb05c8bdb575bd45ba) 
* 深入理解高并发编程  核心原理与案例实战---冰河
* 深入理解高并发编程  JDK核心技术---冰河
* 深入理解高并发编程（第2版）---冰河
* 实战高并发设计模式---冰河
* 

# [并发知识点](https://github.com/stevenli91748/JAVA-Architecture/blob/master/Java%20Advanced/Concurrency/并发面试.md)

<a href="https://ibb.co/mh53RtF"><img src="https://i.ibb.co/6D0kybJ/java-concurrent-overview-1.png" alt="java-concurrent-overview-1" border="0"></a>



# 博客

[如何设计一个支撑高并发大流量系统的思路](https://articles.zsxq.com/id_nwldv7ahcltr.html)|
---|

[字母哥---并发编程](https://mp.weixin.qq.com/mp/appmsgalbum?__biz=MzU0NDU5MTk1MQ==&action=getalbum&album_id=1576334194996232194#wechat_redirect)|
---|

---
# 视频
 * [图灵--提升百倍吞吐量的多线程性能优化实战---一步一步教你怎样用多线程模式代码来开发高并发WEB程序](https://www.youtube.com/watch?v=_QQ3sxftM7A&t=509s)
 * [2小时教你处理网站高并发问题](https://www.youtube.com/watch?v=hXlYe3yPo5g)
 * [互联网“三高”架构实践：高可用 , 高性能 , 高并发](https://www.youtube.com/watch?v=IYsyRtHv_Is&t=4597s)
 * [亿万级高并发分布式系统架构](https://www.youtube.com/@user-px5ls5xo6p/videos)
 # SpringBoot并发编程的例子
  * [spring项目的并发程序是如何写的](https://github.com/stevenli91748/JAVA-Architecture/blob/master/Java%20Advanced/Concurrency/spring%E9%A1%B9%E7%9B%AE%E7%9A%84%E5%B9%B6%E5%8F%91%E7%A8%8B%E5%BA%8F%E6%98%AF%E5%A6%82%E4%BD%95%E5%86%99%E7%9A%84/README.md)
  * [SpringBoot实现Java高并发秒杀系统之DAO层开发（一）](https://developer.aliyun.com/article/664574)
  * [SpringBoot实现Java高并发秒杀系统之Service层开发（二）](https://developer.aliyun.com/article/665046?spm=a2c6h.13262185.profile.243.4e463ceeEAqu1W)
  * [SpringBoot实现Java高并发秒杀系统之Web层开发（三）](https://developer.aliyun.com/article/665347)
  * [SpringBoot实现Java高并发秒杀系统之并发优化（四）](https://blog.csdn.net/TyCoding/article/details/83046537)
 # 高并发编程的例子
  * [图灵  京东资深架构师：高性能高并发服务的瓶颈及突破思路太逆天了，没有之一](https://www.youtube.com/watch?v=SuF83l1c3PA&t=3913s)
---

# 高并发目录
* [【高并发】要想学好并发编程，关键是要理解这三个核心问题](https://mp.weixin.qq.com/s?__biz=Mzg4MjU0OTM1OA==&mid=2247489368&idx=1&sn=e856feb5e9c582e865fddbc91b91a636&source=41#wechat_redirect)
* [【高并发】学好并发编程的步骤，需要掌握这些核心知识体系。 重要！！ 重要！！ 重要！！  ](https://mp.weixin.qq.com/s?__biz=Mzg4MjU0OTM1OA==&mid=2247489161&idx=1&sn=4e5cb69ffd54e4bc083191dc44313d95&chksm=cf55a188f822289e0e2184932c3244bd3016c0011ce6b3865e219bdf372149cfc8d9a9653854&token=776659970&lang=zh_CN#rd)
    * [1 【高并发】解密导致诡异并发问题的第一个幕后黑手——可见性问题](https://mp.weixin.qq.com/s?__biz=Mzg4MjU0OTM1OA==&mid=2247489365&idx=1&sn=f6b7b9f70b8653e7156fdf7c34c4a74d&source=41#wechat_redirect)
    * [2 【高并发】解密导致并发问题的第二个幕后黑手——原子性问题](https://mp.weixin.qq.com/s?__biz=Mzg4MjU0OTM1OA==&mid=2247489364&idx=1&sn=fdeca5407f03b9283bf7699b7882517b&source=41#wechat_redirect) 
    * [3 【高并发】解密导致并发问题的第三个幕后黑手——有序性问题](https://mp.weixin.qq.com/s?__biz=Mzg4MjU0OTM1OA==&mid=2247489363&idx=1&sn=247470d979a1180503a082e53259c5f5&source=41#wechat_redirect)
* 七大并发模型
  * 基于内存共享模型的线程与锁--线程与锁模型有很多众所周知的不足，但仍是其他模型的技术基础，也是很多并发软件开发的首选
  * 函数式编程---函数式编程日渐重要的原因之一，是其对并发编程和并行编程提供了良好的支持。函数式编程消除了可变状态，所以从根本上是线程安全的，而且易于并行执行
  * Clojure之道---编程语言Clojure是一种指令式编程和函数式编程的混搭方案，在两种编程方式上取得了微妙的平衡来发挥两者的优势
  * actor---actor模型是一种适用性很广的并发编程模型，适用于共享内存模型和分布式内存模型，也适合解决地理分布型问题，能提供强大的容错性
  * 通信顺序进程（Communicating Sequential Processes，CSP）---表面上看，CSP模型与actor模型很相似，两者都基于消息传递。不过CSP模型侧重于传递信息的通道，而actor模型侧重于通道两端的实体，使用CSP模型的代码会带有明显不同的风格。
  * 数据级并行---每个笔记本电脑里都藏着一台超级计算机——GPU。GPU利用了数据级并行，不仅可以快速进行图像处理，也可以用于更广阔的领域。如果要进行有限元分析、流体力学计算或其他的大量数字计算，GPU的性能将是不二选择
  * Lambda架构---大数据时代的到来离不开并行——现在我们只需要增加计算资源，就能具有处理TB级数据的能力。Lambda架构综合了MapReduce和流式处理的特点，是一种可以处理多种大数据问题的架构 
  
* 基于内存共享模型的并发学习路径
  * [1 内存共享模型的并发原理](https://github.com/stevenli91748/System-Design/blob/master/High%20concurrency%20architecture/%E5%B9%B6%E5%8F%91%E5%9F%BA%E7%A1%80/%E5%B9%B6%E5%8F%91%E5%9F%BA%E7%A1%80%E7%9B%AE%E5%BD%95.md)
  * [2 java并发集合](https://github.com/stevenli91748/System-Design/blob/master/High%20concurrency%20architecture/java%E5%B9%B6%E5%8F%91%E9%9B%86%E5%90%88/java%E5%B9%B6%E5%8F%91%E9%9B%86%E5%90%88%E7%9B%AE%E5%BD%95.md)
  * [3 并发工具类](https://github.com/stevenli91748/System-Design/blob/master/High%20concurrency%20architecture/%E5%B9%B6%E5%8F%91%E5%B7%A5%E5%85%B7%E7%B1%BB/%E5%B9%B6%E5%8F%91%E5%B7%A5%E5%85%B7%E7%B1%BB%E7%9B%AE%E5%BD%95.md)
  * [4 java内存模型](https://github.com/stevenli91748/System-Design/blob/master/High%20concurrency%20architecture/java%E5%86%85%E5%AD%98%E6%A8%A1%E5%9E%8B/java%E5%86%85%E5%AD%98%E6%A8%A1%E5%9E%8B%E7%9B%AE%E5%BD%95.md)
  * [5 线程池](https://github.com/stevenli91748/System-Design/blob/master/High%20concurrency%20architecture/%E7%BA%BF%E7%A8%8B%E6%B1%A0/%E7%BA%BF%E7%A8%8B%E6%B1%A0%E7%9B%AE%E5%BD%95.md)
  * [6 阻塞对列](https://github.com/stevenli91748/System-Design/blob/master/High%20concurrency%20architecture/%E9%98%BB%E5%A1%9E%E5%AF%B9%E5%88%97/%E9%98%BB%E5%A1%9E%E5%AF%B9%E5%88%97%E7%9B%AE%E5%BD%95.md)
  * [7 锁](https://github.com/stevenli91748/System-Design/blob/master/High%20concurrency%20architecture/%E9%94%81/%E9%94%81%E7%9B%AE%E5%BD%95.md)
  * [8 Atomic](https://github.com/stevenli91748/System-Design/blob/master/High%20concurrency%20architecture/Atomic/Atomic%E7%9B%AE%E5%BD%95.md)
  * [9 常见的内存共享模型高并发策略](https://github.com/stevenli91748/System-Design/blob/master/High%20concurrency%20architecture/%E5%B8%B8%E8%A7%81%E7%9A%84%E5%86%85%E5%AD%98%E5%85%B1%E4%BA%AB%E6%A8%A1%E5%9E%8B%E9%AB%98%E5%B9%B6%E5%8F%91%E7%AD%96%E7%95%A5%E3%80%81%E5%B8%B8%E8%A7%81%E7%9A%84%E5%86%85%E5%AD%98%E5%85%B1%E4%BA%AB%E6%A8%A1%E5%9E%8B%E9%AB%98%E5%B9%B6%E5%8F%91%E7%AD%96%E7%95%A5/%E5%B8%B8%E8%A7%81%E7%9A%84%E5%86%85%E5%AD%98%E5%85%B1%E4%BA%AB%E6%A8%A1%E5%9E%8B%E9%AB%98%E5%B9%B6%E5%8F%91%E7%AD%96%E7%95%A5%E7%9B%AE%E5%BD%95.md)

# 目录
* [并发学习路线](#并发学习路线)
* [总结了几种不同的并发编程模式](https://github.com/aCoder2013/blog/issues/25)
* 并发的多种实现方式
  * 单进程-单线程模型，通过在一台服务器上启多个进程实现多任务的并行处理 
  * 单进程-多线程的模型进行多任务的并发处理
* [七大并发模型](#七大并发模型)
  * [线程与锁](#线程与锁)
    * 锁的种类
      * 1   乐观锁（CAS）
      * 2   悲观锁（synchronized, vector, hashtable）
      * 3   自旋锁（CAS）
      * 4   可重入锁（synchronized, Reentrantlock, lock）
      * 5   读写锁（ReentrantReadWriteLock, CopyOnWriteArrayList,CopyOnWriteArraySet）
      * 6   公平锁（Reentrantlock(true)）
      * 7   非公平锁（synchronized, Reentrantlock(false)） 
      * 8   共享锁（ReentrantReadWriteLock中读锁）
      * 9   独占锁（Synchronized,vector, hashtable, ReentrantReadWriteLock中写锁）
      * 10  重量级锁（synchronized）
      * 11  轻量级锁 (锁优化技术)
      * 12  偏向锁（锁优化技术）
      * 13  分段锁（ConcurrentHashMap）
      * 14  互斥锁 （synchronized）
      * 15  同步锁（synchronized）
      * 16  死锁（）
      * 17  锁粗化（锁优化技术）
      * 18  锁消除（锁优化技术）
  * [函数式编程](#函数式编程)
  * [Clojure之道](#Clojure之道)
  * [Actor](#Actor)
  * [通信顺序进程](#通信顺序进程)
  * [数据并行](#数据并行)
  * [Lambda架构](#Lambda架构)
* 并发基础知识
  * [高并发理论---阿姆达尔定律和局部性原理 ](https://weread.qq.com/web/reader/d9e327a07188b377d9eb7dak636320102206364d3f0ffdc)
  * java 高并发包
    * JMH
    * Java并发包之原子类型详解
    * Java并发包之工具类详解 
    * Java并发包之并发容器详解
    * Java并发包之ExecutorService详解
  * 高并发时代的必备技能
    * [Netty](https://github.com/stevenli91748/JAVA-Architecture/blob/master/Tools%20and%20Middleware/Netty/README.md)
    * [Redis](https://github.com/stevenli91748/Database/tree/master/Redis)
    * ZooKeeper
    * [高性能HTTP服务器组件（如Nginx）](https://github.com/stevenli91748/JAVA-Architecture/tree/master/Tools%20and%20Middleware/Nginx)
    * 高并发Java组件（JUC包 ）
  * 常见的高并发策略
    * [异步——提高业务过程中可异步部分的占比，提高异步部分的执行效率](https://weread.qq.com/web/reader/d9e327a07188b377d9eb7dak636320102206364d3f0ffdc)
      * **在JVM内部，使用代码级别的异步策略：异步线程池或异步回调机制**
        * **异步线程池**---线程池不允许使用Executors去创建，而是通过ThreadPoolExecutor的方式去创建，这样的处理方式让写的人员更明确线程池的运行规则，规避资源耗尽的风险
        * **异步回调机制**---异步回调跟同步调用的不同在于，请求发起方不需要等待服务方的响应返回，可以先去做别的业务，接口请求返回后，会自动调用预先埋设的回调函数，进行后续的业务处理。可以看出，异步回调模式改变了我们写代码的思考模型 
      * **在JVM外部，可以使用系统架构层面的异步策略： 消息队列、Redis队列等中间件**
        * **[消息队列](https://github.com/stevenli91748/Message-Server-System)**
        * **Redis队列**  
    * [缓存—将频繁访问的数据存储在离业务处理逻辑更近的地方](https://weread.qq.com/web/reader/d9e327a07188b377d9eb7dak636320102206364d3f0ffdc)
      * **读数据**---先尝试从缓存中读取数据，如果读到则直接返回；如果没有读到，则从DB中读取数据，并存入缓存，并将该数据返回给客户端 
      * **写数据**---在DB中的数据发生变更（更新或删除）时，需要先操作DB，再将缓存中的数据失效，如图5-9所示。注意，这里不是更新缓存中的数据，而是直接失效，由下一次读取该数据的进程重新写入缓存。这么
                 设计的原因是：如果有A和B两个进程在并发更新同一条数据，则可能的执行顺序为A更新DB、B更新DB、B更新缓存、A更新缓存，可以看到B的更新结果被A覆盖了
      * **缓存穿透**：一般的缓存系统都是按照key去缓存查询的，如果不存在对应的value，则应该去后端系统查找（比如DB）。如果key对应的value一定不存在，并且对该key并发请求量很大，就会对后端系统造成很大的压力。这就叫缓存穿透。
      * **缓存雪崩**：当缓存服务器重启或大量缓存集中在某一个时间段失效，在失效的时候，也会给后端系统（比如DB）带来很大压力。
      * **Redis能够存放的最大value值**是有限的，笔者曾经经历过的故障中，遇到过key对应的value值有700多MB，由于业务上对这个大value的读取操作影响了Redis集群的稳定性，从而影响了其他依赖同一缓存
        集群的业务方。           
      * **热点缓存**：缓存中的某些key（可能对应某个促销商品）对应的value存储在集群的一台机器中，使得所有流量涌向同一机器，成为系统的瓶颈。该问题的挑战在于它无法通过增加机器容量来解决。针对热点
        缓存，可以考虑加入本地缓存来缓解这种问题，不过本地缓存的大小一般都不大，因此需要严格控制热点key的数量，我们可以通过一个RateLimiter来统计过去一段时间内某个key被访问的次数，如果在1分
        钟之内被访问的次数超过了给定的阈值，就将该key设置为热点key。  
    * 池化—对于创建起来比较消耗资源的对象进行缓存 



---


* 在开发高并发系统时可以用三把利器来保护系统：**缓存、降级和限流**
  * 缓存---缓存的目的是提升系统访问速度和增大系统处理的容量，是抗高并发流量的“银弹
    * 应用级缓存
    * HTTP缓存
    * 多级缓存
  * 负载均衡
  * 降级---降级是当服务出现问题或者影响到核心流程时，需要暂时将其屏蔽掉，待高峰过去之后或者问题解决后再打开
  * 限流---而有些场景并不能用缓存和降级来解决，比如稀缺资源（秒杀、抢购）、写服务（如评论、下单）、频繁的复杂查询，因此需要有一种手段来限制这些场景的并发/请求量，即限流，限流的目的是通过对并发访问/请求进行限速或者对一个时间窗口内的请求进行限速来保护系统，一旦达到限制速率则可以拒绝服务（定向到错误页或友好的展示页）、排队或等待（比如秒杀、评论、下单等场景）、降级（返回兜底数据或默认数据），一般的中间件都会有单机限流框架，支持两种限流模式：控制速率和控制并发。
  * 连接池
    * 数据库连接池
    * HttpClient连接池
    * [线程池](https://weread.qq.com/web/reader/df532740723982c7df583bfkd67323c0227d67d8ab4fb04)
      * Java线程池
      * Tomcat线程池
  * 异步并发
    * 异步阻塞调用
    * 异步Future
    * 异步CallBack
    * 异步编排CompletableFuture
    * 异步Web服务实现
    * 请求环存
    * 请求合并
  * 队列
    * [阻塞队列（BlockingQueue）](https://weread.qq.com/web/reader/df532740723982c7df583bfk182326e0221182be0c5ca23) 
      * 1）ArrayBlockingQueue：基于数组实现的有界阻塞队列---常用
           * [ArrayBlockingQueue源码解析](https://weread.qq.com/web/reader/df532740723982c7df583bfk19c3222022419ca14e7eef7) 
      * 2）LinkedBlockingQueue：基于链表实现的有界阻塞队列---常用
           * [LinkedBlockingQueue源码解析](https://weread.qq.com/web/reader/df532740723982c7df583bfka5b325d0225a5bfc9e0772d) 
      * 3）PriorityBlockingQueue：支持按优先级排序的无界阻塞队列
      * 4）DelayQueue：优先级队列实现的无界阻塞队列
      * 5）SynchronousQueue：不存储元素的阻塞队列
      * 6）LinkedTransferQueue：基于链表实现的无界阻塞队列
      * 7）LinkedBlockingDeque：基于链表实现的双向无界阻塞队列 
    * 非阻塞队列
    * 应用场境
    * 缓冲队列
    * 任务队列
    * 消息队列
    * 请求队列
    * 数据总线队列
    * 混合队列
    * 其他队列
    * Disruptor+Redis队列
* 高并发方案
  * 架构中的各个组件的并发量规格
    * 并发量规格---并发量规格指的是连接数，不是线程数。
    * Web服务器并发量规格
      * Nginx(OpenResty)---mysql的并发量在4000-8000连接数
      * Netty---Netty的并发量在3000-6000连接数
      * Tomcat---tomcat官方宣称的并发量是1000连接数，厉害点的做点参数调优，也不过3000并发连接数
      * Apache---apache的并发比tomcat更不堪，200-300连接数
      * Weblogic---weblogic的并发稍好，平均能达到3000左右连接数
      * Webphere---
    * 程序中的并发量规格
      * Spring Boot的并发量规格---Spring Boot 能支持的最大并发量主要看其对默认Tomcat的设置，默认设置中，Tomcat的最大线程数是200，最大连接数是10000。
      * JVM的并发量规格---这取决于你使用的CPU，操作系统，其他进程正在做的事情，你使用的Java的版本，还有其他的因素,参考 [JVM最多支持多少个线程？](https://zhuanlan.zhihu.com/p/70371794)
    * 操作系统的并发量规格 
  * 并发容量规划
    * 吞吐量 响应时间与并发数
    * 压力测试与容量评估
  * 解决侧重于“高并发读”的系统问题
    * 策略1： 加缓存
      * [高并发场景下缓存处理的一些思路](https://mp.weixin.qq.com/s?__biz=MzI4Njc5NjM1NQ==&mid=2247488645&idx=1&sn=2d937355744f7b92f75417c022ba49a5&chksm=ebd62ba9dca1a2bf240151d8f57881cfd05965a2104c33a0e5891c7683ced6a38275561ba0d9&scene=21#wechat_redirect)
    * 策略2： 并发读
    * 策略3： 重写轻读
    * 读写分离（CQRS架构）
  * 解决侧重于“高并发写”的系统问题
    * 策略1：数据分片
      * 数据库拆分
        * 分库分表策略
        * 使用sharding-jdbc分库分表
        * sharding-jdbc分库分表配置
        * 使用sharding-jdbc读写分离         
    * 策略2：任务分片
    * 策略3：异步并发
    * 策略4：批量
    * 策略5：串行化 + 多进程单线程 + 异步I/O
  * 解决侧重于“高并发读” 和 “高并发写”的系统问题
* 并发关键字
* Lock体系
  * [Java注解如何基于Redission实现分布式锁](https://www.jb51.net/article/178525.htm)
  * [Java基于注解实现的锁实例解析](https://www.jb51.net/article/181492.htm)
* [并发容器](https://weread.qq.com/web/reader/df532740723982c7df583bfk6ea321b021d6ea9ab1ba605)
* [线程池](https://weread.qq.com/web/reader/df532740723982c7df583bfkd67323c0227d67d8ab4fb04)
* [原子操作类](https://weread.qq.com/web/reader/df532740723982c7df583bfk98f3284021498f137082c2e)
* 并发工具
* 并发实践 





# 博客

[怎样设置电脑CPU运行的核心数](https://www.youtube.com/shorts/lnn4nOh8c9E)|
---|

[Java 全栈知识体系---Java并发知识体系详解](https://www.pdai.tech/md/java/thread/java-thread-x-overview.html)|[Java Multithreading Tutorial example](https://www.javaguides.net/p/java-multithreading-utorial.html)|[Java Concurrency Tutorial example](https://www.javaguides.net/p/java-concurrency-tutorial.html)|
---|----|---|

[高并发三部曲](https://www.cnblogs.com/crazymakercircle/p/14365820.html)|[高并发分布式架构演进之路](https://zhuanlan.zhihu.com/p/149369244)|[Java并发编程-解决并发：多线程应用没那么难写](https://segmentfault.com/a/1190000039000025?utm_source=sf-similar-article)|
---|---|---|

[精尽 Java【并发】学习指南](http://svip.iocoder.cn/Java/Concurrent/tutorials/)|[高并发都要学哪些技术](https://zhuanlan.zhihu.com/p/139509856?utm_source=wechat_session&utm_medium=social&utm_oi=991812777480134656)|[应用程序应对高并发的五步处理逻辑](https://www.coollf.com/archives/article-24)|
---|---|---|

[12个真实项目实战带你玩转Java并发编程](https://apppukyptrl1086.pc.xiaoe-tech.com/detail/p_60ab6413e4b07e4d7fd8458a/6)|[架构设计：高并发读取，高并发写入，并发设计规划落地方案思考](https://www.toutiao.com/a6898156832674775564/?log_from=fc0170d6dbb7f_1630131791697)|
---|---|

[Disruptor高并发开发框架](https://github.com/stevenli91748/JAVA-Architecture/blob/master/Java%20Advanced/%E5%88%86%E5%B8%83%E5%BC%8FDisruptor%E9%AB%98%E6%80%A7%E8%83%BD%E5%B9%B6%E5%8F%91%E6%A1%86%E6%9E%B6/README.md)|[Java并发知识体系详解](https://www.pdai.tech/md/java/thread/java-thread-x-overview.html)|
---|---|


[高并发编程从入门到精通（一）](https://juejin.im/post/6844904195091349512)|[高并发编程从入门到精通（二）](https://juejin.im/post/6844904199004635143)|[高并发编程从入门到精通（三）](https://juejin.im/post/6847902217123397639)|
---|---|---|

[高并发编程从入门到精通（四）](https://juejin.im/post/6847902217127755783)|[高并发编程从入门到精通（五）](https://juejin.im/post/6854573209778569230)|[高并发编程从入门到精通（六](https://juejin.im/post/6856562407142227982)|
---|---|---|

|[面试官问我高并发服务模型哪家强](https://mp.weixin.qq.com/s/_XPzjzM6Tp1KoeYJBOOTCg)|
---|

[java并发成神之路---JUC全方位解读脑图](https://naotu.baidu.com/file/89fb28b05e3395800f9dc2d332d2b198?token=9b45e08e55281667)|[Java多任务并行处理框架 Fork Join](https://www.bilibili.com/video/BV1Gp411R7YG)|
---|---|

[高并发系统中三大利器绝学-亿级高并发削峰](https://www.bilibili.com/video/BV1uW411P7HR)|[天猫高并发场景的订单号、ID生成策略](https://www.bilibili.com/video/BV1xs411571g)|
---|---|

[架构师带你深入研究，亿级高并发削峰利器](https://www.bilibili.com/video/BV1Ut411277z)|[Java必备技能，亿级高并发削峰利器](https://www.bilibili.com/video/BV1S4411X7qp)|
---|---|

[深入了解Java高并发通信模型NIO](https://www.bilibili.com/video/BV1x4411Z7ek)|[Java高可用/高并发/高性能系统的必备技术](https://www.bilibili.com/video/BV154411f74F)|
---|---|

[电商中常见的高并发怎么处理](https://www.bilibili.com/read/cv690850)|[高并发系统开发实战！美团大佬手把手直播教学](https://www.bilibili.com/video/BV1z4411z7FN?from=search&seid=9409290589494288789)|
---|---|

[操作系统能否支持百万连接?](https://cloud.tencent.com/developer/article/1114773)|[单台服务器并发百万级配置(转)](https://blog.csdn.net/luo200618/article/details/54133505/?utm_medium=distribute.pc_relevant.none-task-blog-baidujs_baidulandingword-0&spm=1001.2101.3001.4242)|[Netty 100万级高并发服务器配置](https://blog.csdn.net/crazymakercircle/article/details/83758107?utm_medium=distribute.pc_relevant.none-task-blog-baidujs_title-0&spm=1001.2101.3001.4242)|
---|---|---|


[公司项目并发量都特小，自己如何实际接触高并发项目](https://www.zhihu.com/question/267113602/answer/1861665973)|
---|

[Swoole 从入门到实战教程---高并发实战演示](https://laravelacademy.org/books/swoole-tutorial)|
---|

[guava---Google Java标准库的十全大补](https://github.com/google/guava)|[Guava RateLimiter 实现 API 限流，这才是正确的姿势](https://mp.weixin.qq.com/s/uyYqni2Li6DpaAYB0vniow)|
---|---|

# GPU并行开发

* [GPU 选购指南：训练 ML 模型，我必须买 RTX3080 吗？](https://www.infoq.cn/article/yujetuzzjhlnvjwrfo5s)

# 疯狂创客圈
###  JUC并发包
* [ CyclicBarrier 使用&核心原理 图解   ](https://www.cnblogs.com/crazymakercircle/p/13906379.html)
* [countDownLatch 使用&核心原理 图解](https://www.cnblogs.com/crazymakercircle/p/13906922.html)
* [Semaphore 使用&核心原理 图解](https://www.cnblogs.com/crazymakercircle/p/13907012.html)
* [跳表 核心原理 图解](https://www.cnblogs.com/crazymakercircle/p/13925511.html)
* [ConcurrentSkipListMap - 秒懂](https://www.cnblogs.com/crazymakercircle/p/13928386.html)
* [ConcurrentSkipListSet - 秒懂](https://www.cnblogs.com/crazymakercircle/p/13928504.html)

###  无锁编程 高并发框架

* [伪共享 （图解）](https://www.cnblogs.com/crazymakercircle/p/13909102.html)
* [disruptor （史上最全）](https://www.cnblogs.com/crazymakercircle/p/13909235.html)
* [Akka 框架的原理和入门实例](https://www.cnblogs.com/crazymakercircle/p/13910553.html)


# 视频
 * [2小时教你处理网站高并发问题](https://www.youtube.com/watch?v=hXlYe3yPo5g)
 * [Java高并发之魂：synchronized深度解析](https://www.imooc.com/learn/1086)
 * [玩转Java并发工具，精通JUC，成为并发多面手](https://drive.google.com/drive/folders/1OSoTu7hUjJ3my2cxLGy2VGeqyBsqEs8n)
 * [Java并发编程原理与实战](https://www.youtube.com/watch?v=10Xrkmqa9d0&list=PLStUqVcO94bhOvk5msq7gxkcxoP4Tc8mv)
 * [阿里巴巴大牛教你快速了解并发编程](https://www.bilibili.com/video/av19131750/?spm_id_from=333.788.videocard.17)
 * [程序员一线互联网面试必杀技Java并发编程之Volatile源码分析](https://www.bilibili.com/video/av68881701)
 * [JUC](https://www.bilibili.com/video/av68272550/?spm_id_from=333.788.videocard.2)
 * [juc 与 jvm - Java 必学 2019版本-阳哥- 尚硅谷](https://www.bilibili.com/video/av70166821?from=search&seid=4915820349885388522)
 * [2019最新最全Java并发编程全套源码解析原理与实战](https://www.bilibili.com/video/av65172968/?spm_id_from=333.788.videocard.8)
 * [并发编程专题-java内存模型jmm与volatile关键字详解](https://www.bilibili.com/video/av61474893?from=search&seid=808943440095103708)
 * [JAVA开发工程师/并发编程利器aqs源码深度解读](https://www.bilibili.com/video/av61176596?from=search&seid=9591105149997618327)
 
 # 高并发
 * [1. Java高并发秒杀API之业务分析与DAO层](https://www.imooc.com/learn/587)
 * [2. Java高并发秒杀API之Service层](https://www.imooc.com/learn/631)
 * [3. Java高并发秒杀API之web层](https://www.imooc.com/learn/630)
 * [4. Java高并发秒杀API之高并发优化](https://www.imooc.com/learn/632)
 
 
# 有用的参考
* 亿级流量Java高并发与网络编程实战.pdf
* 大型网站技术架构演进与性能优化.pdf
* 软件架构设计：大型网站技术架构与业务架构融合之道.pdf

* [并发编程面试题（2020最新版）](https://blog.csdn.net/ThinkWon/article/details/104863992)
* [并发网系列文章集](http://ifeve.com/paper-set/)
* [看动画学并发编程](https://sourceforge.net/projects/javaconcurrenta/)


## 高并发量的规格
 * [Java并发编程-解决并发：多线程应用没那么难写](https://segmentfault.com/a/1190000039000025?utm_source=sf-similar-article)
 * [linux的TCP连接数量最大不能超过65535个吗，那服务器是如何应对百万千万的并发的？](https://mp.weixin.qq.com/s/k_6Oi-_z-MpdytSvFSLN0A)
 * [OpenResty(Nginx)支持的并发量](https://www.cnblogs.com/Tanwheey/p/12689629.html)
 * [【杂谈】Spring Boot 默认支持的并发量](https://blog.csdn.net/f45056231p/article/details/97390548)
 * [springboot能抗住多少并发_并发测试神器，看看你的能不能抗住超过 5 万的并发用户](https://blog.csdn.net/weixin_39989688/article/details/111394127?utm_medium=distribute.pc_relevant.none-task-blog-baidujs_baidulandingword-0&spm=1001.2101.3001.4242)

* [聊聊高并发](https://blog.csdn.net/ITer_ZC/column/info/loveconcurrency)
* [我们来谈下高并发和分布式中的幂等处理](https://juejin.im/post/5c05f233e51d4524860fc51a)
* [关于java高并发设计整合-分布式事务(转发)](https://blog.csdn.net/rainyear/article/details/81294959)
* [Java系统的高并发解决方法详解](https://www.jb51.net/article/124145.htm)
* [Java使用代码模拟高并发操作的示例](https://www.jb51.net/article/139429.htm)
* [Java构建高并发高可用的电商平台架构实践](https://blog.csdn.net/lsm135/article/details/50920483)
* [【Java并发编程】并发编程大合集](https://blog.csdn.net/ns_code/article/details/17539599)
* [java系统高并发解决方案（转载）](https://blog.csdn.net/jimmy609/article/details/37810591)
* [Java并发-不懂原理多吃亏](http://ifeve.com/java-concureent/)
石杉的架构笔记
* [大白话聊聊Java并发面试问题之volatile到底是什么？](https://mp.weixin.qq.com/s/MIsQv8ZWWBzfB-Qhg3l4lA)
* [大白话聊聊Java并发面试问题之Java 8如何优化CAS性能？](https://mp.weixin.qq.com/s/KFsqsCVgyiiTDXMR-Hu1-Q)
* [大白话聊聊Java并发面试问题之谈谈你对AQS的理解？](https://mp.weixin.qq.com/s/PAn5oTlvVmjMepmCRdBnkQ)
* [大白话聊聊Java并发面试问题之公平锁与非公平锁是啥？](https://mp.weixin.qq.com/s/Os8tT1kBqsq0vteB6KD4hg)
* [大白话聊聊Java并发面试问题之微服务注册中心的读写锁优化](https://mp.weixin.qq.com/s/9SKmHeMu_1lNVEJPlEcpsA)
* [Java并发面试系列文章总结](https://mp.weixin.qq.com/s/vTCrilBQfeycbsFKVFQ-cA)
* [高并发场景下，如何保证生产者投递到消息中间件的消息不丢失？](https://mp.weixin.qq.com/s/r2_o5wa6Gn94NY4ViRnjpA)
* [从团队自研的百万并发中间件系统的内核设计看Java并发性能优化](https://juejin.im/post/5c3f708151882524b333b67f)
* [10倍请求压力来袭，你的系统会被击垮吗？](https://juejin.im/post/5c1baab7e51d455e4b55ff72)
* [大白话聊聊Java并发面试问题之微服务注册中心的读写锁优化](https://juejin.im/post/5c0c8540e51d451dbe4fdd83)
* [从团队自研的百万并发中间件系统的内核设计看Java并发性能优化](https://mp.weixin.qq.com/s/d4qfu2MxESc1YJV4Ud5mnA)
* [Java 线程池原理分析](https://www.tianxiaobo.com/2018/04/17/Java-%E7%BA%BF%E7%A8%8B%E6%B1%A0%E5%8E%9F%E7%90%86%E5%88%86%E6%9E%90/)
* [AbstractQueuedSynchronizer 原理分析 - 独占/共享模式](https://www.tianxiaobo.com/2018/05/01/AbstractQueuedSynchronizer-%E5%8E%9F%E7%90%86%E5%88%86%E6%9E%90-%E7%8B%AC%E5%8D%A0-%E5%85%B1%E4%BA%AB%E6%A8%A1%E5%BC%8F/)
* [AbstractQueuedSynchronizer 原理分析 - Condition 实现原理](https://www.tianxiaobo.com/2018/05/04/AbstractQueuedSynchronizer-%E5%8E%9F%E7%90%86%E5%88%86%E6%9E%90-Condition-%E5%AE%9E%E7%8E%B0%E5%8E%9F%E7%90%86/)
* [Java 重入锁 ReentrantLock 原理分析](https://www.tianxiaobo.com/2018/05/07/Java-%E9%87%8D%E5%85%A5%E9%94%81-ReentrantLock-%E5%8E%9F%E7%90%86%E5%88%86%E6%9E%90/)
* [Java 线程同步组件 CountDownLatch 与 CyclicBarrier 原理分析](https://www.tianxiaobo.com/2018/05/10/Java-%E7%BA%BF%E7%A8%8B%E5%90%8C%E6%AD%A5%E7%BB%84%E4%BB%B6-CountDownLatch-%E4%B8%8E-CyclicBarrier-%E5%8E%9F%E7%90%86%E5%88%86%E6%9E%90/)
* [Java CAS 原理分析](https://www.tianxiaobo.com/2018/05/15/Java-%E4%B8%AD%E7%9A%84-CAS-%E5%8E%9F%E7%90%86%E5%88%86%E6%9E%90/)


#### 2020汇总Java并发核心篇


* [深度源码剖析AQS的实现原理](https://youzhixueyuan.com/aqs.html)
* [Java从网络编程到高并发学习路线](https://coding.imooc.com/learningpath/route?pathId=11)
* [Java如何获取当前线程](https://mp.weixin.qq.com/s?__biz=MjM5MzA1Mzc3Nw==&mid=2247484573&idx=1&sn=6502f30deee7da855ff489e506867fbf&chksm=a69da9a391ea20b50f9e34870b6bf5e01f485a2e5bbc02eb52c0791fbd41a904551ba18f8bd3&scene=21#wechat_redirect)
* [从Java到JVM到OS线程睡眠](https://mp.weixin.qq.com/s?__biz=MjM5MzA1Mzc3Nw==&mid=2247484652&idx=1&sn=41833d8efde1ce3511171db8179409c4&chksm=a69da9d291ea20c458496ceddd7d482d3bc79a72f6221daaae671922b6523d91168a84310531&scene=21#wechat_redirect)
* [从Java到JVM到OS线程的优先级](https://mp.weixin.qq.com/s?__biz=MjM5MzA1Mzc3Nw==&mid=2247484542&idx=1&sn=3f0321d211c9739337f35f88daaf2c91&chksm=a69da94091ea2056a317aaca1f5d69888baccbe9cb210544a8c9d5f42a39eea0245bcf478a1e&scene=21#wechat_redirect)
* [Java线程的CPU时间片](https://mp.weixin.qq.com/s?__biz=MjM5MzA1Mzc3Nw==&mid=2247484453&idx=1&sn=08775b75b5011f5b3f08d9d9e83bf3fe&chksm=a69da91b91ea200dac3149709a27240f6eb510f6b085b044d3e5c0f11cb1a8b8b5d73244d776&scene=21#wechat_redirect)
* [ava线程的调度](https://mp.weixin.qq.com/s?__biz=MjM5MzA1Mzc3Nw==&mid=2247484460&idx=1&sn=f6c2dd1dc71e459c849556c7a32f06d2&chksm=a69da91291ea2004c88d2844c4f2d31e27afde39dd594e8d5bd1762a1a5d7eb6c3d5a09c7308&scene=21#wechat_redirect)
* [Java线程的状态](https://mp.weixin.qq.com/s?__biz=MjM5MzA1Mzc3Nw==&mid=2247484515&idx=1&sn=bfaac161978ccd9339d1b69f01a1bc0e&chksm=a69da95d91ea204b6419df5ac1be7655587995c14fc0f680aa7159fb33dcac16255a9360263d&scene=21#wechat_redirect)
* [乐观的并发策略——基于CAS的自旋](https://mp.weixin.qq.com/s?__biz=MjM5MzA1Mzc3Nw==&mid=2247484445&idx=1&sn=74812d16ffad546e0f376bb9ea8589e8&chksm=a69da92391ea20350e24b83fee91c70122e21b36100000bb74be5d3e455b8920fddc9efcbd82&scene=21#wechat_redirect)
* [悲观的并发策略——synchronized互斥锁](https://mp.weixin.qq.com/s?__biz=MjM5MzA1Mzc3Nw==&mid=2247484423&idx=1&sn=91bb67ff4b410f069c8390e5155f3950&chksm=a69da93991ea202f2da7541faf650b686676c96382ecd12827d4c50c184ca9f1eceaccc0c598&scene=21#wechat_redirect)
* [从JDK源码角度看并发的原子性如何保证](https://mp.weixin.qq.com/s?__biz=MjM5MzA1Mzc3Nw==&mid=2247483931&idx=1&sn=454f72dd2bda04baf363af702e795834&chksm=a69daf2591ea26330b8060fa3a86e2c28e46ac9f875d2f6e76696330dbebc1e83586859586cb&scene=21#wechat_redirect)
* [从 JDK 源码角度看 java 并发线程的中断](https://mp.weixin.qq.com/s?__biz=MjM5MzA1Mzc3Nw==&mid=2247483827&idx=1&sn=49da65b4f48f31418d1d8698764dbba3&chksm=a69dac8d91ea259b2de74d3a99ded3c1952abac4dc0dc3e58da98e3b835fde6054327c1ed694&scene=21#wechat_redirect)
* [JDK源码角度看并发锁的优化](https://mp.weixin.qq.com/s?__biz=MjM5MzA1Mzc3Nw==&mid=2247483782&idx=1&sn=88df28cc2eb5a2308ed6a780442a7533&chksm=a69dacb891ea25ae1cd304dbb4725ddda1a577adba8ce7331cf8fec061575d7107ce9d26e4dc&scene=21#wechat_redirect)
* [从JDK源码角度看线程的阻塞和唤醒](https://mp.weixin.qq.com/s?__biz=MjM5MzA1Mzc3Nw==&mid=2247483772&idx=1&sn=22a4bc28d71393ac539486f71d492b71&chksm=a69dac4291ea2554eb4f7a45b6a89a11cb8e43c3e10c3c7c757565a51802dd31dfbc64bb1698&scene=21#wechat_redirect)
* [从JDK源码角度看并发竞争的超时](https://mp.weixin.qq.com/s?__biz=MjM5MzA1Mzc3Nw==&mid=2247483751&idx=1&sn=0f6b64e617ee652f3975f19fd18d521a&chksm=a69dac5991ea254ff23ab06b3d23ee7141dde8f484595dfde5bbf780d6fa810b0ee1d57b6a49&scene=21#wechat_redirect)
* [从 JDK 源码角度看 Java 并发的公平性](https://mp.weixin.qq.com/s?__biz=MjM5MzA1Mzc3Nw==&mid=2247483743&idx=1&sn=4dda60569cf2e58e38bef39ae9741d2d&chksm=a69dac6191ea25774851339a6d36443a67c1f610f33ce8513fa65b5f11dbfa66a6734ced5dd7&scene=21#wechat_redirect)
* [volatile足以保证数据同步吗](https://mp.weixin.qq.com/s?__biz=MjM5MzA1Mzc3Nw==&mid=2247483960&idx=1&sn=bd1fa1639ac7da0f45667db7cbfb12d8&chksm=a69daf0691ea2610c7c7d85694ed046928de7f7e98ae6d54fa272b235b44c0e953be180cef5a&scene=21#wechat_redirect)
* [Java 内存模型](https://mp.weixin.qq.com/s?__biz=MjM5MzA1Mzc3Nw==&mid=2247484074&idx=1&sn=8a98892077ff90582865f5542aba4253&chksm=a69daf9491ea268205b816a4ea5ef5e4d925a1564fbcb8894d10c086daf61534f641ad489979&scene=21#wechat_redirect)
* [JDK并发AQS系列(一)](https://mp.weixin.qq.com/s?__biz=MjM5MzA1Mzc3Nw==&mid=2247484695&idx=1&sn=06a69ff81ddd44b8051a6771bf471a57&chksm=a69da82991ea213fab0c84ddfbd7d9ae49c84c867ee4b13ac74105c69a83461d91bb463d7191&scene=21#wechat_redirect)
* [JDK并发AQS系列(二)](https://mp.weixin.qq.com/s?__biz=MjM5MzA1Mzc3Nw==&mid=2247484703&idx=1&sn=b45477953fcd67e1bd4a91e3e9e21a77&chksm=a69da82191ea2137b215892608638a68efd40dbe47acd2a60882ab45085b75255c67e651d48a&scene=21#wechat_redirect)
* [JDK并发AQS系列(三)](https://mp.weixin.qq.com/s?__biz=MjM5MzA1Mzc3Nw==&mid=2247484715&idx=1&sn=05f593d428946d6a514e0ddaf447d48f&chksm=a69da81591ea2103eb9792cedde0458ee94c4c229ee592536608bfafbae5f14639ec7643df52&scene=21#wechat_redirect)
* [JDK并发AQS系列(四)](https://mp.weixin.qq.com/s?__biz=MjM5MzA1Mzc3Nw==&mid=2247484723&idx=1&sn=c8eb8fad43662f010b599b23c1701874&chksm=a69da80d91ea211b2865beb79d6d0671e6850589dd5b500aada656a1d8c64c5708eeab73e5bc&scene=21#wechat_redirect)
* [JDK并发AQS系列(五)](https://mp.weixin.qq.com/s?__biz=MjM5MzA1Mzc3Nw==&mid=2247484731&idx=1&sn=ab2953011ff87bb863d1aec8fdd176dc&chksm=a69da80591ea21133cc8a3057b73c0bda4cc833c8a7cb16ee6a93cd2db0fcad167e546244aba&scene=21#wechat_redirect)
* [Java并发编程：深入剖析ThreadLocal](https://www.cnblogs.com/dolphin0520/p/3920407.html)
* [聊聊并发系列文章](http://ifeve.com/talk-concurrency/)
* [从Java视角理解系统结构(一)CPU上下文切换](http://ifeve.com/java-context-switch/)
* [从Java视角理解系统结构（二）CPU缓存](http://ifeve.com/from-javaeye-cpu-cache/)
* [从Java视角理解系统结构（三）伪共享](http://ifeve.com/from-javaeye-false-sharing/)
* [Java 7 并发编程指南中文版](http://ifeve.com/java-7-concurrency-cookbook/)
* [Java并发性和多线程介绍目录](http://ifeve.com/java-concurrency-thread-directory/)
* [CPU缓存刷新的误解](http://ifeve.com/cpu-cache-flushing-fallacy-cn/)
* [伪共享(False Sharing)](http://ifeve.com/falsesharing/)
* [Java 7与伪共享的新仇旧恨](http://ifeve.com/false-shareing-java-7-cn/)
* [内存访问模型的重要性](http://ifeve.com/memory-access-patterns-are-important-2/)
* [Memory Barriers/Fences](http://ifeve.com/mechanical-sympathy/)
* [合并写(write combining)](http://ifeve.com/writecombining/)
* [内存屏障](http://ifeve.com/memory-barriers-or-fences/)
* [Java并发结构](http://ifeve.com/java-concurrency-constructs/)
* [任务取消(Cancellation)](http://ifeve.com/cancellation/)
* [JUC同步框架 ](http://ifeve.com/aqs/)
* [并发数据结构](http://ifeve.com/concurrent-data-structures/)
* [J.U.C并发框架](http://ifeve.com/j-u-c-framework/)
* [并发框架Disruptor](http://ifeve.com/disruptor/)
* [Oracle官方并发教程](http://ifeve.com/oracle-java-concurrency-tutorial/)
* [聊聊并发（一）深入分析Volatile的实现原理](http://ifeve.com/volatile/)
* [聊聊并发（二）Java SE1.6中的Synchronized](http://ifeve.com/java-synchronized/)
* [聊聊并发（三）Java线程池的分析和使用](http://ifeve.com/java-threadpool/)
* [聊聊并发（四）深入分析ConcurrentHashMap](http://ifeve.com/concurrenthashmap/)
* [聊聊并发（五）原子操作的实现原理](http://ifeve.com/atomic-operation/)
* [聊聊并发（六）ConcurrentLinkedQueue的实现原理分析](http://ifeve.com/concurrentlinkedqueue/)
* [聊聊并发（七）——Java中的阻塞队列](http://ifeve.com/java-blocking-queue/)
* [聊聊并发（八）——Fork/Join框架介绍](http://ifeve.com/talk-concurrency-forkjoin/)
* [聊聊并发（九）Java中的CopyOnWrite容器](http://ifeve.com/java-copy-on-write/)
* [聊聊并发（十）生产者消费者模式](http://ifeve.com/producers-and-consumers-mode/)
* [非阻塞同步算法实战（一）](http://ifeve.com/no-blicking-do-1/)
* [非阻塞同步算法实战（二）－BoundlessCyclicBarrier](http://ifeve.com/boundlesscyclicbarrier/)
* [非阻塞同步算法实战（三）－LatestResultsProvider](http://ifeve.com/latestresultsprovider/)
* [TimeUnit是java.util.concurrent包下面的一个类，表示给定单元粒度的时间段](https://www.cnblogs.com/zhaoyanjun/p/5486726.html)
* [阿里一道Java并发面试题 (详细分析篇)](https://blog.csdn.net/lirenzuo/article/details/90050894)

* [从0到4000高并发请求背后的努力](http://www.52im.net/thread-2141-1-1.html)
* [解密小米抢购系统千万高并发架构的演进和实践](http://www.52im.net/thread-2323-1-1.html)
* [高并发、高性能 Web 架构](https://blog.csdn.net/qq_26562641/article/details/58597154)
* [究竟啥才是互联网架构“高并发](https://mp.weixin.qq.com/s?__biz=MjM5ODYxMDA5OQ==&mid=2651959830&idx=1&sn=ce1c5a58caed227d7dfdbc16d6e1cea4&chksm=bd2d07ca8a5a8edc45cc45c4787cc72cf4c8b96fb43d2840c7ccd44978036a7d39a03dd578b5&scene=21#wechat_redirect)

* [电商那些年，我摸爬打滚出的高并发架构实战精髓（一）](https://blog.csdn.net/weixin_37288522/article/details/79624235)
* [电商那些年，我摸爬打滚出的高并发架构实战精髓（二）](https://blog.csdn.net/weixin_37288522/article/details/79624228)
* [电商那些年，我摸爬打滚出的高并发架构实战精髓(续)](https://blog.csdn.net/wulantian/article/details/66967807)
* [高并发高可用服务设计思路](https://blog.csdn.net/u013322876/article/details/80605183)
* [关于java高并发设计整合-分布式事务(转发)](https://blog.csdn.net/rainyear/article/details/81294959)
* [Java系统的高并发解决方法详解](https://www.jb51.net/article/124145.htm)
* [Java使用代码模拟高并发操作的示例](https://www.jb51.net/article/139429.htm)
* [什么是高并发 ，详细讲解](https://blog.csdn.net/DreamWeaver_zhou/article/details/78587580)
* [9种高性能高可用高并发的技术架构](https://blog.csdn.net/guolong1983811/article/details/78604814)
* [高并发、高性能 Web 架构](https://blog.csdn.net/qq_26562641/article/details/58597154)
* [Java构建高并发高可用的电商平台架构实践](https://blog.csdn.net/lsm135/article/details/50920483)
* [生产实践总结】支撑百万连接的系统应该如何设计其高并发架构？](https://juejin.im/post/5c7fcf1be51d457d0353d5ea)
* [【高并发优化实践】10倍请求压力来袭，你的系统会被击垮吗？](https://juejin.im/post/5c1baab7e51d455e4b55ff72)
* [设计自己的高并发架构](https://blog.csdn.net/zhangbijun1230/article/details/80714181)


