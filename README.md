# Ex.No:1a  			Study of Socket Programming

## Aim: 
To perform a study on Socket Programming
## Introduction:

 	Socket programming is a crucial aspect of network communication, allowing for data exchange between computers over a network. It forms the backbone of various networked applications, enabling communication between clients and servers. This study explores the fundamental concepts of socket programming, its use cases, and provides a practical example to demonstrate its implementation.
## Understanding Socket Programming:
	Socket programming involves the use of sockets, which serve as endpoints for communication. A socket is identified by an IP address and a port number, and it facilitates data transfer between a client and a server. The two main types of sockets are Stream Sockets, which provide a reliable, connection-oriented communication, and Datagram Sockets, which are connectionless and suitable for scenarios where reliability is less critical.
## Key Concepts in Socket Programming:
1.Sockets
•	A socket is a software representation of a communication endpoint in a network.
•	It is identified by an IP address and a port number.
•	Sockets can be classified into two main types: Stream Sockets and Datagram Sockets.
•	Stream Sockets provide a reliable, connection-oriented communication, while Datagram Sockets are connectionless and operate in a best-effort mode.

2. Client-Server Model

•	Socket programming typically follows the client-server model.
•	The server listens for incoming connections from clients, while clients initiate connections to the server.
•	Servers are passive, waiting for connection requests, and clients are active, initiating communication.

3, TCP/IP Protocol:

•	Transmission Control Protocol (TCP) and Internet Protocol (IP) are the foundational protocols for socket programming.
•	TCP provides reliable, connection-oriented communication, ensuring data integrity and order.
•	IP facilitates the routing of data between devices in a network.

4.Basic Socket Functions:

•	Socket programming involves a set of functions provided by the operating system or programming language to create, bind, listen, accept, connect, send, and receive data through sockets.
•	Examples of functions include socket(), bind(), listen(), accept(), connect(), send(), and recv().

## Server-Side Operations:
```

import socket

# Create socket
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Bind socket to IP and port
host = '127.0.0.1'
port = 12345
server_socket.bind((host, port))

# Listen for connections
server_socket.listen(1)
print("Server is waiting for connection...")

# Accept client connection
conn, addr = server_socket.accept()
print("Connected to:", addr)

# Receive data from client
data = conn.recv(1024).decode()
print("Client says:", data)

# Send response to client
message = "Hello Client, message received!"
conn.send(message.encode())

# Close connection
conn.close()
server_socket.close()
```

## Client –Server Operations
```
2. Client Program (client.py)
import socket

# Create socket
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# Connect to server
host = '127.0.0.1'
port = 12345
client_socket.connect((host, port))

# Send message to server
message = "Hello Server!"
client_socket.send(message.encode())

# Receive response from server
data = client_socket.recv(1024).decode()
print("Server says:", data)

# Close socket
client_socket.close()
`````
## Output:

<img width="1476" height="127" alt="Screenshot 2026-03-11 105558" src="https://github.com/user-attachments/assets/ce74ca01-a9e8-4802-9026-c285ee52f2af" />
<img width="1325" height="221" alt="Screenshot 2026-03-11 105639" src="https://github.com/user-attachments/assets/588148c0-9e92-4a37-b8cd-bac44dc2faed" />



## Result:
Thus the study of Socket Programming Completed Successfully
