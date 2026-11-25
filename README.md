# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
### SERVER:
```
import socket

server = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

server.bind(('localhost', 8000))
server.listen(1)

print("Server is waiting for client...")

conn, addr = server.accept()
print("Connected to:", addr)

while True:
    data = conn.recv(1024).decode()

    if not data:
        break

    print("Client:", data)

    conn.send(data.encode())

conn.close()
server.close()

```

### CLIENT:
```

import socket

client = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

client.connect(('localhost', 8000))

while True:
    msg = input("Enter message: ")

    if msg.lower() == 'exit':
        break

    client.send(msg.encode())

    data = client.recv(1024).decode()

    print("Echo from Server:", data)

client.close()

```
## OUPUT

### CLIENT & SERVER:

<img width="1320" height="365" alt="image" src="https://github.com/user-attachments/assets/1ea3100f-a5a6-41dd-8fbb-30698bcadb41" />


## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
