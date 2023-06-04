## IMPLEMENTATION OF STOP AND WAIT PROTOCOL

## EXP : 2

## DATE : 15-03-2023

## AIM :
To write a python program to perform stop and wait protocol

## ALGORITHM :
```python
1.Start the program.
2.Get the frame size from the user
3.To create the frame based on the user request.
4.To send frames to server from the client side.
5.If your frames reach the server it will send ACK signal to client otherwise it will send NACK signal to client.
6.Stop the program
```

## CLIENT PROGRAM :
```python
import socket
s = socket.socket()
s.bind(("localhost", 8000))
s.listen(5)
c, addr = s.accept()
while True:
    i = input("Enter a data:")
    c.send(i.encode())
    ack = c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
```

## SERVER PROGRAM :
```python
import socket
s=socket.socket()
s.connect(("localhost", 8000))
while True:
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Received".encode())
```

## CLIENT OUTPUT :

![ex 2 cl output](https://github.com/MrSanthosh-dev/EX-2/assets/117916573/cbae6761-4ed9-4d14-8615-76a76fde05bd)

## SERVER OUTPUT :

![ex 2 se output](https://github.com/MrSanthosh-dev/EX-2/assets/117916573/fe0a3cd3-0694-4a75-8acc-c82293b1b99f)

## RESULT :
Thus, python program to perform stop and wait protocol was successfully executed
