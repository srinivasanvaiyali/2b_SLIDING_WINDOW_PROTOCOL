# Develop By:SRINIVASAN.S
# Reg No:212222043008
# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
## Client program:
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

## sever program:
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
print(s.recv(1024).decode())
s.send("acknowledgement recived from the server".encode())
## OUPUT
## Client 
![image](https://github.com/srinivasanvaiyali/2b_SLIDING_WINDOW_PROTOCOL/assets/145117665/280ad824-59fb-4983-af6f-4d4a33e258c1)
## server 
![image](https://github.com/srinivasanvaiyali/2b_SLIDING_WINDOW_PROTOCOL/assets/145117665/49d2c883-27c5-478c-927a-264526546a2b)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
