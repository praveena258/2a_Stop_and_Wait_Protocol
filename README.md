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
client.py
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
server.py
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT
server.py
![image](https://github.com/user-attachments/assets/3c905704-021f-4713-bef8-e2a14f351538)
client.py
![Screenshot 2025-05-20 133440](https://github.com/user-attachments/assets/369f4be0-777a-4c7b-b343-18953e1e21ff)



## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
