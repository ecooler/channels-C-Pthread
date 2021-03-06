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
# ????????? powcoder

# [????????????CS???????????????????????????](https://powcoder.com/)

# Programming Help Add Wechat powcoder

# Email: powcoder@163.com

[????????????](https://powcoder.com/tag/????????????/)

[java??????](https://powcoder.com/tag/java/) [c/c++??????](https://powcoder.com/tag/c/) [python??????](https://powcoder.com/tag/python/) [drracket??????](https://powcoder.com/tag/drracket/) [MIPS????????????](https://powcoder.com/tag/MIPS/) [matlab??????](https://powcoder.com/tag/matlab/) [R????????????](https://powcoder.com/tag/r/) [javascript??????](https://powcoder.com/tag/javascript/)

[prolog??????](https://powcoder.com/tag/prolog/) [haskell??????](https://powcoder.com/tag/haskell/) [processing??????](https://powcoder.com/tag/processing/) [ruby??????](https://powcoder.com/tag/ruby/) [scheme??????](https://powcoder.com/tag/drracket/) [ocaml??????](https://powcoder.com/tag/ocaml/) [lisp??????](https://powcoder.com/tag/lisp/)

- [?????????????????? data structure algorithm ??????](https://powcoder.com/category/data-structure-algorithm/)
- [??????????????? ??????????????? computer network socket programming ??????](https://powcoder.com/category/network-socket/)
- [????????? DB Database SQL ??????](https://powcoder.com/category/database-db-sql/)
- [???????????? machine learning ??????](https://powcoder.com/category/machine-learning/)
- [??????????????? Compiler ??????](https://powcoder.com/category/compiler/)
- [????????????OS(Operating System) ??????](https://powcoder.com/category/????????????osoperating-system/)
- [?????????????????? Computer Graphics opengl webgl ??????](https://powcoder.com/category/computer-graphics-opengl-webgl/)
- [???????????? AI Artificial Intelligence ??????](https://powcoder.com/category/????????????-ai-artificial-intelligence/)
- [????????? Hadoop Map Reduce Spark HBase ??????](https://powcoder.com/category/hadoop-map-reduce-spark-hbase/)
- [???????????? System programming ??????](https://powcoder.com/category/sys-programming/)
- [???????????? Web Application ??????](https://powcoder.com/category/web/)
- [?????????????????? NLP natural language processing ??????](https://powcoder.com/category/nlp/)
- [????????????????????? Computer Architecture ??????](https://powcoder.com/category/computer-architecture/)
- [????????????????????????computer security cryptography ??????](https://powcoder.com/category/computer-security/)
- [??????????????? Computation Theory ??????](https://powcoder.com/category/computation-theory/)
- [???????????????(Compute Vision) ??????](https://powcoder.com/category/???????????????compute-vision/)

