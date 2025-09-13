# EX01 Developing a Simple Webserver
## Date: 4/9/25

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
~~~
from http.server import HTTPServer, BaseHTTPRequestHandler

htmlcontent = '''
<!doctype html>
<html>
<head>
<title> Sample </title>
</head>
<body>
<font color="blue" face="Lucida Handwriting" size="120">
            <h1 align="center"> <b> List of protocol in TCP/IP Model</b></h1>
        </font>
        <font color="red">
        <h2>
            Application Layer - HTTP, FTP, DNS, Telnet & SSH <br>
            Transport Layer - TCP & UDP <br>
            Network Layer - IPV4/IPV6 <br>
        </h2>
        </font>
</body>
</html>
'''
class ServerResponse(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(htmlcontent.encode())

print("This is my webserver") 
server_address =('',5000)
httpd = HTTPServer(server_address,ServerResponse)
httpd.serve_forever()
~~~

## OUTPUT:

<img width="1839" height="889" alt="image" src="https://github.com/user-attachments/assets/c8328903-4de6-4721-ab7e-c076634785f0" />


## RESULT:
The program for implementing simple webserver is executed successfully.
