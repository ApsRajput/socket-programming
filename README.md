# socket-programming
- This is socket programming repo, working with python socket for server client connection

# Guide to Socket Programming Introduction
[![HitCount](http://hits.dwyl.io/shauryauppal/Socket-Programming-Python.svg)](https://github.com/ApsRajput/socket-programming) [![MadeIn](https://img.shields.io/badge/MADE%20IN-PYTHON-darkblue.svg)](https://github.com/ApsRajput/socket-programming) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)
[![GitHub stars](https://img.shields.io/github/stars/shauryauppal/Socket-Programming-Python.svg)](https://github.com/ApsRajput/socket-programming)

## Socket programming is started by socket library

```
import socket
s = socket.socket(socket.AF_INET,socket.SOCK_STREAM)
```

+ AF_INET refers to address family ipv4
+ SOCK_STREAM meaning TCP protocol

*****************


## SERVER code
+ s = socket.socket()
   + It simply creates a new socket using the given address family,socket type and protocol number.
+ port = 12345
   + Reserves a port for computer
+ s.bind('',port)
  + We binded our server to the specified port. Passing an empty string means that the server can listen to incoming connections from other computers as well. If we would have passed 127.0.0.1 then it would have listened to only those calls made within the local computer.
+ s.listen(5)
   + Server can connect to 5 clients, 6th or more clients are rejected.
+ s.accept()
   + Return new socket object c and address
+ s.close()
  + Marks the socket closed, all future operaions on socket will be failed.

 #### OverView
  ```
import socket                
  
s = socket.socket()          
print("Socket successfully created")
port = 1224

s.bind(('', port))         
print("socket binded to %s" %(port))  

s.listen(5)      
print("socket is listening")  
while True:   
   c, addr = s.accept()      
   print('Got connection from', addr)  
   c.send(bytes('Thank you for connecting', 'utf-8')) 
   c.close() 
```
Server uses `bind() , listen() , accept()`
*************
## Client Code

+ First create socket object
+ Give port number same as server
+ connect() '127.0.0.1' local machine connection
+ print s.recv(1024) #print data recv from socket
+ close() connection
```
import socket                
s = socket.socket()          
port = 1224       
s.connect(('127.0.0.1', port)) 
print(s.recv(1024)) 
s.close()
```

# Made in Quarantine :mask:
