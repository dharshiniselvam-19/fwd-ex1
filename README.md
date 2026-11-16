# EX01 Developing a Simple Webserver
## Date: 16.11.2026
## REF NO: 26010031
## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """


<!DOCTYPE html>
<html>
<head>
    <title>TCP/IP Protocol Model</title>

    <style>
        body {
            font-family: Arial;
            text-align: center;
        }

        h1 {
            text-decoration: underline;
        }

        .container {
            width: 60%;
            margin: auto;
        }

        .layer {
            border: 2px solid black;
            padding: 20px;
            margin: 12px;
            border-radius: 5px;
        }

        h2 {
            margin: 5px;
        }
    </style>
</head>

<body>

    <h1>TCP/IP PROTOCOL MODEL</h1>

    <div class="container">

        <div class="layer">
            <h2>4. Application Layer</h2>
            <p>Provides services to users.</p>
            <b>HTTP | FTP | SMTP | DNS</b>
        </div>

        <div class="layer">
            <h2>3. Transport Layer</h2>
            <p>Provides end-to-end communication.</p>
            <b>TCP | UDP</b>
        </div>

        <div class="layer">
            <h2>2. Internet Layer</h2>
            <p>Handles addressing and routing.</p>
            <b>IP | ICMP</b>
        </div>

        <div class="layer">
            <h2>1. Network Access Layer</h2>
            <p>Transfers data through the network.</p>
            <b>Ethernet | Wi-Fi</b>
        </div>

    </div>

</body>
</html>

"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',880)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()

## OUTPUT:
<img width="1431" height="861" alt="Screenshot 2026-11-14 160210" src="https://github.com/user-attachments/assets/5eb45d72-58a4-4968-bdda-24c2dfc395b4" />
<img width="888" height="302" alt="Screenshot 2026-11-14 160241" src="https://github.com/user-attachments/assets/e35cd494-4063-4749-aaf6-a35fe212345a" />


## RESULT:
The program for implementing simple webserver is executed successfully.

