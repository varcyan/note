# AJAX工作原理

### 1. Ajax的名字

>   `ajax` 的全称是Asynchronous JavaScript and XML，其中，Asynchronous 是异步的意思，它有别于传统web开发中采用的同步的方式。

### 2. Ajax包含的技术

ajax 是几种原有技术的结合体，它由下列技术组合而成：

1.  使用css和html来表示
2.  使用DOM模型来交互和动态显示
3.  使用XMLHttpRequest来和服务器进行异步通信
4.  使用javascript来进行绑定和调用

在上面几中技术中，除了`XmlHttpRequest`对象以外，其它所有的技术都是基于web标准并且已经得到了广泛使用的，XMLHttpRequest虽然目前还没有被W3C所采纳，但是它已经是一个事实的标准，因为目前几乎所有的主流浏览器都支持它。

### 3. Ajax原理和XmlHttpRequest对象

Ajax的原理简单来说通过`XmlHttpRequest`对象来向服务器发异步请求，从服务器获得数据，然后用javascript来操作DOM而更新页面。
*这其中最关键的一步就是从服务器获得请求数据。要清楚这个过程和原理，我们必须对 XMLHttpRequest有所了解。*

**XmlHttpRequest对象的属性**

onreadystatechange  每次状态改变所触发事件的事件处理程序。
responseText        从服务器进程返回数据的字符串形式。
responseXML         从服务器进程返回的DOM兼容的文档数据对象。
status              从服务器返回的数字代码，比如常见的404（未找到）和200（已就绪）
status Text         伴随状态码的字符串信息
readyState          对象状态值

-   0 (未初始化) 对象已建立，但是尚未初始化（尚未调用open方法）
-   1 (初始化) 对象已建立，尚未调用send方法
-   2 (发送数据) send方法已调用，但是当前的状态及http头未知
-   3 (数据传送中) 已接收部分数据，因为响应及http头不全，这时通过responseBody和responseText获取部分数据会出现错误
-   4 (完成) 数据接收完毕,此时可以通过通过responseXml和responseText获取完整的回应数据

*为了给xmlHttp的readyState变化绑定一个监听事件。*