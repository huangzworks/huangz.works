.. Redis使用教程 documentation master file, created by
   sphinx-quickstart on Thu Mar 24 20:00:03 2016.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Redis使用手册
==================

.. image:: image/banner.png
   
**Redis方面的集大成之作，学习和使用Redis必不可少的一本书**

- 对一百八十多个 Redis 命令进行了详细且深入的介绍，并提供了相应的执行示例和参考信息，无论是学习新命令还是回顾已知命令的用法，都会非常方便。
- 展示了锁、缓存、计数信号量、队列、分页、好友关系、自动补全、摇一摇、网址缩短器、唯一计数器、排行榜、登录会话等数十个实际可用的 Redis 应用程序的实现方法，帮助读者学习如何将 Redis 应用到实际开发中。（书中展示的所有应用程序代码都会以开源的方式公开。）
- 内容涵盖最新的 Redis 5，帮助读者将 HyperLogLog、位图（bitmap）、地理位置（GEO）、Redis 集群（cluster）、流（Stream）、模块（Module）等新特性知识全部收入囊中。
- 全书所有章节均经过精心设计和编排，既可以在学习 Redis 时用作教程，又可以在使用 Redis 的过程中用作参考书。
- 通过丰富的图示和详细的例子来展示 Redis 的关键技术，让知识不再枯燥难懂。
- 《Redis设计与实现》作者、《Redis实战》译者、《Redis命令参考》译者黄健宏（huangz）最新力作，学习 Redis 的权威之选。

购买
----------

本书在以下网店或应用有售：

- 京东（\ `自营 <https://item.jd.com/12716266.html>`_\ 、\ `非自营 <https://search.jd.com/Search?keyword=Redis%E4%BD%BF%E7%94%A8%E6%89%8B%E5%86%8C&enc=utf-8&suggest=1.his.0.0&wq=&pvid=00c90db7dc5a473999b2da9407019fb5>`_\ 、\ `电子版 <https://e.jd.com/30530879.html>`_\ ）

- 当当（\ `纸书 <http://product.dangdang.com/27943233.html>`_\ 、\ `电子书 <http://e.dangdang.com/products/1901153748.html>`_\ ）

- `豆瓣读书 <https://book.douban.com/subject/34836750/>`_\ 、\ `豆瓣阅读电子书 <https://read.douban.com/ebook/124156809/>`_

- `微信读书 <https://weibo.com/3219474004/IdRGK79yg>`_

.. - 亚马逊（\ `Kindle电子书 <https://www.amazon.cn/dp/B07YBRPVB8>`_\ ）
.. - `淘宝 <https://s.taobao.com/search?q=redis%E4%BD%BF%E7%94%A8%E6%89%8B%E5%86%8C&imgfile=&commend=all&ssid=s5-e&search_type=item&sourceId=tb.index&spm=a21bo.2017.201856-taobao-item.1&ie=utf8&initiative_id=tbindexz_20170306>`_

.. - `互动出版网 <http://product.china-pub.com/8063671>`_


..
    除了上述网店发售的公版图书之外，
    你还可以选择购买\ `限量的作者签名版 <http://redisguide.com/signed.html>`_\ 。

    本书作者会根据书本的发售情况陆续公布最新的网店销售信息，
    对此感兴趣的朋友请定期浏览本网站，
    又或者关注作者的\ `微博 <http://weibo.com/huangzworks>`_\ 或\ `twitter <https://twitter.com/huangzworks>`_\ 。

目录&试读
------------

*以下目录中可点击的部分为试读内容*\，
你也可以\ `下载 PDF 格式的试读文档 <https://raw.githubusercontent.com/huangzworks/redis-manual-website/master/RedisGuide_preview.pdf>`_ 。

.. toctree::
   :maxdepth: 1

   preface

.. toctree::
   :maxdepth: 2

   introduction

|  

**第一部分：数据结构与应用**

.. toctree::
   :maxdepth: 2

   string

.. toctree::
   :maxdepth: 2

   hash

.. toctree::
   :maxdepth: 2

   list

.. toctree::
   :maxdepth: 2

   set

- 有序集合（Sorted Set）

  - ZADD：添加或更新成员
  - ZREM：移除指定的成员
  - ZSCORE：获取成员的分值
  - ZINCRBY：对成员的分值执行自增或自减操作
  - ZCARD：获取有序集合的大小
  - ZRANK、ZREVRANK：获取成员在有序集合中的排名
  - ZRANGE、ZREVRANGE：获取指定索引范围内的成员
  - 示例：排行榜
  - ZRANGEBYSCORE、ZREVRANGEBYSCORE：获取指定分值范围内的成员
  - ZCOUNT：统计指定分值范围内的成员数量
  - 示例：时间线
  - ZREMRANGEBYRANK：移除指定排名范围内的成员
  - ZREMRANGEBYSCORE：移除指定分值范围内的成员
  - ZUNIONSTORE、ZINTERSTORE：有序集合的并集运算和交集运算
  - 示例：商品推荐
  - ZRANGEBYLEX、ZREVRANGEBYLEX：返回指定字典序范围内的成员
  - ZLEXCOUNT：统计位于字典序指定范围内的成员数量
  - ZREMRANGEBYLEX：移除位于字典序指定范围内的成员
  - 示例：自动补全
  - ZPOPMAX、ZPOPMIN：弹出分值最高和最低的成员
  - BZPOPMAX、BZPOPMIN：阻塞式最大/最小元素弹出操作
  - 重点回顾

