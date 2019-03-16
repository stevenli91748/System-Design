
# 目录
  * [负载均衡概述](#负载均衡概述)
  * [Layer 4 load balancing]
  * [Layer 7 load balancing]


## 负载均衡概述

在架构中加入负载均衡系统，负载均衡系统可以使用的位置：可以使用在web应用服务之前，也可用在数据库集群前（如：在MySQL集群中，使用LVS将数据库请求分散到各个从服务器）。
实现方式包括：硬件负载均衡、软件负载均衡。

硬件负载均衡效率高，价格贵，如F5等；

软件负载均衡系统价格低或免费，效率较硬件低，但一般够用，如LVS，nginx也有负载均衡功能。

   
   
   
   # 有用的参考
   
   * [如何打造应对超大流量的高性能负载均衡](https://mp.weixin.qq.com/s?__biz=MzI4NTA1MDEwNg==&mid=2650763691&idx=1&sn=e5f6e863e54b347d431e99dccee1b6be&chksm=f3f9c43ec48e4d28ff6b5cc3a6795db08ba89e6aaf330dba5a09d853ff96e2fc05d31d63ddb4&scene=21#wechat_redirect)
   
   * [一分钟了解负载均衡的一切](https://mp.weixin.qq.com/s?__biz=MjM5ODYxMDA5OQ==&mid=2651959585&idx=1&sn=0a9222cbfeb62a662edffafb7f0b43ae&scene=21#wechat_redirect)
   
   * [lvs为何不能完全替代DNS轮询](https://mp.weixin.qq.com/s?__biz=MjM5ODYxMDA5OQ==&mid=2651959595&idx=1&sn=5f0633afd24c547b895f29f6538baa99&scene=21#wechat_redirect)
   
   * [如何实施异构服务器的负载均衡及过载保护](https://mp.weixin.qq.com/s?__biz=MjM5ODYxMDA5OQ==&mid=2651959601&idx=1&sn=5684c39676b1f6d9366d9d15a2cdcec3&scene=21#wechat_redirect)
