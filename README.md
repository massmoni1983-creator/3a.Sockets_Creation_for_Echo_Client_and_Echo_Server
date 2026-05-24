# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
server.py
```
import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
print("Echo Server is running on port 8000...")

c, addr = s.accept()
print(f"Connected to client at {addr}")

while True:
    ClientMessage = c.recv(1024).decode()
    if not ClientMessage: 
        break  # Stops the loop if the client disconnects
        
    print("Received from Client:", ClientMessage)
    c.send(ClientMessage.encode()) # Echoes the message back

c.close()
s.close()

```
client.py
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    msg = input("Client > ")
    if msg.lower() == 'exit':
        break
        
    s.send(msg.encode())
    print("Server (Echo) > ", s.recv(1024).decode())

s.close()
print("Disconnected.")
```
## OUPUT
<img width="658" height="240" alt="image" src="https://github.com/user-attachments/assets/a658e0db-c61c-427f-aacf-5d2dc7d08c62" />

<img width="654" height="228" alt="image" src="https://github.com/user-attachments/assets/b9069f27-e225-4614-9abe-7780f510019a" />

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
