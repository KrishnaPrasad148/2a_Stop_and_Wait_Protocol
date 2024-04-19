# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM


#### Client side:

```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter a data: ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
```

#### Server side:

```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```


## OUTPUT

![Screenshot 2024-04-19 205231](https://github.com/KrishnaPrasad148/2a_Stop_and_Wait_Protocol/assets/147332763/3adcc98a-45b1-4e5f-a7f0-f45bb02a1827)

![Screenshot 2024-04-19 205244](https://github.com/KrishnaPrasad148/2a_Stop_and_Wait_Protocol/assets/147332763/a8363a98-4fa8-4fac-9683-1acd5a8e32c8)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
