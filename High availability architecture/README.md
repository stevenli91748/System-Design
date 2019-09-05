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
      
      CAP 理论告诉我们分布式系统只能选择CP 或AP ，但其实这里的前提是系统发生了“分区”
      
      虽然CAP 理论定义是三个要素中只能取两个，但放到分布式环境下来思考，我们必须要首先考虑系统是否会发生了“分区”现象（节点间的网络连接一切正常），也
      就是说CAP中P是重点，有两种情况：
      
      1. 没有分区现象
         如果系统没有发生分区现象，也就是说P 不存在的时候（节点间的网络连接一切正常），我们没有必要放弃C 或A，应该C 和A 都可以保证，这就要求架构
         设计的时候既要考虑分区发生时选择CP 还是AP ，也要考虑分区没有发生时如何保证CA 。

      2. 有分区现象
      
         因为网络本身无法做到100%可靠，有可能出故障，所以分区是一个必然的现象。如果我们选择了CA 而放弃了P，那么当发生分区现象时，为了保证C ，系统需
         要禁止写入，当有写入请求时，系统返回 error （例如，当前系统不允许写入），这又和A 冲突了，因为A 要求返回no eηor 和no timeout。因此，分布式
         系统理论上不可能选择CA 架构，只能选择CP 或AP 架构。
      
      
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
   
    第一版解释：
    
    所有节点在同一时刻都能看到相同的数据。

    第二版解释：

    对某个指定的客户端来说，读操作保证能够返回最新的写操作结果
    
    第一版解释和第二版解释的主要差异点表现在以下几个方面：
    
    • 第一版从节点node 的角度描述，第二版从客户端client 的角度描述。相比来说，第二版更加符合我们观察和评估系统的方式，即站在客户端的角度来观
      察系统的行为和特征。
    • 第一版的关键词是see ，第二版的关键词是read 。第一版解释中的see ，其实并不确切，因为节点node 是拥有数据，而不是看到数据，即
      使要描述也是用have ；第二版从客户端client 的读写角度来描述一致性，定义更加精确。
    • 第一版强调同一时刻拥有相同数据（ same time + same data ），第二版并没有强调这点。这就意味着实际上对于节点来说，可能同一时刻拥有不同数
      据（ same time + different data ） ，这和我们通常理解的一致性是有差异的，

    对于系统执行事务来说，在事务执行过程中，系统其实处于一个不一致的状态，不同的节点的数据并不完全一致。因此第一版的解释“ All nodes see the 
    same data at thesame time ，， 是不严谨的，而第二版强调client 读操作能够获取最新的写结果就没有问题。因为事务在执行过程中， client 是无
    法读取到未提交的数据的， 只有等到事务提交后， client 才能读取到事务写入的数据，而如果事务失败则会进行回滚， client 也不会读取到事务中间
    写入的数据。
    
    
## Availability

     非故障的节点在合理的时间内返回合理的响应（ 不是错误和超时的响应〉
     
     
## Partition Tolerance

    第一版解释：
       尽管出现消息丢失或分区错误，但系统能够继续运行。
    
    第二版解释：
    
       当出现网络分区后，系统能够继续“ 履行职责”。
       
    第一版解释和第二版解释主要差异点表现在以下几个方面
    
    • 第一版用的是work ， 第二版用的是“nction 。work 强调“运行”，只要系统不窑机，我们都可以说系统在work：返回错误也是work,拒绝服务也是work ；
      而function 强调“发挥作用”“ 履行职责飞这点和可用性是一脉相承的。也就是说，只有返回reasonable response 才是“nction o 相比之下，第二版
      解释更加明确。
    • 第一版描述分区用的是message loss or partial failure ，第二版直接用network partitions 。相比之下，第一版是直接说原因，即message loss 
      造成了分区，但message loss 的定义有点狭隘，因为通常我们说的message loss （丢包），只是网络故障中的一种；第二版直接说现象，即发生了分区现
      象，不管是什么原因，可能是丢包，也可能是连接中断，还可能是拥塞，只要导致了网络分区，就通通算在里面。
       
       
       


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
