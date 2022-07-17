# Channels

## Hello From Channel 5
You are tasked with implementing MPSC (multiple producer, single consumer) channel. You will need to facilitate a transport buffer for this channel. This buffer will contain objects of an agreed sized on channel initialisation. You are required to define the receiver and sender structs which you will use within your implementation.

MPSC is used in the scenario where you have a clear distinction between a consumer end (receives objects)  and a producer end (sends objects). For example, you may have many residents which send mail to a single post office. The post office is the consumer, residents are the producers and the mail is the object.

Research a little bit on shared memory and/or pipes and make a decision about your implementation.

## Initialisation
~~~
void channel_init(struct receiver* recv, struct sender* sender, size_t msg_sz) 
~~~

Given a reference to receiver and sender objects, this function will initialise the receiver and sender objects.

receiver and sender must agree on a size of messages during initialisation. The communication channel must be able to work within the same process, different threads or processes within the same process tree. The channel should not be accessible by processes outside of the process tree and you should not use files in your implementation.

## Retrieving
~~~
void channel_get(struct receiver* channel, void* data)
~~~

The caller is able to retrieve data that exist within the channel. Given a channel and a new location to move the data, we can consume the data from the channel and move it to the data location. This function must block if no data exists within the channel and will retrieve the next available message sent over the channel.

When data is available it should immediately retrieve it and attempt to copy it to the data address. You can assume that data is the size agreed upon initialisation. If data address is NULL, the function should not attempt to consume and write to the data location.

## Sending
~~~
void channel_send(struct sender* channel, void* data)
~~~

A channel is able to send data to a receiver. This will add an object of the size agreed upon on initialisation to the channel. When the receiver retrieves this object it will effectively be removed from the channel. if the data address is NULL, the send function should not attempt to send any data.

## Duplicating
~~~
void sender_dup(struct sender* dest, struct sender* src)
~~~

Sender objects can be duplicated and be spread over multiple threads and processes. If the sender is passed to this function, it must duplicate all fields related to sender and return a copy. If the dest or src is NULL, nothing will be duplicated.

## Destroy (Called but not tested)
~~~
void channel_destroy(struct receiver* recv, struct sender* sender)
~~~

This function will be called in the event that you have malloc'd an object during the init. However, it should not attempt to destroy the receiver or sender. If recv is NULL, it should be ignored, if sender is NULL it should be ignored. If both recv and sender are NULL, the function should not do anything.

Your implementation should be around 60 lines of code.
# channels C Pthread
# 加微信 powcoder

# [代做各类CS相关课程和程序语言](https://powcoder.com/)

# Programming Help Add Wechat powcoder

# Email: powcoder@163.com

[成功案例](https://powcoder.com/tag/成功案例/)

[java代写](https://powcoder.com/tag/java/) [c/c++代写](https://powcoder.com/tag/c/) [python代写](https://powcoder.com/tag/python/) [drracket代写](https://powcoder.com/tag/drracket/) [MIPS汇编代写](https://powcoder.com/tag/MIPS/) [matlab代写](https://powcoder.com/tag/matlab/) [R语言代写](https://powcoder.com/tag/r/) [javascript代写](https://powcoder.com/tag/javascript/)

[prolog代写](https://powcoder.com/tag/prolog/) [haskell代写](https://powcoder.com/tag/haskell/) [processing代写](https://powcoder.com/tag/processing/) [ruby代写](https://powcoder.com/tag/ruby/) [scheme代写](https://powcoder.com/tag/drracket/) [ocaml代写](https://powcoder.com/tag/ocaml/) [lisp代写](https://powcoder.com/tag/lisp/)

- [数据结构算法 data structure algorithm 代写](https://powcoder.com/category/data-structure-algorithm/)
- [计算机网络 套接字编程 computer network socket programming 代写](https://powcoder.com/category/network-socket/)
- [数据库 DB Database SQL 代写](https://powcoder.com/category/database-db-sql/)
- [机器学习 machine learning 代写](https://powcoder.com/category/machine-learning/)
- [编译器原理 Compiler 代写](https://powcoder.com/category/compiler/)
- [操作系统OS(Operating System) 代写](https://powcoder.com/category/操作系统osoperating-system/)
- [计算机图形学 Computer Graphics opengl webgl 代写](https://powcoder.com/category/computer-graphics-opengl-webgl/)
- [人工智能 AI Artificial Intelligence 代写](https://powcoder.com/category/人工智能-ai-artificial-intelligence/)
- [大数据 Hadoop Map Reduce Spark HBase 代写](https://powcoder.com/category/hadoop-map-reduce-spark-hbase/)
- [系统编程 System programming 代写](https://powcoder.com/category/sys-programming/)
- [网页应用 Web Application 代写](https://powcoder.com/category/web/)
- [自然语言处理 NLP natural language processing 代写](https://powcoder.com/category/nlp/)
- [计算机体系结构 Computer Architecture 代写](https://powcoder.com/category/computer-architecture/)
- [计算机安全密码学computer security cryptography 代写](https://powcoder.com/category/computer-security/)
- [计算机理论 Computation Theory 代写](https://powcoder.com/category/computation-theory/)
- [计算机视觉(Compute Vision) 代写](https://powcoder.com/category/计算机视觉compute-vision/)

