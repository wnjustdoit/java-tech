# java_tech
Java技术全栈，供学习、交流使用

* [Java技术体系（基础篇）](README.md)
* [Java技术体系进阶（架构篇）](javatech_advanced.md)

## Java技术体系（基础篇）

---
#### 计算机基础
* 二进制、按位运算；
* 字节（8个二进制位）、进制转化、字符、ASCII码、GB2312、UNICODE编码、UTF-8（1-6位）、GBK；
* 编码方式；
    * Unicode、有了 Unicode 为啥还需要 UTF-8；
    * GBK、GB2312、GB18030 之间的区别；
    * UTF8、UTF16、UTF32 区别；
    * URL 编解码、Big Endian 和 Little Endian；
    * 如何解决乱码问题；

---
#### Java基础
* 面向对象编程（Object Oriented Programming，OOP，与面向过程的区别，三大基本特征和五大基本原则，高内聚低耦合）；
* 封装、继承、多态。方法重写与重载。继承与组合。
* 平台无关性，Jvm支持的其他语言（Kotlin、Groovy、JRuby、Jython、Scala等）；
* Java中线程调度算法（抢占式）；
* ClassLoader、类加载过程、双亲委派（破坏双亲委派）、模块化（jboss modules、osgi、jigsaw）；
* 编译与反编译；
    * 什么是编译（前端编译 .java -> .class、后端编译 .class -> 机器码）、什么是反编译；
    * JIT、JIT优化（逃逸分析、栈上分配、标量替换、锁优化）；
    * 编译工具：javac；
    * 反编译工具：javap、jd-gui、jad、CFR、Procyon；
    * 编译过程：词法分析，语法分析（LL算法，递归下降算法，LR算法）、语义分析，运行时环境，中间代码，代码生成，代码优化；
* JVM；
    * 字节码、class文件格式；
    * JVM内存结构
        * 运行时数据区：堆、栈、方法区、直接内存、运行时常量池、堆和栈区别；
        * Java中的对象一定在堆上分配吗？
    * Java内存模型
        * 计算机内存模型、缓存一致性、MESI协议；
        * 可见性、原子性、顺序性、happens-before、内存屏障、synchronized、volatile、final、锁
    * 垃圾回收
        * GC算法：引用计数、标记清除、复制、标记压缩/整理、分代回收、增量式回收；
        * GC参数、对象存活的判定、垃圾收集器（CMS、G1、ZGC、Epsilon）
    * JVM参数及调优
        * -Xmx、-Xmn、-Xms、Xss、-XX:SurvivorRatio、-XX:PermSize、-XX:MaxPermSize、-XX:MaxTenuringThreshold
    * Java对象模型
        * oop-klass、对象头；
    * HotSpot
        * 即时编译器、编译优化；
    * 虚拟机性能监控与故障处理工具
        * javap、jps、jinfo、jstack、jmap、jstat、jconsole、jvisualvm（BTrace插件）、jmc、jhat、第三方（JProfiler、TProfiler、Arthas）；
* 静态变量 -> 静态代码块 -> 普通变量 -> 普通代码块 -> 构造函数（初始化顺序；1、类加载时初始化静态变量和静态代码块，2、有父类时先初始化父类变量和构造函数）；
* 什么是序列化与反序列化、为什么序列化、序列化底层原理、序列化与单例模式、为什么说序列化并不安全；
* 反射相关：
    * Java反射的3种方式（实例对象.getClass()；ClassType.class；Class.forName(className)），访问私有方法method.setAccessible(true)；
    * 反射与工厂模式、反射有什么用；
    * Class类、java.lang.reflect.*；
    * 静态代理和动态代理；
    * 动态代理和反射的关系；
    * 动态代理的几种实现方式（jdk、cglib、javassit）；
    * AOP；
