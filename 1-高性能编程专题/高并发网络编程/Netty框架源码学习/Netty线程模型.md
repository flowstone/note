# Netty线程模型
## Netty简介
Netty是一个高性能、高可扩展性的异步事件驱动的网络应用程序框架，它极大地简化TCP和UDP客户端和服务器开发等网络编程。
### Netty重要的四个内容：
1、Reactor线程模型：一种高性能的多线程程序设计思路
2、Netty中自己定义的Channel概念：增强版的通道概念
3、ChannelPipeline职责链设计模式：事件处理机制
4、内存管理：增强的ByteBuf缓冲区

## Netty整体结构图
![Netty整体结构图](_v_images/20190531214625284_6610.png =700x)
## Netty线程模型
为了让NIO处理更好的利用多线程特性，Netty实现了Reactor线程模型。
Reactor模型中有四个核心概念：
1、Resources资源(请求/任务)
2、Synchronous Event Demultiplexer同步事件复用器
3、Dispatcher分配器
4、Request Handler请求处理器
![Netty线程模型](_v_images/20190531214949499_31962.png =600x)

## EventLoopGroup初始化过程
![EventLoopGroup初始化过程](_v_images/20190531215138260_24396.png =780x)
