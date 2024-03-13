### M.Harini
### 212222240035
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
## PROGRAM:
### Client:
```
import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
c, addr = s.accept()

while True:
    data = input("Enter data to send: ")
    c.send(data.encode())

    ack = c.recv(1024).decode()
    if ack == "Acknowledgement Received":
        print("Server acknowledged the data.")
    else:
        print("Error in acknowledgment. Closing connection.")
        c.close()
        break

c.close()
```

### Server:
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    received_data = s.recv(1024).decode()
    print("Received data:", received_data)

    ack_message = "Acknowledgement Received"
    s.send(ack_message.encode())
```
### PROGRAM:

![Screenshot 2024-03-13 113003](https://github.com/Harinimuthu17/2a_Stop_and_Wait_Protocol/assets/130278614/e674a84d-1a04-472f-afdf-db12d46ee3de)



![Screenshot 2024-03-13 112951](https://github.com/Harinimuthu17/2a_Stop_and_Wait_Protocol/assets/130278614/c0642e4a-feb1-4f59-86fd-f849c42b33f8)



## OUTPUT:

![Screenshot 2024-03-13 112935](https://github.com/Harinimuthu17/2a_Stop_and_Wait_Protocol/assets/130278614/cc4d4d72-e4d9-462e-97f8-53ed759ef181)


![Screenshot 2024-03-13 112924](https://github.com/Harinimuthu17/2a_Stop_and_Wait_Protocol/assets/130278614/b8607bf9-0a8d-4694-93f0-c4580dfd978c)


## RESULT

Thus, python program to perform stop and wait protocol was successfully executed.


