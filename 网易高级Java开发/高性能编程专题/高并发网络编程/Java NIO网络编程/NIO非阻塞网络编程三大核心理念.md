# NIO非阻塞网络编程三大核心理念
## JAVA NIO
始于Java1.4，提供了新的Java IO操作非阻塞API.
用意是替代Java IO和Java Networking相关的API.

![NIO有三个核心组件](_v_images/20190530093424702_24557.png)
## Buffer缓冲区
缓冲区本质是一个可以写入数据的内存块(类似数组)，然后可以再次读取。此内存块包含在NIO Buffer对象中，该对象提供了一组方法，可以更轻松地使用内存块。
相比较直接对数组的操作，Buffer API更加容易操作和管理


使用Buffer进行数据写入与读取，需要进行如下四个步骤：
1. 将数据写入缓存区
2. 调用buffer.flip()，转换为读取模式
3. 缓冲区读取数据
4. 调用buffer.clear()或buffer.compact()清除缓冲区

### Buffer工作原理
Buffer三个重要属性：
capacity容量：作为一个内存块，Buffer具有一定的固定大小，也称为“容量”。
position位置：写入模式时代表写数据的位置。读取模式时代表读取数据的位置。
limit限制：写入模式，限制等于buffer的容量。读取模式下，limit等于写入的数据量。