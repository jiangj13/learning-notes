# 套接字
Socket 是应用程序和操作系统网络协议栈之间的接口，让程序可以通过网络发送和接收数据
介于应用层和传输层之间，

# TCP Socket 通信模型
如下图所示：![TCP套接字通信过程](Computer_NetWork\images\image.png)
以这个模型举例
示例代码：
## 服务器端
```python
import socket


# 1. 创建TCP Socket
server_socket = socket.socket(
    socket.AF_INET,        # IPv4
    socket.SOCK_STREAM     # TCP
)


# 2. 绑定IP和端口
server_socket.bind(
    ("0.0.0.0", 8080)
)


# 3. 开始监听
server_socket.listen(5)

print("服务器等待连接...")


# 4. 接收客户端连接
conn, addr = server_socket.accept()

print("客户端连接:", addr)


# 5. 接收客户端数据
data = conn.recv(1024)

print("收到客户端:", data.decode())


# 6. 返回数据
conn.send(
    b"hello client"
)


# 7. 关闭连接
conn.close()

server_socket.close()
```


## 客户端

```python
import socket


# 1. 创建TCP Socket
client_socket = socket.socket(
    socket.AF_INET,
    socket.SOCK_STREAM
)


# 2. 连接服务器
client_socket.connect(
    ("服务器IP",8080)
)


# 3. 发送数据
client_socket.send(
    b"hello server"
)


# 4. 接收服务器回复
data = client_socket.recv(1024)

print("服务器回复:", data.decode())


# 5. 关闭连接
client_socket.close()
```