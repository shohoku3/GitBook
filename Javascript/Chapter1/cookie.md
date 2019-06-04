### cookie
**Cookie** 是在您的计算机上存储在小的文本文件中的数据。
- 是一种客户端的状态管理技术
- 当客户端向服务端发送请求时，服务端将少量信息以set-cookie消息头的形式发回客户端
- cookie是有时间限制的，根据生命期不同分成两种：会话cookie和持久cookie；
**Session**
- 是一种服务端的状态管理技术
- 基于cookie技术
- 客户端访问服务器端时 服务端创建一个session对象 有唯一id sessionid
- sessonid 会以cookie的方式发回服务器