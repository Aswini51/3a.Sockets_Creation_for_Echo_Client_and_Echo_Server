# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM:
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
# ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
# PROGRAM:
## CLIENT:
```
import socket
s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
s.connect(('localhost', 7000)) 

while True:
    msg = input("Client message: ")
    if msg.lower() == "exit":
        break
    s.send(msg.encode())
    reply = s.recv(1024).decode()
    print("Server:", reply)

s.close()

```
## SERVER:
```
import socket
s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
s.bind(('localhost', 7000)) 
s.listen(1)  
print("Server is listening on port 7000...")

conn, addr = s.accept()
print("Connected with:", addr)

while True:
    data = conn.recv(1024).decode()
    if not data:
        break
    print("Client:", data)
    reply = input("Server reply: ")
    conn.send(reply.encode())

conn.close()
s.close()

```
# OUPUT:
<img width="1154" height="269" alt="Screenshot 2025-09-29 102305" src="https://github.com/user-attachments/assets/2be1a71f-d32f-4fd4-ac44-15c8279f579f" />

# RESULT:
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
