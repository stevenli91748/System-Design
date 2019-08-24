# 软件系统中高性能带来的复杂度主要体现在两方面， 一方面是单台计算机内部为了高性能带来的复杂度：另一方面是多台计算机集群为了高性能带来的复杂度。
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
  * [NoSQL数据库集群](https://github.com/stevenli91748/System-Design/blob/master/High%20performance%20architecture/NoSQL数据库集群.md)
  * [缓存]()
    * 缓存穿透
    * 缓存雪崩
    * 缓存热点

# 计算高性能
  * 单服务器性能
    * PPC
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
