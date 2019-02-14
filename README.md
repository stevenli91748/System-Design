
# [系统设计面试](https://github.com/stevenli91748/System-Design/blob/master/Interview.md)

# 目录

# 1.  System-Design

  系统设计的6个方向
      
 * 1.1.  高性能架构
 * 1.2.  高可用性架构
 * 1.3.  高伸缩性架构
 * 1.4.  高櫎展性架构
 * 1.5.  高安全性架构
 * 1.6.  高并发架构

# [2.  分布式系统](https://github.com/stevenli91748/Distributed-System)

# [3.  微服务系统](https://github.com/stevenli91748/MicroService)

# 4.  系统架构层次结构

## 采用RESTful API 技术
<p align="center">
  <img src="http://i.imgur.com/jj3A5N8.png">
  <br/>
</p>

---
## 采用微服务技术 + RESTful API 技术

![Imgur](http://i.imgur.com/jrUBAF7.png)

## 1  DNS (Domain Name System)  

## 2  CDN (Content Delivery Network)

   * [2.1.  Push CDNs]
   * [2.2.  Pull CDNs]
   
## 3  Load Balancer

   * [3.5.  Layer 4 load balancing]
   * [3.6.  Layer 7 load balancing]

## 4  Cache

  * [4.1.  Client caching]
  * [4.2.  HTTP  Caching]  
  * [4.3.  CDN caching]
  * [4.4.  Web server caching ]
  * [4.5.  Database caching]
  * [4.6.  Application caching]
  * [4.7.  Caching at database query level]
  * [4.8.  Caching at object level]
  * [4.9.  When to update the cache]
     * [4.9.1.  Cache aside]
     * [4.9.2.  Write through]
     * [4.9.3.  Write behind]
     * [4.9.4.  Refresh ahead]
  

## 5  反向代理

## 6  Interface API

  * [6.1.  Writing API]
  * [6.2.  Reading API]
  * [6.3.  Searching API]
  
## 7  Application Layer

  * [7.1.  Microservice]
  * [7.2.  Service Discovery]

## 8  Database

  * [8.1. SQL--Relational database management system(RDBMS)]
     * [8.1.1.  Master slave replication]
     * [8.1.2.  Master master replication]
     * [8.1.3.  Federation]
     * [8.1.4.  Sharding]
     * [8.1.5.  Denormalization]
     * [8.1.6.  SQL tuning]
  * [8.2.  NoSQL]
     * [8.2.1.  key-value store]
     * [8.2.2.  Document store]
     * [8.2.3.  Wide column store ]
     * [8.2.4.  Graph database]
     
## 9  异步

  * [9.1.  消息队列]
  * [9.2.  任务队列]
  * [9.3.  背压机制]

## 10 通信

  * [10.1.  传输控制协议（TCP）]
  * [10.2.  用户数据报协议（UDP）]
  * [10.3.  远程过程调用协议（RPC]
  * [10.4.  表述性状态转移（REST]
    

## 11 Security

# 参考书籍

 * 人人都是架构师  分布式系统架构落地与瓶颈突破
 * 大型网站技术核心原理与案例分析
 * 架构解密.从分布式到微服务
 * 亿级流量网站架构核心技术+跟开涛学搭建高可用高并发系统
 
# 有用的参考

  * [Java系统的高并发解决方法详解](https://www.jb51.net/article/124145.htm)
  * [Java使用代码模拟高并发操作的示例](https://www.jb51.net/article/139429.htm)
  * [什么是高并发 ，详细讲解](https://blog.csdn.net/DreamWeaver_zhou/article/details/78587580)
  * [9种高性能高可用高并发的技术架构](https://blog.csdn.net/guolong1983811/article/details/78604814)
  * [高并发、高性能 Web 架构](https://blog.csdn.net/qq_26562641/article/details/58597154)
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
  
 ### 大型网站架构 
  * [从 0 到 1，Java Web 网站架构搭建的技术演进](https://blog.csdn.net/qq_40267706/article/details/78628352)
  * [1千用户与1千万用户的网站系统架构区别？](https://blog.csdn.net/zqftisson/article/details/51777042)
  * [Java构建高并发高可用的电商平台架构实践](https://blog.csdn.net/lsm135/article/details/50920483)
  * [大型分布式电商系统架构是如何从0开始演进的？](https://blog.csdn.net/jianai0602/article/details/80346837)
  * [电商系统学习笔记之一系统架构](https://blog.csdn.net/hanruikai/article/details/79928211)
  * [百万级别网站架构思路](https://blog.csdn.net/ahjxhy2010/article/details/79854980)
  * [大型电商网站千万级别架构案例和技术架构【推荐】](https://blog.csdn.net/jianai0602/article/details/80346837)
  * [结合实例谈项目架构设计](https://blog.csdn.net/javayujiafeng/article/details/79086710)
  * []()
  