- HyperLogLog

  - HyperLogLog 简介
  - PFADD：对集合元素进行计数
  - PFCOUNT：返回集合的近似基数
  - 示例：优化唯一计数器
  - 示例：检测重复信息
  - PFMERGE：计算多个 HyperLogLog 的并集
  - 示例：实现每周/月度/年度计数器
  - 重点回顾

- 位图（bitmap）

  - SETBIT：设置二进制位的值
  - GETBIT：获取二进制位的值
  - BITCOUNT：统计被设置的二进制位数量
  - 示例：用户行为记录器
  - BITPOS：查找第一个指定的二进制位值
  - BITOP：执行二进制位运算
  - 示例：0-1矩阵
  - BITFIELD：在位图中储存整数值
  - 示例：紧凑计数器
  - 使用字符串命令对位图进行操作
  - 重点回顾

- 地理坐标（GEO）

  - GEOADD：储存坐标
  - GEOPOS：获取指定位置的坐标
  - GEODIST：计算两个位置之间的直线距离
  - 示例：具有基本功能的用户地理位置程序
  - GEORADIUS：查找指定坐标半径范围内的其他位置
  - GEORADIUSBYMEMBER：查找指定位置半径范围内的其他位置
  - 示例：查找附近用户
  - GEOHASH：获取指定位置的 Geohash 值
  - 使用有序集合命令操作 GEO 数据
  - 重点回顾

- 流（Stream）

  - XADD：追加新元素到流的末尾
  - XTRIM：对流进行修剪
  - XDEL：移除指定元素
  - XLEN：获知流包含的元素数量
  - XRANGE、XREVRANGE：访问流中元素
  - XREAD：以阻塞或非阻塞方式获取流元素
  - 示例：消息队列
  - 消费者组
  - XGROUP：管理消费者组
  - XREADGROUP：读取消费者组中的消息
  - XPENDING：显示待处理消息的相关信息
  - XACK：将消息标记为“已处理”
  - XCLAIM：转移消息的归属权
  - XINFO：查看流和消费者组的相关信息
  - 示例：为消息队列提供消费者组功能
  - 重点回顾

|  

**第二部分：附加功能**

.. toctree::
   :maxdepth: 2

   database

.. toctree::
   :maxdepth: 2

   expire

.. toctree::
   :maxdepth: 2

   pipeline-and-transaction

- Lua 脚本

  - EVAL：执行脚本
  - 示例：使用脚本重新实现带有身份验证功能的锁
  - 示例：实现 LPOPRPUSH 命令
  - SCRIPT LOAD 和 EVALSHA ：缓存并执行脚本
  - 脚本管理
  - 内置函数库
  - 脚本调试
  - 重点回顾

- 持久化

  - RDB 持久化
  - AOF 持久化
  - RDB-AOF 混合持久化
  - 同时使用 RDB 持久化和 AOF 持久化
  - 无持久化
  - SHUTDOWN：关闭服务器
  - 重点回顾

- 发布与订阅

  - PUBLISH：向频道发送消息
  - SUBSCRIBE：订阅频道
  - UNSUBSCRIBE：退订频道
  - PSUBSCRIBE：订阅模式
  - PUNSUBSCRIBE：退订模式
  - PUBSUB：查看发布与订阅的相关信息
  - 示例：广播系统
  - 重点回顾

- 模块

  - 模块的管理
  - ReJSON 模块
  - RediSQL 模块
  - RediSearch 模块
  - 重点回顾

|

**第三部分：多机功能**

.. toctree::
   :maxdepth: 2

   replication

- Sentinel

  - 启动 Sentinel
  - Sentinel 网络
  - Sentinel 管理命令
  - 在线配置 Sentinel
  - 实例：使用 redis-py 管理 Sentinel
  - 重点回顾

- 集群

  - 基本特性
  - 搭建集群
  - 实例：使用客户端连接集群
  - 散列标签
  - 打开/关闭从节点的读命令执行权限
  - 集群管理工具 redis-cli
  - 集群管理命令
  - 槽管理命令
  - 重点回顾

|

**附录**

.. toctree::
   :maxdepth: 2

   appendix_a

.. toctree::
   :maxdepth: 2

   appendix_b

- 附录 C ：Redis 命令索引表


代码示例
------------

《Redis使用手册》在书中包含了大量 Redis 应用程序示例，你可以通过访问以下页面来获取这些示例的源码：
`github.com/huangzworks/redis-manual-code <https://github.com/huangzworks/redis-manual-code>`_ 。

.. image:: image/github.png


勘误信息
------------

查看《Redis使用手册》已知错误或报告你发现的错误，
请访问\ `此页面 <https://github.com/huangzworks/redis-manual-errata>`_\ 。


作者简介
------------

.. image:: image/huangz.png
   :align: right
   :scale: 35%

本书作者黄健宏自 2011 年接触 Redis 起就一直在持续地学习和研究 Redis ，
并通过写书、翻译、讲授课程等方式与大家分享他了解到的 Redis 知识。

黄健宏分别是\ `《Redis 设计与实现》 <http://huangz.works/redisbook1e>`_\ 和\ `《Redis 实战》 <http://huangz.works/ria>`_\ 这两本畅销 Redis 图书的作者和译者。
与此同时他还长期翻译并维护着在线的中文 Redis 文档《Redis 命令参考》，
这个文档每天都为数量众多的 Redis 使用者提供服务。

作为早期接触 Redis 并且一直深入研究 Redis 的技术人员，
黄健宏对 Redis 的应用和源码有深入的了解，
他希望通过这本《Redis使用手册》向读者传授最常用和最核心的 Redis 知识，
帮助读者了解 Redis 和用好 Redis 。

关于黄健宏的更多信息以及他的联系方式可以在他的个人网站\ `huangz.works <http://huangz.works>`_\ 上面找到。