* 元注解、自定义注解、Java中常用注解使用、注解与反射的结合；
* 值传递和引用传递；
* 接口与抽象类的区别，继承与组合的优劣；
* 八种基本数据类型，占用字节数，取值范围；
* 基本类型与包装类型，自动拆装箱（NPE问题，==和equals比较相同问题）；
* Integer的缓存机制；
* 浮点类型的单精度和双精度，浮点类型不精确的原因，怎么正确表达金额（BigDecimal）；
* Long/Double在32位和64位系统的差别；
* String类：
    * 字符串的不可变性；
    * JDK6和JDK7中substring的原理及区别；
    * replaceFirst、replaceAll、replace 区别；
    * String 对“+”的重载、字符串拼接的几种方式和区别；
    * String.valueOf和Integer.toString的区别；
    * switch对String的支持；
    * 字符串池、常量池（运行时常量池、Class常量池）、intern；
* Enum类；
    * 枚举的用法、枚举的实现、枚举与单例；
    * Java枚举如何比较；
    * switch对枚举的支持；
    * 枚举的序列化如何实现；
    * 枚举的线程安全性问题；
* 泛型；
    * 泛型与继承、类型擦除、泛型中 KTVE? object 等的含义、泛型各种用法；
    * 限定通配符和非限定通配符、上下界限定符 extends 和 super；
    * List<Object> 和原始类型 List 之间的区别? 
    * List<?> 和 List<Object> 之间的区别是什么?
* Java中的关键字：transient、instanceof、final、static、volatile、synchronized、const的原理及用法；
* Object顶级类有哪几个方法（另equals与hashcode）；
* 并发编程；
    * 什么是并发、什么是并行、并发与并行的区别；
    * 什么是线程、什么是进程、线程与进程的区别；
    * 线程的实现、线程的状态、优先级、线程调度、创建线程的多种方式（Thread、Runnable、Callable）、守护线程；
    * 线程池，自己设计线程池、submit() 和 execute()、线程池原理、为什么不允许使用 Executors 创建线程池；
    * 线程安全，死锁、死锁如何排查、线程安全和内存模型的关系；
    * 锁，CAS、乐观锁与悲观锁、数据库相关锁机制、分布式锁、偏向锁、轻量级锁、重量级锁、monitor、锁优化、锁消除、锁粗化、自旋锁、可重入锁、阻塞锁、死锁；
    * 死锁，什么是死锁、 死锁如何解决；
    * synchronized；
        * synchronized 是如何实现的？
        * synchronized 和 lock 之间关系、不使用 synchronized 如何实现一个线程安全的单例；
        * synchronized 和原子性、可见性和有序性之间的关系
    * volatile；
        * happens-before、内存屏障、编译器指令重排和 CPU 指令重排序；
        * volatile 的实现原理；
        * volatile 和原子性、可见性和有序性之间的关系；
        * 有了 synchronized 为什么还需要 volatile；
    * 线程的各个状态以及转化，如何中断/终止一个线程（什么状态下），线程A/B并行执行，串行结束怎么实现（join、yield）；
    * sleep 和 wait（对应于Condition、AQS的方法）；
    * wait 和 notify；
    * notify 和 notifyAll；
    * Unsafe 类；
    * ThreadLocal 的原理；
    * 写一个死锁的程序；
    * 写代码来解决生产者消费者问题；
    * JUC（java.util.concurrent）并发包下常用类的实现，如：AbstractQueuedSynchronizer、ConcurrentHashMap、Semaphore、CyclicBarrier、CountDownLaunch、BlockingQueue的子类、Lock的子类、原子类（CAS/ABA）、Executors、AtomicLong与LongAdder等；
