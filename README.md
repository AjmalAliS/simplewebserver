# EX01 Developing a Simple Webserver
## Date: 25.03.2025
## Name: Ajmal Ali S
## Register No: 212224100003
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
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TCP/IP PROTOCOLS</title>
        
</head> 
<body>
    <div class="head">
        <b>TCP/IP PROTOCOLS SUITE.</b>
    </div>
    <center>
    <table style="border: 5px;">
        <tr>
            <th>LAYER NAMES</th>
            <td>PROTOCOLS</td>
        </tr>
        <tr>
            <th>APPLICATION LAYER</th>
            <td>HTTP,FTP,POP3,SMTP,SNMP</td>
        </tr>
        <tr>
            <th>TRANSPORT LAYER</th>
            <td>TCP,UDP</td>
        </tr>
        <tr>
            <th>NETWORKING LAYER</th>
            <td>IP,ICMP</td>
        </tr>
        <tr>
            <th>DATALINK LAYER</th>
            <td>ETHERNET, ARP</td>
        </tr>                        
    </table>
</center>

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
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```

## OUTPUT:
![alt text](<Screenshot (44).png>)


![alt text](<Screenshot (45).png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
