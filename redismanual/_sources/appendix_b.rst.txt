附录 B ：redis-py 安装方法
===============================

本书的绝大部分代码示例都使用 Python 语言编写，
并且使用了 redis-py 客户端来连接服务器并发送命令请求。

如果你正在使用的电脑尚未安装 Python ，
那么请访问 Python 的官方网站并按照文档中介绍的方法下载并安装相应的编程环境：
https://www.python.org/downloads/ 。

因为本书的程序都是使用 Python 3 编写的，
所以在下载 Python 安装程序的时候，
请确保你下载的是 Python 3 而不是 Python 2 的安装程序。

在安装 Python 之后，
你应该可以通过输入以下命令来运行该语言的解释器：

::

    $ python3
    Python 3.7.3 (default, Mar 27 2019, 09:23:15) 
    [Clang 10.0.1 (clang-1001.0.46.3)] on darwin
    Type "help", "copyright", "credits" or "license" for more information.
    >>> 

在安装完 Python 语言环境之后，
我们就可以通过执行以下命令，
使用其附带的 pip 程序来安装 redis-py 客户端了：

::

    $ pip install redis

在成功安装 redis-py 之后，
我们就能够在 Python 解释器里面载入这个库了：

::

    >>> from redis import Redis             # 载入库
    >>> client = Redis()                    # 创建客户端实例
    >>> client.set("msg", "hello world")    # 执行 SET 命令
    True
    >>> client.get("msg")                   # 执行 GET 命令
    b'hello world'                          # 未解码的值

注意，
正如这里展示的 ``GET`` 命令执行结果所示，
redis-py 默认将返回编码后的值作为结果。
如果我们想让 redis-py 在操作字符串数据的时候自动对其实施解码，
那么只需要在创建客户端实例的时候将 ``decode_responses`` 可选项的值设置为 ``True`` 即可，
就像这样：

::

    >>> client = Redis(decode_responses=True)
    >>> client.get("msg")
    'hello world'           # 字符串已解码

最后，
如果你有兴趣的话，
还可以通过执行以下命令查看 redis-py 目前支持的 Redis 命令：

::

    >>> for i in dir(client):
    ...   print(i)
    ...
    RESPONSE_CALLBACKS
    __class__
    # ...
    _zaggregate
    append
    bgrewriteaof
    bgsave
    bitcount
    bitfield
    bitop
    bitpos
    # ...
    zscan
    zscan_iter
    zscore
    zunionstore
