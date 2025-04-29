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
CLIENT
```
import socket
s=socket.socket()
s.bind(('localhost',9000))
s.listen(5)
c,addr=s.accept()
address={"6A:08:AA:C2":"192.168.1.100","8A:BC:E3:FA":"192.168.1.99"};
while True:
    ip=c.recv(1024).decode()
    try:
        c.send(address[ip].encode())
    except KeyError:
        c.send("Not Found".encode())
```
SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',9000))
while True:
    ip=input("Enter MAC Address : ")
    s.send(ip.encode())
    print("Logical Address",s.recv(1024).decode())
```
## OUPUT
CLIENT:
![438315258-e0516af3-5134-49aa-8e85-cb6a884b8a8d](https://github.com/user-attachments/assets/567b780b-fca5-4946-af41-2f1394f67022)
SERVER:
![438315334-cd203a72-29af-4f21-9f86-8de3628b0789](https://github.com/user-attachments/assets/17ecfe91-a865-478f-8b34-ce3d1edc2466)


## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
