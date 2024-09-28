# 2c.SIMULATING ARP /RARP PROTOCOLS
## NAME : E.Mythri
## REG.NO : 212223240034
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
P
## PROGRAM - ARP
## CLIENT 
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"};
while True:
       ip=c.recv(1024).deco
de()
       try:
         c.send(address[ip].encode())
       except KeyError:
         c.send("Not Found".encode())
```
## SERVER

```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 ip=input("Enter logical Address : ")
 s.send(ip.encode())
 print("MAC Address",s.recv(1024).decode())
```
## OUTPUT - ARP
## CLIENT 
![Screenshot 2024-09-26 114234](https://github.com/user-attachments/assets/7021ba9d-0551-4f24-acf7-3ec6f1943ba5)

## SERVER
![Screenshot 2024-09-26 114244](https://github.com/user-attachments/assets/0b9bf8da-89c0-4dce-a70f-9db17da21579)
## PROGRAM - RARP
## CLIENT

```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
address={ "6A:08:AA:C2":"165.165.80.80","8A:BC:E3:FA":"165.165.79.1"};
while True:
       ip=c.recv(1024).decode()
       try:
          c.send(address[ip].encode())
       except KeyError:
         c.send("Not Found".encode())
```
## SERVER 

```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter logical Address : ")
    s.send(ip.encode())
    print("Logical Address",s.recv(1024).decode())
```

## OUTPUT -RARP
## CLIENT 
![image](https://github.com/user-attachments/assets/62933394-fe31-4fc0-bbd2-03a0912c5993)

## SERVER 
![image](https://github.com/user-attachments/assets/ce6ecefd-5d51-473b-91b8-8a07f73b2dbb)


## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
