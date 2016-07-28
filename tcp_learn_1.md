#图解TCP/IP分层与数据在网络中的传送

## TCP/IP分层基础

要理解TCP/IP协议及数据的传送，基础知识是必须要理解的，虽然枯燥，但还是得从基础概念开始啊（话说足球也要从娃娃从青少年抓起，足协那些人怎么这都不懂啊？！）：

* 首先看看OSI参考模型解析，不了解各层的主要功能怎么理解TCP/IP，所以你一定要读读，而且大致知道各层干些啥，而且不要张冠李戴哈

![Alt text](https://github.com/carrier001/blog/blob/master/tcp-1.png "各层应用") 

其实，数据在TCP/IP协议栈中以及网络中的过程不外乎就是数据封装和解封装的过程，只是有些网络中的数据设备有点偷懒，没有解析全部数据（某些数据设备表示反对：哼，不该我干的活当然不干，吃力不讨好啊）

* 数据封装

![Alt text](https://github.com/carrier001/blog/blob/master/tcp-unpack.png "封包") 

实际上协议栈内部就是这么干的。下图是基于DPDK开发协议栈的一种设计：

![Alt text](https://github.com/carrier001/blog/blob/master/d_2.png "") 

* 数据解封装

![Alt text](https://github.com/carrier001/blog/blob/master/tcp-pack.png "解包") 

下图是处理方式

![Alt text](https://github.com/carrier001/blog/blob/master/d_1.png "") 

* 下面的就是数据帧、数据包、数据段啊，其实就是上层数据加上或者减去各层的头而已嘛，基础知识是不是也不枯燥，也很简单，耶^_^

![Alt text](https://github.com/carrier001/blog/blob/master/frame.png "") 

预告，后面图解子网内从A发到B数据发送过程是如何封装和解封装的
