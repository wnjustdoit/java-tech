# java_tech
Java技术全栈，供学习、交流使用

* [Java技术体系（基础篇）](README.md)
* [Java技术体系进阶（架构篇）](javatech_advanced.md)

## Java技术体系进阶（架构篇）

---
#### 中间件
###### Zookeeper
* zookeeper节点类型，监听事件；
* zookeeper分布式锁；
* 客户端Curator；
* 从paxos到zookeeper，选举策略，原理及使用；
* 拜占庭问题，两将军问题；
* 注册中心，配置中心；

###### 缓存
* 在项目中缓存是如何使用的？缓存如果使用不当会造成什么后果？
* Redis 和 Memcached 有什么区别？Redis 的线程模型是什么？为什么单线程的 Redis 比多线程的 Memcached 效率要高得多？
* Redis 都有哪些数据类型？分别在哪些场景下使用比较合适？
* Redis 的过期策略都有哪些？手写一下 LRU 代码实现？
* 如何保证 Redis 高并发、高可用？Redis 的主从复制原理能介绍一下么？Redis 的哨兵原理能介绍一下么？
* Redis 的持久化有哪几种方式？不同的持久化机制都有什么优缺点？持久化机制具体底层是如何实现的？
* Redis 集群模式的工作原理能说一下么？在集群模式下，Redis 的 key 是如何寻址的？分布式寻址都有哪些算法？了解一致性 hash 算法吗？如何动态增加和删除一个节点？
* 了解什么是 redis 的雪崩、穿透和击穿？Redis 崩溃之后会怎么样？系统该如何应对这种情况？如何处理 Redis 的穿透？
* 如何保证缓存与数据库的双写一致性？
* Redis 的并发竞争问题是什么？如何解决这个问题？了解 Redis 事务的 CAS 方案吗？
* 生产环境中的 Redis 是怎么部署的？
* redis限流、计数器，各个数据结构使用场景，单线程效率高的原因，主从复制原理，持久化两种方式及原理，redis客户端通信协议，cluster原理，key失效策略，秒杀场景的实现，滑动时间窗口；
* redis的key/value最大容纳字节数范围；
* redis key的翻页优化，游标（导致结果不够准确）；
* redis与memcached区别；
* redisson分布式锁；
* RedLock；
* 事务、管道、Lua脚本；

###### 消息队列
* 为什么使用消息队列？消息队列有什么优点（解耦、异步、削峰）和缺点（系统可用性降低、系统复杂性提高、一致性问题）？
* Kafka、ActiveMQ、RabbitMQ、RocketMQ 都有什么优点和缺点？
* 如何保证消息队列的高可用？
* 如何保证消息不被重复消费？（如何保证消息消费的幂等性）
* 如何保证消息的可靠性传输？（如何处理消息丢失的问题）
* 如何保证消息的顺序性？
* 如何解决消息队列的延时以及过期失效问题？消息队列满了以后该怎么处理？有几百万消息持续积压几小时，说说怎么解决？
* 如果让你写一个消息队列，该如何进行架构设计啊？说一下你的思路。
* Kafka性能监测与影响因素；

###### 搜索引擎 & 日志
* es 的分布式架构原理能说一下么（es 是如何实现分布式的啊）？
* es 写入数据的工作原理是什么啊？es 查询数据的工作原理是什么啊？底层的 lucene 介绍一下呗？倒排索引了解吗？
* es 在数据量很大的情况下（数十亿级别）如何提高查询效率啊？
* es 生产集群的部署架构是什么？每个索引的数据量大概有多少？每个索引大概有多少个分片？
* Lucene；
* Elasticsearch，倒排索引，与Solr区别；
* ELK；
* 分词器（IK、MMseg4j）；

###### 配置中心
* DisConf；
* Diamond；
* Spring Cloud Config（基于git）；
* 基于Zookeeper定制；

###### 调度框架
* 基于数据库配置的Quartz（与spring集成）；
* TBSchedule；
* XXL-JOB；
* Elastic-Job；

---
#### 运维
* nginx、tomcat等获取真实ip（IPv4、IPv6）；
* 优化nginx、tomcat、jvm、mysql；
* Nginx限流（OpenResty、Lua）、反向代理、黑白名单、负载均衡（算法）、keepalived；
* 负载均衡（客户端/服务端，软/硬），SLB、LVS、F5；
* 性能基准；
* 基准测试；
* 服务器时钟同步；
* 日志（日志脱敏、logback）；
* 网站安全；
    * XSS
        * XSS 的防御
    * CSRF
    * 注入攻击
        * SQL 注入、XML 注入、CRLF 注入
    * 文件上传漏洞
    * 加密与解密
        * 对称加密、非对称加密、哈希算法、加盐哈希算法；
        * MD5，SHA1、DES、AES、RSA、DSA；
        * 彩虹表
    * DDOS 攻击
        * DOS 攻击、DDOS 攻击；
        * memcached为什么可以导致DDos攻击、什么是反射型DDoS；
        * 如何通过Hash碰撞进行DOS攻击 
        * CC攻击
    * SSL、TLS，HTTPS
    * 用openssl签一个证书部署到Apache或Nginx或Tomcat
