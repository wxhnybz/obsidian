#### thrift的定义 
thrift是一个跨语言的RPC（Remote Procedure Call）框架，用于远程通信。
通常来说，一个应用系统（System），可能会由多个服务（Service）组成，多个服务（Service）可能会部署在多台服务器（Server）上。而这些服务之间可能需要进行通信，这时就需要网络通信的参与了，而RPC框架，就是把网络通信的细节给封装和隐藏起来，只暴露一些简单的接口，使得不同服务之间的远程调用变得简单，并提升了开发效率。

#### thrift通信的3个步骤
- 定义接口
- 定义server
- 定义client
![[Pasted image 20231010130712.png]]
使用场景为thrift代码生成器，thrift应用框架库，和生成的代码

#### Thrift的协议
这是对传输协议的封装，也就是传输采用二进制，XML或者text表示信息，它的功能有两个 :

1. 双向的消息队列
2. 信息的编码和解码