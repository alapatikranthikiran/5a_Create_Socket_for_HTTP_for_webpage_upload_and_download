# 5a_Create_Socket_for_HTTP_for_webpage_upload_and_download
## AIM :
To write a PYTHON program for socket for HTTP for web page upload and download
## Algorithm

1.Start the program.
<BR>
2.Get the frame size from the user
<BR>
3.To create the frame based on the user request.
<BR>
4.To send frames to server from the client side.
<BR>
5.If your frames reach the server it will send ACK signal to client otherwise it will send NACK signal to client.
<BR>
6.Stop the program
<BR>
## Program 
main.py
```
import socket

def send_request(host, port, request):
    s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    s.connect((host, port))

    s.sendall(request.encode())
    response = s.recv(4096)

    print(response.decode())
    s.close()

host = "example.com"
port = 80

request = "GET / HTTP/1.1\r\nHost: example.com\r\n\r\n"

send_request(host, port, request)
```
text.html
```
<!DOCTYPE html>
<html>
<head>
    <title>Simple HTML Page</title>
</head>
<body>

    <h1>Welcome to HTML</h1>
    <p>This is a simple HTML file.</p>

    <button onclick="showMessage()">Click Me</button>

    <script>
        function showMessage() {
            alert("Hello World!");
        }
    </script>

</body>
</html>
```
## OUTPUT
<img width="1183" height="792" alt="image" src="https://github.com/user-attachments/assets/569b6537-687f-47e9-90d5-be1b94b2b97e" />

## Result
Thus the socket for HTTP for web page upload and download created and Executed
