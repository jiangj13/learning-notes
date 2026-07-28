# 套接字
Socket 是应用程序和操作系统网络协议栈之间的接口，让程序可以通过网络发送和接收数据
介于应用层和传输层之间，

# TCP Socket 通信模型
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

第一步：创建 Socket
server_socket = socket.socket()
第二步：绑定地址
server_socket.bind(("0.0.0.0",8080))
ip是 0.0.0.0 代表监听本机所有的ip地址，端口号为8080
第三步：进入监听状态
server_socket.listen()
第四步：接受连接
conn, addr = server_socket.accept()
返回的 conn 是连接的新 Socket
addr 是 客户端 ip 地址和端口号
第五步：接受客户端数据
data = conn.recv(1024) %1024指的是最大读取的字节

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