* Jdk的定时器Timer以及超时机制（wait/notify，Condition/Lock，轮询）；
* Runtime.addShutdownHook()使用场景；
* Java的集合框架（ArrayList 和 LinkedList 和 Vector 的区别 、SynchronizedList 和 Vector 的区别、HashMap、HashTable、ConcurrentHashMap区别、Set 和 List 区别？Set 如何保证元素不重复？）；
* Java 8 中 stream 相关用法、apache 集合处理工具类的使用、不同版本的 JDK 中 HashMap 的实现的区别以及原因；
* Collection 和 Collections 区别；
* Arrays.asList 获得的 List 使用时需要注意什么；
* Enumeration 和 Iterator 区别；
* fail-fast 和 fail-safe；
* CopyOnWriteArrayList、ConcurrentSkipListMap；
* 数据结构（二叉树、跳表）和算法（算法复杂度，递归，冒泡、快排、二分）；
* TreeMap（红黑树）和LinkedHashMap（最简单的lru缓存淘汰实现）的有序性；
* （伪）随机数的生成（Random、ThreadLocalRandom、SecureRandom）；
* Jdk 的 MD5 算法，Jdk 生成 UUID（Universally Unique Identifier）；
* 正则表达式，java.lang.util.regex.*；
* 字符流、字节流、输入流、输出流；
* 什么是 Java 消息服务、JMS 消息传送模型；
* 什么是 JMX、java.lang.management.*、javax.management.*；
* 时间的本质；
    * 时区、冬令时和夏令时、时间戳、Java 中时间 API；
    * 格林威治时间、CET,UTC,GMT,CST 几种常见时间的含义和关系；
    * SimpleDateFormat 的线程安全性问题（用java8的DateTimeFormatter替换）；
    * Java8中的时间处理（Instant替换Date，LocalDateTime替换Calendar）；
    * 如何在东八区的计算机上获取美国时间；
* 源码阅读；
    * String、Integer、Long、Enum；
    * BigDecimal、ThreadLocal、ClassLoader & URLClassLoader；
    * ArrayList & LinkedList；
    * HashMap & LinkedHashMap & TreeMap & ConcurrentHashMap、HashSet & LinkedHashSet & TreeSet；

#### Web基础
* Servlet；
    * Servlet的生命周期、工作原理；
    * Servlet线程安全问题；
    * web.xml中常用配置及作用（执行顺序：context-param -> listener -> filter -> servlet）；
    * Servlet获取路径的方式（HttpServletRequest），一般java程序获取文件路径的方式（ClassLoader）；
    
* Hibernate；
    * 什么是 OR Mapping
    * Hibernate 的懒加载
    * Hibernate 的缓存机制
    * Hibernate/Ibatis/MyBatis之间的区别
    
* MyBatis；
    * MyBatis实现分表（动态SQL，取模）；
    * MyBatis的实现机制、缓存机制（多级缓存）；
    
* JPA；
    
* Spring体系；
    * Spring AOP的实现原理；
    * Spring IOC（变量/构造函数/set方法，xml配置时为：构造函数/set方法/静态工程/实例工厂）、
    * Spring 对缓存抽象；
    * Spring 的事务管理（with MyBatis、JdbcTemplate）；
    * Spring 注解的应用和实现；
    * Spring MVC参数绑定；
    * Spring Bean的生命周期（bean的管理，尤其是初始化一系列动作）；
    * Spring 与设计模式；
    * Spring 一些注解@Async（ThreadPoolTaskExecutor），@Conditional；
    * Spring 随时获取request、session；
    * 自定义注解，与AOP；
    * Spring Bean等缓存机制；
    * Spring MVC，什么是MVC，与struts MVC的区别；
    * Spring Boot，运行机制（起步依赖、自动配置，starter 原理，自己实现一个 starter）；
    * Spring Cloud栈；
        * 服务发现与注册：Eureka、Zookeeper、Consul
        * 负载均衡：Feign、Spring Cloud Loadbalance
        * 服务配置：Spring Cloud Config
        * 服务限流与熔断：Hystrix
        * 服务链路追踪：Sleuth + Zipkin
        * 服务网关（Spring Cloud Gateway）、安全、消息
    * 其他Spring子项目：spring-data-redis、spring-session、spring-security、spring-kafka；
    
* Web服务器
    * Nginx；
        * Nginx的负载均衡器KeepAlived；
    * Apache（for php）；
    
