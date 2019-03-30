
# [系统设计面试](https://github.com/stevenli91748/System-Design/blob/master/Interview/README.md)

# 目录

# 1.  System-Design

 ![Imgur](https://i.ibb.co/qRCKVVP/1.jpg)        

# 1.0 软件开发文档模板

# 1.1  系统设计流程
  * 人员安排
      
    * 前端UI效果设计
    * 前端程序员
    * 后端程序员
    * 项目经理
    * 部们经理
      
  * 了解需求
    * 在软件需求了解中的 5W2H 问题
  * 需求分析
  * 文档设计
  * 项目设计
    * 业务流程
    * 前端
    * 数据库
    * 开发总体架构
    * 前端和后端各自局部架构
    * 技术关键点
    * 人员安排和时间点
        
 # 1.2  功能性设计
 
 # 1.3  非功能性设计
 
 系统非功能性设计的6个方向
      
  * 1.1.  [高性能架构](https://github.com/stevenli91748/System-Design/blob/master/High%20performance%20architecture/README.md)
  * 1.2.  [高可用性架构](https://github.com/stevenli91748/System-Design/blob/master/High%20availability%20architecture/README.md)
  * 1.3.  [高伸缩性架构](https://github.com/stevenli91748/System-Design/blob/master/Highly%20scalable%20architecture/README.md)
  * 1.4.  高櫎展性架构
  * 1.5.  高安全性架构
  * 1.6.  [高并发架构](https://github.com/stevenli91748/System-Design/blob/master/High%20concurrency%20architecture/README.md)

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

## 1  [DNS (Domain Name System)  ](https://github.com/stevenli91748/System-Design/blob/master/DNS/README.md)

## 2  [CDN (Content Delivery Network)](https://github.com/stevenli91748/System-Design/blob/master/CDN/README.md)

   * [2.1.  Push CDNs]
   * [2.2.  Pull CDNs]
   
## 3. [API Gateway](https://github.com/stevenli91748/System-Design/blob/master/APIGateWay/README.md)

  
## 4  [负载均衡](https://github.com/stevenli91748/System-Design/blob/master/Load%20%20Balance/README.md)

## 5  [缓存系统](https://github.com/stevenli91748/System-Design/blob/master/Cache/README.md)

  * [5.1.  Client caching]
  * [5.2.  HTTP  Caching]  
    * [HTTP----HTTP缓存机制](https://juejin.im/post/5a1d4e546fb9a0450f21af23)
  * [5.3.  CDN caching]
  * [5.4.  Web server caching ]
  * [5.5.  Database caching]
  * [5.6.  Application caching]
  * [5.7.  Caching at database query level]
  * [5.8.  Caching at object level]
  * [5.9.  When to update the cache]
     * [5.9.1.  Cache aside]
     * [5.9.2.  Write through]
     * [5.9.3.  Write behind]
     * [5.9.4.  Refresh ahead]
  

## 6  [反向代理](https://github.com/stevenli91748/System-Design/blob/master/Reverse%20Proxy/README.md)

## 7  Interface API

  * [7.1.  Writing API]
  * [7.2.  Reading API]
  * [7.3.  Searching API]
  
## 8  Application Layer

  * [8.1.  Microservice]
  * [8.2.  Service Discovery]

## 9  [数据库集群系统](https://github.com/stevenli91748/Database/blob/master/README.md)

  * [9.1. SQL--Relational database management system(RDBMS)]
     * [9.1.1.  Master slave replication]
     * [9.1.2.  Master master replication]
     * [9.1.3.  Federation]
     * [9.1.4.  Sharding]
     * [9.1.5.  Denormalization]
     * [9.1.6.  SQL tuning]
  * [9.2.  NoSQL]
     * [9.2.1.  key-value store]
     * [9.2.2.  Document store]
     * [9.2.3.  Wide column store ]
     * [9.2.4.  Graph database]
     
## 10  异步计算策略

  * [10.1.  消息队列]
  * [10.2.  任务队列]
  * [10.3.  背压机制]

## [11 网络通信](https://github.com/stevenli91748/Network/blob/master/README.md)

## 12 数据交互
  * json
  * XML
  * Google Protocol Buffer

## 12 分布式存储系统

## 13 Security

## 14 系统集群

集群主要分成三大类( 高可用集群， 负载均衡集群，科学计算集群)

* [高可用集群]()
  
* [负载均衡集群]()
  * [DNS负载均衡]()
  * 四层负载均衡(F5、LVS)工作在TCP协议下
  * 七层负载均衡(Nginx、haproxy)工作在Http协议下
  
* [科学计算集群]()

## [15 分布式session](https://github.com/stevenli91748/System-Design/blob/master/Session/README.md)



# 内容


# 参考书籍

 * 人人都是架构师  分布式系统架构落地与瓶颈突破
 * 大型网站技术核心原理与案例分析
 * 架构解密.从分布式到微服务
 * 亿级流量网站架构核心技术+跟开涛学搭建高可用高并发系统
 * [大型网站架构系列：20本技术书籍推荐](https://blog.csdn.net/zdy0_2004/article/details/50513152)
# 有用的参考
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
  
 ### 大型网站架构 
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















