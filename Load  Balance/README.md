
# 目录
  
  * [负载均衡概述](#负载均衡概述)
  * [负载均衡集群的复杂度](#负载均衡集群的复杂度)
  * [负载均衡系统分类](#负载均衡系统分类)
    * DNS域名解析负载均衡---一般用来实现地理级别的均衡

    * 硬件负载均衡---硬件负载均衡用于实现集群级别的负载均衡
      * F5
    
    * 软件负载均衡---软件负载均衡用于实现机器级别的负载均衡。
      * HTTP重定向负载均衡
      * 反向代理负载均衡
      * LVS负载均衡---LVS 是最流行的四层负载均衡软件
      * HAProxy负载均衡---HAProxy可是另一个既支持四层又支持七层负载均衡的软件
      * Nginx负载均衡---Nginx 则是七层负载均衡最流行的解决方案
      * IP负载均衡
      * 数据链路层负载均衡
      
      
  * [负载均衡架构](#负载均衡架构)
  
    * 地理级别的均衡
    * 集群级别的负载均衡
    * 机器级别的负载均衡
  
  * [负载均衡算法](#负载均衡算法)
    * 任务平分类算法
    * 负载均衡类算法
    * 性能最优类算法
    * Hash 类算法
    * 轮询算法
    * 按权重分配算法
    * 按照负载进行分配算法(如果按照服务器的负载进行分配，则业务服务器还要能够上报自己的状态给任务分配器)
    
  * 负载均衡服务器和业务服务器之间连接和交互
    * 连接建立
    * 连接检测
    * 连接中断后的处理
    

## 负载均衡概述

在运算系统集群 或 存储系统集群 或 缓存系统集群都要用到负载均衡

在架构中加入负载均衡系统，负载均衡系统可以使用的位置：可以使用在web应用服务之前，也可用在数据库集群前（如：在MySQL集群中，使用LVS将数据库请求分散到各个从服务器）。


## 负载均衡集群的复杂度

   **单个任务负载均衡分配器复杂度     **

   <a href="https://ibb.co/F0cP8VQ"><img src="https://i.ibb.co/nn4WQCX/2018-09-01-3.png" alt="2018-09-01-3" border="0"></a>


   **N个任务负载均衡分配器的复杂度**

   <a href="https://ibb.co/VSsDXpY"><img src="https://i.ibb.co/Z80Ky1z/1-2018-09-01-2.png" alt="1-2018-09-01-2" border="0"></a>

   
## 负载均衡系统分类

## 负载均衡架构

## 负载均衡算法




---

# 有用的参考
   
   * 实用负载均衡技术网站性能优化攻略.pdf
   
   * [快速理解高性能HTTP服务端的负载均衡技术原理](http://www.52im.net/thread-1950-1-1.html)
   
   * [如何打造应对超大流量的高性能负载均衡](https://mp.weixin.qq.com/s?__biz=MzI4NTA1MDEwNg==&mid=2650763691&idx=1&sn=e5f6e863e54b347d431e99dccee1b6be&chksm=f3f9c43ec48e4d28ff6b5cc3a6795db08ba89e6aaf330dba5a09d853ff96e2fc05d31d63ddb4&scene=21#wechat_redirect)
   
   * [一分钟了解负载均衡的一切](https://mp.weixin.qq.com/s?__biz=MjM5ODYxMDA5OQ==&mid=2651959585&idx=1&sn=0a9222cbfeb62a662edffafb7f0b43ae&scene=21#wechat_redirect)
   
   * [lvs为何不能完全替代DNS轮询](https://mp.weixin.qq.com/s?__biz=MjM5ODYxMDA5OQ==&mid=2651959595&idx=1&sn=5f0633afd24c547b895f29f6538baa99&scene=21#wechat_redirect)
   
   * [如何实施异构服务器的负载均衡及过载保护](https://mp.weixin.qq.com/s?__biz=MjM5ODYxMDA5OQ==&mid=2651959601&idx=1&sn=5684c39676b1f6d9366d9d15a2cdcec3&scene=21#wechat_redirect)