* 应用服务器；
    * Tomcat、Jetty、JBoss、WebLogic
    * Jetty工作原理，Apj协议，tomcat工作原理，与设计模式；
    * Tomcat和Jetty的IO模型（reactor）；
    * Tomcat和Jetty的类加载异同；

---
#### 网络编程
* tcp、udp、http、https等常用协议；
    * 三次握手与四次关闭、流量控制和拥塞控制、OSI七层模型、tcp粘包与拆包；
    * WebSocket主动推送；
    * TCPdump工具；

* http/1.0 http/1.1 http/2 之前的区别；
    * http中get和post区别
    * 常见的web请求返回的状态码
    * 404、302、301、500分别代表什么
    * http 301（永久重定向，推荐）、302（临时重定向，可能url劫持）状态码的含义；

* http/3
* Java RMI，Socket，HttpClient；
* Cookie与Session
    * Cookie被禁用，如何实现Session

* 用Java写一个简单的静态文件的HTTP服务器；
* 了解Nginx和Apache服务器的特性并搭建一个对应的服务器；
* 用Java实现FTP、SMTP协议；
* 进程间通讯的方式；
* 什么是 CDN？如果实现？
* DNS
    * 什么是DNS 、记录类型: A记录、CNAME记录、AAAA记录等；
    * 域名解析、根域名服务器；
    * DNS污染、DNS劫持、公共DNS：114 DNS、Google DNS、OpenDNS；

* 反向代理
    * 正向代理、反向代理
    * 反向代理服务器
    
* BIO、NIO和AIO的区别、三种IO的用法与原理，NETTY、MINA；

---
#### 数据库
###### MySQL
* 连接；
    * 内连接，左连接，右连接；
* mysql索引类型（主键索引、普通索引、前缀索引、唯一索引、复合/联合/组合索引、全文索引）、索引的数据结构及原理；
    * Hash索引、B树索引（B+树、和B树、R树）；
    * 普通索引、唯一索引；
    * 前缀索引，索引的选择性count(distinct left(column, 4))/count(*) >= 80%；
    * 覆盖索引（逻辑）、最左前缀原则、索引下推；
    * 聚簇索引、非聚簇索引（聚集索引、非聚集索引）
* mysql存储引擎（MYISAM & INNODB）及区别；
* 数据库事务
    * 4个特征ACID；
    * 4类隔离级别；
    * 隔离级别与3个问题；
    * 事务能不能实现锁的功能；
* mysql的锁；
    * 乐观锁：版本号或其他不可逆唯一性列；
    * 悲观锁：共享锁、排它锁、行锁、表锁；
    * 使用数据库锁实现乐观锁；
    * 使用数据库锁实现分布式锁；
    * MVCC，与隔离级别；
    * > 查询全局等待事务锁超时时间 SHOW GLOBAL VARIABLES LIKE 'innodb_lock_wait_timeout';
          设置全局等待事务锁超时时间 SET  GLOBAL innodb_lock_wait_timeout=100;
          查询当前会话等待事务锁超时时间 SHOW VARIABLES LIKE 'innodb_lock_wait_timeout';
          
* sql语句执行顺序（1、FROM；2、ON；3、JOIN；4、WHERE；5、GROUP BY；6、CUBE | ROLLUP；7、HAVING；8、SELECT；9、DISTINCT；10、ORDER BY；11、LIMIT）；
* mysql执行计划explain/explain extended（SHOW WARNINGS;）；
* show [FULL\] processlist（select * from information_schema.processlist; KILL [CONNECTION | QUERY\] processlist_id）；
* sql优化；
    * unsigned；
    * 先查数据总条数再决定是否查列表，而且sql可能不一样；
    * 尽量用索引（区分度高优先）；
    * union all > union > join > 子查询；
    * 变相分页（> 前一页总数 limit pageSize）；
