# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## DATE: 12-05-26
## AIM:
To implement sliding window protocol.
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
## CLIENT
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5);
c,add = s.accept()
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
## SERVER
```
import socket
s=socket.socket()
s.connect(('localhost', 8000))
while True:
   print(s.recv(1024).decode())
   s.send("acknowledgement received from the server".encode())
```
## OUPUT
![IMAGE](https://github.com/VGSAIRAIMA/2b_SLIDING_WINDOW_PROTOCOL/blob/main/Screenshot%202026-05-12%20054626.png)
![IMAGE](https://github.com/VGSAIRAIMA/2b_SLIDING_WINDOW_PROTOCOL/blob/main/Screenshot%202026-05-12%20054641.png)
## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
