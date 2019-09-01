* [高可用架构理论](#高可用架构理论)
  * [CAP定理](#CAP定理)---从理论上论证了存储高可用的复杂度。
    * [Consistency](#Consistency)(一致性)
    * [Availability](#Availability)(可用性)
    * [Partition Tolerance](#Partition-Tolerance)(分区容错性)
  * FMEA定理
  * 可用性的度量
* 高可用架构  
* 业务高可用---高可用的应用
  * 异地多活
  * 接口级的故障应对方案
    * 降级
    * 熔断
    * 限流
    * 排队
* 存储高可用---高可用的数据
  * 主备复制
  * 主从复制
  * 主主复制
  * 主备倒换与主从倒换
  * 数据集群
    * 数据集中集群
    * 数据分布集群
    * 分布式事务算法
    * 分布式一致性算法
  * 数据分区
* 计算高可用---高可用的服务
  * 计算高可用复杂度
  * 高可用双机调度算法
  * 主主  
  * 主备
    * 热备
    * 温备
    * 冷备
  * 主从
  * 对称集群
  * 非对称集群
 
 --- 
# 高可用架构理论

## CAP定理
      
      对于设计分布式系统的架构师来说， CAP 是必须掌握的理论。
      
      前后有两版的CAP定理：
      
      第一版：
      
          any distibuted system cannot guaranty C, A, and P simu ltaneously 。
          简单翻译为： 对于一个分布式计算系统，不可能同时满足一致性（ Consistence ）、可用性(Availability ）、分区容错性（ 
          Partition Tolerance ）三个设计约束。
          
      第二版：
     
          in a distibuted system (a collection of inteconnected nodes that shae data.), you can only have
          two out of the following thee guaantees acoss a wite/read pai： Co1sistency, Availability, and
          Patition Toleance - one of them must be sacrificed 。

          简单翻译为：在一个分布式系统（ 指互相连接并共享数据的节点的集合）中，当涉及读写操作时，只能保证一致性（ Consistence ）、可用性
          （ Availability ）、分区容错性（ Partition Tolerance)三者中的两个，另外一个必须被牺牲。     
          
      前后有两版的差异点：
      
           (1）第二版定义了什么才是CAP 理论探讨的分布式系统，强调了两点： interconnected 和share data ，为何要强调这两点呢？ 因为分布式系统并
               不一定会互联和共享数据。最简单的例如Memcache 的集群，相互之间就没有连接和共享数据，因此Memcache 集群这类分布式系统就不符合CAP 理
               论探讨的对象；而MySQL 集群就是互联和进行数据复制的，因此是CAP 理论探讨的对象。
               
           (2）第二版强调了write / read pair ，这点其实和第1 条差异点是一脉相承的。也就是说，CAP 关注的是对数据的读写操作，而不是分布式系统的所
               有功能。例如， ZooKeeper 的选举机制就不是CAP 探讨的对象。
      
       相比来说，第二版的定义更加精确。

## Consistency
## Availability
## Partition Tolerance

# 有用的参考

* 从零开始学架构：照着做，你也能成为架构师.pdf
* 从零开始学架构--系列文集（李运华）.pdf
* 大型网站技术核心原理与案例分析.pdf
* 软件架构设计：大型网站技术架构与业务架构融合之道.pdf
* 亿级流量网站架构核心技术+跟开涛学搭建高可用高并发系统.pdf
* 高可用架构.pdf
* 可伸缩架构-面向增长应用的高可用.pdf


 * [究竟啥才是互联网架构“高可用](https://mp.weixin.qq.com/s?__biz=MjM5ODYxMDA5OQ==&mid=2651959728&idx=1&sn=933227840ec8cdc35d3a33ae3fe97ec5&chksm=bd2d046c8a5a8d7a13551124af36bedf68f7a6e31f6f32828678d2adb108b86b7e08c678f22f&scene=21#wechat_redirect)
 
 * [高可用架构详解](https://blog.csdn.net/wuxing26jiayou/article/details/54584906)