* mysql主从复制、binlog、redolog；
* mysql编码类型，emoji字符编码（utf8mb4），存储容量；
* mysql分库、分表、表分区、读写分离；
* cobar（分库）、mycat、mybatis（分表）官方文档；
* sql执行的过程，各分段执行的顺序；
* 性能调优；
* 数据库连接池druid；
* 其他语法或关键字；
    * CUBE | ROLLUP；

###### HBase
* HBase原理，RowKey优化，OpenTSDB（时间序列数据库）；

###### 时间序列数据库
* influxdb；

###### redis
* redis持久化；
* redis缓存；
* redis集群（sentinel，cluster）

###### memcached
* memcached内存数据库；

###### h2
* 内存数据库（h2）；

###### derby
* Jdk自带的数据库derby；

---
#### LINUX操作系统
* linux常用命令、shell脚本编写（开头的声明含义）；
* linux占用cpu、内存的排序；
* linux安装软件或工具的方式；
* linux进程、线程，时间片，上下文切换；
* 进程间通信，进程同步（生产者消费者问题、哲学家就餐问题、读者写者问题）；
* 缓冲区溢出；
* 分段和分页；
* 虚拟内存与主存；
* 虚拟内存管理；
* 换页算法；
* 服务器性能各项指标（load，cpu，内存、网络io、磁盘io）；
* 同步、异步、阻塞、非阻塞的概念，Linux 5 种 IO 模型；
* CPU 缓存，L1，L2，L3 和伪共享；
* 尾递归；
* 位运算；
* 用位运算实现加、减、乘、除、取余；

---
#### 数据结构和算法
* 简单的数据结构
    * 栈、队列、链表、数组、哈希表；
    * 栈和队列的相同和不同之处；
    * 栈通常采用的两种存储结构
 
* 树
    * 二叉树、字典树、平衡树、排序树、B 树、B+ 树、R 树、多路树、红黑树
 
* 堆
    * 大根堆、小根堆
 
* 图
    * 有向图、无向图、拓扑
 
* 排序算法
    * 稳定的排序：冒泡排序、插入排序、鸡尾酒排序、桶排序、计数排序、归并排序、原地归并排序、二叉排序树排序、鸽巢排序、基数排序、侏儒排序、图书馆排序、块排序；
    * 不稳定的排序：选择排序、希尔排序、Clover 排序算法、梳排序、堆排序、平滑排序、快速排序、内省排序、耐心排序；
    * 各种排序算法和时间复杂度；
 
* 两个栈实现队列，和两个队列实现栈；
* 深度优先和广度优先搜索；
* 全排列、贪心算法、KMP算法、hash算法；
* 海量数据处理
    * 分治，hash映射，堆排序，双层桶划分，Bloom Filter，bitmap，数据库索引，MapReduce 等；
    
* JDK的zip压缩算法CRC32；
* hash一致性算法；
* 加解密算法、对称非对称算法、hash算法、验证文件的完整性；

---
#### 线上问题分析
* dump 获取
    * 线程 Dump、内存 Dump、gc 情况
* dump 分析
    * 分析死锁、分析内存泄露
* dump 分析及获取工具
    * jstack、jstat、jmap、jhat、Arthas
* 自己编写各种 outofmemory，stackoverflow 程序、HeapOutOfMemory、 Young OutOfMemory、MethodArea OutOfMemory、ConstantPool OutOfMemory、DirectMemory OutOfMemory、Stack OutOfMemory Stack OverFlow
* Arthas
    * jvm 相关、class/classloader 相关、monitor/watch/trace 相关、options、管道、后台异步任务文档：https://alibaba.github.io/arthas/advanced-use.html
* 常见问题解决思路
    * 内存溢出、线程死锁、类加载冲突
* 使用工具尝试解决以下问题，并写下总结
    * 当一个 Java 程序响应很慢时如何查找问题
    * 当一个 Java 程序频繁 FullGC 时如何解决问题
    * 如何查看垃圾回收日志
    * 当一个 Java 应用发生 OutOfMemory 时该如何解决
    * 如何判断是否出现死锁
    * 如何判断是否存在内存泄露
    * 使用 Arthas 快速排查 Spring Boot 应用404/401问题
    * 使用 Arthas 排查线上应用日志打满问题
    * 利用 Arthas 排查 Spring Boot 应用 NoSuchMethodError