* 限流，降级，压测，并发，吞吐率；
* 网关系统；
* 监控系统；
* 全链路日志跟踪；
    * Google Dapper；
    * skywalking；
* DevOps；
* 持续集成CI，集成测试；

---
#### 架构
* SDN；
* 数据中台，中台化；
* 去中心化；
* 架构类型：业务架构/系统架构、应用架构、技术架构；
* 业务类型：2B、2C；
* 模块化（OSGI），服务化（以及平台化、中台化）；
* MVC；
* DDD（建模，领域驱动设计）；
* 重构（持续重构）；
* 设计模式；
* SPI（JNDI、JDBC，违背双亲委派模型）；
* AOP；
* TDD（测试驱动开发）；
* NoSQL；
* Akka；
* Docker & Kubernetes；
* Paas、Saas、Iaas；
* 缓存策略（LRU、）；
* 分布式全局唯一ID（UUID、twitter的snowflake）；
* 单点登录SSO、OAUTH2、CAS，集中式会话管理；
* RBAC 权限设计；
* 滑动时间窗口；
* 乐观锁（CAS 自旋）、悲观锁；
* 事务，减库存；
* 分布式（数据一致性、服务治理、服务降级）；
    * 分布式事务；
        * XA、2PC、3PC、CAP、BASE、可靠消息最终一致性、最大努力通知、TCC、DTS，事务补偿机制，最终一致性，本地事务表，事务消息，柔性事务；
        * 幂等性；
    * Dubbo；
        * 服务注册与发现，服务治理，http://dubbo.apache.org/zh-cn/
        * 说一下的 dubbo 的工作原理？注册中心挂了可以继续通信吗？
        * dubbo 支持哪些序列化协议？说一下 hessian 的数据结构？PB 知道吗？为什么 PB 的效率是最高的？
        * dubbo 负载均衡策略和高可用策略都有哪些？动态代理策略呢？
        * dubbo 的 spi 思想是什么？
        * 如何基于 dubbo 进行服务治理、服务降级、失败重试以及超时重试？
        * 分布式服务接口的幂等性如何设计（比如不能重复扣款）？
        * 分布式服务接口请求的顺序性如何保证？
        * 如何自己设计一个类似 dubbo 的 rpc 框架？
    * 分布式数据库；
        * 怎样打造一个分布式数据库、什么时候需要分布式数据库、mycat、otter、HBase；
    * 分布式文件系统；
        * mfs、fastDFS；
    * 分布式缓存；
        * 缓存一致性、缓存命中率、缓存冗余、缓存穿透、多级缓存；
    * 服务熔断、限流降级；
        * Hystrix、Sentinel；
    * 算法；
        * 共识算法、Raft协议、Paxos算法与Raft算法、拜占庭问题与算法、2PC、3PC；
* RPC；
    * Thrift；
    * protobuf 序列化；
    * 序列化协议（hessian），RPC协议，跨语言，RPC的超时判断；
    * webservice/rmi、soa、soap、REST；
    * gRPC;
* 微服务（SOA、康威定律）；
    * Spring Boot；
    * Spring Cloud；
    * ServiceMesh；
        * sidecar；
    * Dubbo；
* 高并发；
    * 分库分表；
        * 为什么要分库分表（设计高并发系统的时候，数据库层面该如何设计）？用过哪些分库分表中间件？不同的分库分表中间件都有什么优点和缺点？你们具体是如何对数据库如何进行垂直拆分或水平拆分的？
        * 现在有一个未分库分表的系统，未来要分库分表，如何设计才可以让系统从未分库分表动态切换到分库分表上？
        * 如何设计可以动态扩容缩容的分库分表方案？
        * 分库分表之后，id 主键如何处理？
    * 读写分离；
        * 如何实现 MySQL 的读写分离？MySQL 主从复制原理是啥？如何解决 MySQL 主从同步的延时问题？
    * CDN技术；
    * 消息队列；
    * 如何设计一个高并发系统？
* 监控；
    * 监控什么；
        * CPU、内存、磁盘I/O、网络I/O等 ；
    * 监控手段；
        * 进程监控、语义监控、机器资源监控、数据波动；
    * 监控数据采集；
        * 日志、埋点；
    * Google Dapper；
    * open-falcon；
    * pinpoint；
    * 大众点评cat；
* 负载均衡SLB；
    * tomcat负载均衡、Nginx负载均衡；
    * 四层负载均衡、七层负载均衡；
* DNS；
    * DNS原理、DNS的设计；
* CDN；
    * 数据一致性；

---
#### 性能优化
* 使用单例、使用 Future 模式、使用线程池；
* 选择就绪、减少上下文切换、减少锁粒度、数据压缩、结果缓存；
* 空间换时间；
