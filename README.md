# Ex No:2b  IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## NAME : KAAMESH M
## REGISTER NUMBER : 212223040080
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM:
### CLIENT
```py
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c, addr=s. accept()
size=int(input ("Enter number of frames to send"))
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
### SERVER
```py
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())

```
## OUTPUT
### CLIENT OUTPUT:

![CN 2b c](https://github.com/Kaameshm25/2b_SLIDING_WINDOW_PROTOCOL/assets/144870650/826c7bdc-3346-4ec9-85fc-6cbca69f5592)


### SERVER OUTPUT:

![CN 2b s](https://github.com/Kaameshm25/2b_SLIDING_WINDOW_PROTOCOL/assets/144870650/a0b18c2b-7c7d-4be9-9911-a079c46acc9f)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