---
#### 设计模式
* 设计模式的六大原则：
    * 开闭原则（Open Close Principle）、里氏代换原则（Liskov Substitution Principle）、依赖倒转原则（Dependence Inversion Principle）、接口隔离原则（Interface Segregation Principle）、迪米特法则（最少知道原则）（Demeter Principle）、合成复用原则（Composite Reuse Principle）

* 了解23种设计模式
    * 创建型模式：单例模式、抽象工厂模式、建造者模式、工厂模式、原型模式；
    * 结构型模式：适配器模式、桥接模式、装饰模式、组合模式、外观模式、享元模式、代理模式；
    * 行为型模式：模版方法模式、命令模式、迭代器模式、观察者模式、中介者模式、备忘录模式、解释器模式（Interpreter模式）、状态模式、策略模式、职责链模式(责任链模式)、访问者模式。

* 会使用常用设计模式
    * 单例的七种写法（优先选择枚举类和静态内部类）：懒汉——线程不安全、懒汉——线程安全、饿汉、饿汉——变种、静态内部类、枚举、双重锁校验；
    * 工厂模式、适配器模式、策略模式、模板方法模式、观察者模式、外观模式、代理模式等必会；

* 不用synchronized和Lock，实现线程安全的单例模式；
* 实现AOP；
* 实现IOC；
* nio和reactor设计模式；

---
#### 新技术
* JDK 6、7、8、9、10、11、12的新特性以及一些集合类（扩容机制）等底层实现的差异，内存模型的差异、垃圾回收的差异、默认的垃圾收集器（分代回收）；
* Java 8
    * lambda 表达式、Stream API、时间 API
* Java 9
    * Jigsaw、Jshell、Reactive Streams
* Java 10
    * 局部变量类型推断、G1 的并行 Full GC、ThreadLocal 握手机制
* Java 11
    * ZGC、Epsilon、增强 var
* Spring 5
    * 响应式编程
* Spring Boot 2.0
* HTTP/2
* HTTP/3

---
#### 前端&移动端
* SPA；
* PWA；
* flutter；
* 跨域，cookie、iframe、P3P、jsonp；
* js闭包；

---
#### 其他语言
* Groovy、Python、Go、NodeJs、Swift、Rust

---
#### 其它技术趋势
* 区块链；
    * 哈希算法、Merkle 树、公钥密码算法、共识算法、Raft 协议、Paxos 算法与 Raft 算法、拜占庭问题与算法、消息认证码与数字签名
    * 比特币
        * 挖矿、共识机制、闪电网络、侧链、热点问题、分叉
    * 以太坊
    * 超级账本
* 物联网Iot；
    * MQTT（M2M协议）；
    * EMQ消息服务；
* 机器学习；
* 人工智能AI；
    * 数学基础、机器学习、人工神经网络、深度学习、应用场景
    * 常用框架
        * TensorFlow、DeepLearning4J
* 大数据；
    * ETL；
    * Zookeeper
        * 基本概念、常见用法；
    * Solr/SolrCloud，Lucene，ElasticSearch、Nutch
        * 在Linux上部署Solr，SolrCloud，新增、删除、查询索引，分词器；
    * Storm，流式计算，了解Spark，S4
        * 在Linux上部署Storm，用Zookeeper做协调，运行storm hello world，local和remote模式运行调试storm topology。
    * Hadoop，离线计算
        * HDFS & MR、MapReduce
    * 分布式日志收集Flume，Kafka，LogStash
        * 数据挖掘，Mahout
* 云计算；
    * IaaS、SaaS、PaaS、虚拟化技术、OpenStack、ServerLess
* 5G、6G；
* 自动驾驶；
* 量子计算；
* AR & VR；


