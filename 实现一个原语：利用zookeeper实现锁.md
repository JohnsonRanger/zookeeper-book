使用Zookeeper的一个简单例子就是通过锁来实现临界区。目前有多种锁（如读写锁，全局锁），使用Zookeeper来实现锁也有多种方式。这里我们讨论一个简单的秘方来说明应用如何使用Zookeeper，不考虑其它锁的变体。

假设我们现在有一个应用，其中有n个进程尝试获取一个锁。回想到Zookeeper是不直接暴露原语，所以我们需要使用Zookeeper的接口来操作一个znode以此来实现一个锁。

