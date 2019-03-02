
大家都知道，服务一般分为有状态和无状态，而分布式sessoion就是针对有状态的服务。

## 分布式Session的几种实现方式

  * 基于数据库的Session共享
  * 基于resin/tomcat web容器本身的session复制机制
  * 基于oscache/Redis/memcached 进行 session 共享。
  * 基于cookie 进行session共享

## 分布式Session的几种管理方式

  * Session Replication 方式管理 (即session复制)
    简介：将一台机器上的Session数据广播复制到集群中其余机器上
    使用场景：机器较少，网络流量较小
    优点：实现简单、配置较少、当网络中有机器Down掉时不影响用户访问
    缺点：广播式复制到其余机器有一定廷时，带来一定网络开销
  
  * Session Sticky 方式管理
   简介：即粘性Session、当用户访问集群中某台机器后，强制指定后续所有请求均落到此机器上
   使用场景：机器数适中、对稳定性要求不是非常苛刻
   优点：实现简单、配置方便、没有额外网络开销
   缺点：网络中有机器Down掉时、用户Session会丢失、容易造成单点故障
