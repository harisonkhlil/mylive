# 重新理解 TCP 三次握手

#TCP #三次握手 #网络

> 三次握手的目的

**保证双方都有发送和接收的能力**

具体流程如下图:

![图片来自 图解网络-小林coding-亮白风格-v4.0，第 26 页](https://raw.githubusercontent.com/harisonkhlil/oss/main/uPic/%E5%9B%BE%E7%89%87%E6%9D%A5%E8%87%AA%20%E5%9B%BE%E8%A7%A3%E7%BD%91%E7%BB%9C-%E5%B0%8F%E6%9E%97coding-%E4%BA%AE%E7%99%BD%E9%A3%8E%E6%A0%BC-v4.0%EF%BC%8C%E7%AC%AC%2026%20%E9%A1%B5.png)

1. 双方都是 `CLOSE` 状态,但是 服务端处于 `LISTEN`状态
2. 客户端发送`SYN`,之后处于`SYN_SENT`状态
3. 服务端收到发起的连接,返回`SYN`,并且`ACK(回复)`客户端的`SYN`,之后处于`SYN_RCVD`状态.**这步操作在服务端成功验证了客户端具有发送的能力**
4. 客户端收到服务端发送的 `SYN` 和 `ACK` 之后，发送对 `SYN` 确认的 `ACK` ，之后处于 `ESTABLISHED` 状态，**这步操作客户端验证了服务端具有接收和发送的能力**
5. 服务端收到 `ACK` 的 `ACK `之后，处于 `ESTABLISHED` 状态，**这步操作服务端验证了客户端具有接收的能力**

