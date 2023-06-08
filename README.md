# EX-3 IMPLEMENTATION OF SLIDING WINDOW PROTOCOL

```
DATE : 23-03-2023
```
# AIM :
To write a python program to perform sliding window protocol.

# ALGORITHM :
```
1.Start the program.
2.Get the frame size from the user
3.To create the frame based on the user request.
4.To send frames to server from the client side.
5.If your frames reach the server it will send ACK signal to client otherwise it will 
  send NACKsignal to client.
6.Stop the program
```

# PROGRAM :
```
Developed by: S Adithya Chowdary.
Reg. No: 212221230100.
```

# Client Side:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
    while(i<len(l)):
        st+=s
        c.send(str(l[i:st]).encode())
        ack=c.recv(1024).decode()
        if ack:
            print(ack)
            i+=s
 ```
 # Server Side:
 ```
 import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("acknowledgement recived from the server".encode())
 ```
 
 # OUTPUT :
 # Client Side:
 ![241420225-d19669fc-ae54-480a-8d17-194dabd529e8](https://github.com/arunkumardev-07/EX-3/assets/135949761/032d4265-5261-4e0d-ae91-04510117233d)

# Server Side:
![241420230-80a65f3e-021b-44d4-af2e-a6ddbfebc3ed](https://github.com/arunkumardev-07/EX-3/assets/135949761/4cacbb0e-ce89-4185-b8e8-c02490ba29c3)

# RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.