# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM
## SERVER
```
import socket
server = socket.socket()
server.bind(("127.0.0.1", 5555))
server.listen(1)
print("Server waiting for connection...")
client, addr = server.accept()
print("Connected to:", addr)
filename = input("Enter file name to send: ")
with open(filename, "rb") as file:
    data = file.read()
    client.send(data)
print("File sent successfully")
client.close()
server.close()
```

## CLIENT
```
import socket
client = socket.socket()
client.connect(("127.0.0.1", 5555))
save_name = input("Enter name to save file: ")
data = client.recv(1000000)
with open(save_name, "wb") as file:
    file.write(data)
print("File received successfully")
client.close()
```
## Sample.txt
```
Hello Python Socket Programming 
```

## OUPUT
## SERVER
<img width="1507" height="862" alt="Screenshot 2026-08-25 112242" src="https://github.com/user-attachments/assets/439743a8-5d31-45af-be52-1b2e951c229e" />

## CLIENT
<img width="1511" height="796" alt="Screenshot 2026-08-25 112301" src="https://github.com/user-attachments/assets/384945a9-60f5-4b46-888d-9d91320634a8" />

## Sample.txt
<img width="1348" height="510" alt="Screenshot 2026-08-25 112333" src="https://github.com/user-attachments/assets/70c57ad2-ade5-4f5c-845f-c062252d711d" />

## Received.txt
<img width="1450" height="527" alt="Screenshot 2026-08-25 112320" src="https://github.com/user-attachments/assets/05f1eee2-4bfd-4378-857b-e08adebf3026" />


## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
