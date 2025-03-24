# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
~~~
import socket
HOST = "127.0.0.1"
PORT = 65432
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    print("Server is listening...")
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
~~~
CLIENT.PY:
~~~
import socket
HOST = "127.0.0.1"
PORT = 65432
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    message = "Hello, world!"
    s.sendall(message.encode())
    data = s.recv(1024)
    print(f"Received {data.decode()}")
~~~

## OUTPUT:
![Screenshot 2025-03-24 143013](https://github.com/user-attachments/assets/7c9461c8-5764-4a97-9c60-8d22351a6b3f)
![Screenshot 2025-03-24 143223](https://github.com/user-attachments/assets/0dc728bc-c198-4a23-89cc-f4414423a52d)
![Screenshot 2025-03-24 143353](https://github.com/user-attachments/assets/f57d1f97-9731-4cb0-bbfd-7c177978dce0)
![Screenshot 2025-03-24 143624](https://github.com/user-attachments/assets/b0c927b9-9de4-4124-aee7-ef87682cd7f8)

## RESULT:
The program is executed successfully
