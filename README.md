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
# Client
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

# Server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode()) 
```
## OUTPUT
# Client
<img width="837" height="1041" alt="Screenshot 2026-08-19 115136" src="https://github.com/user-attachments/assets/cde85ba3-3f6a-4576-9c20-daf3fdf1103f" />

# Server
<img width="1007" height="1022" alt="Screenshot 2026-08-19 115156" src="https://github.com/user-attachments/assets/59b9aee1-5930-4de9-98b4-75ad0f9206f0" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
