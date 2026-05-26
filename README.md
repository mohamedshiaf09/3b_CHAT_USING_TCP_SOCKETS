# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM
### Server:
```
import socket

s = socket.socket()

s.bind(('localhost', 8000))

s.listen(5)

print("Server Waiting...")

c, addr = s.accept()

print("Connected with", addr)

while True:
    ClientMessage = c.recv(1024).decode()

    print("Client >", ClientMessage)

    if ClientMessage.lower() == "exit":
        break

    msg = input("Server > ")

    c.send(msg.encode())

c.close()
s.close()
```
### Client:
```
import socket

s = socket.socket()

s.connect(('localhost', 8000))

while True:
    msg = input("Client > ")

    s.send(msg.encode())

    reply = s.recv(1024).decode()

    print("Server >", reply)

    if msg.lower() == "exit":
        break

s.close()
```
## OUPUT
### Server:

<img width="785" height="249" alt="image" src="https://github.com/user-attachments/assets/806f52d8-9720-4c17-bde9-f59c46ad41c1" />

### Client:

<img width="873" height="275" alt="image" src="https://github.com/user-attachments/assets/8b63ede0-2528-413d-be01-e00554e6b6cb" />


## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
