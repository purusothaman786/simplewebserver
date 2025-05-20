# EX01 Developing a Simple Webserver
## Date:20/05/2025

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
<html>
<title>laptop configuration</title>
<body align="center">
    <h1>MY LENOVO THINK PAD E16 GEN 1 CONFIGURATION</h1>
    <table border="7" cellpadding="5" cellspacing="4" width="50%" align="center">
        <tr>
            <th>Configuration</th>
            <th>Description</th>
        </tr>
        <tr>
            <td>Processor</td>
            <td>13th Gen Intel(R) Core(TM) i5-1335U 1.30 GHz
            </td>
        </tr>
        <tr>
            <td>Primary Memory</td>
            <td>16 GB RAM</td>
        </tr>
        <tr>
            <td>system type</td>
            <td>64-bit operating system, x64-based processor</td>
        </tr>
        <tr>
            <td>Dedicated Graphic Memory Capacity
            </td>
            <td> GPU ENVIDIA GeForce MX5504 GB</td>
        </tr>
        <tr>
            <td>SSD Capacity
            </td>
            <td>512 GB</td>
        </tr>
        <tr>
            <td>Primary Memory</td>
            <td>16 GB RAM</td>
        </tr>
        <tr>
            <td>Clock Speed
            </td>
            <td>Upto 5.0 GHz</td>
        </tr>
        <tr>
            <td>Screen Type</td>
            <td>Full HD, IPS, 300nits, Anti-glare, 100% sRGB, 144Hz Refresh Rate, G-SYNC
            </td>
        </tr>
        <tr>
            <td>MAC ADDRESS
            </td>
            <td>68-34-21-7F-09-F9</td>
        </tr>
        <tr>
            <td>EDITION</td>
            </td>
            <td>Windows 11 Home Single Language</td>
        </tr>
    </table>
</body>

</html>
"""
class myhandler (BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('', 8000)
httpd = HTTPServer (server_address, myhandler)
print("my webserver is running...")
httpd.serve_forever()
```

## OUTPUT:

![image](https://github.com/user-attachments/assets/ad71dbac-7b99-4975-a276-6ff0d8bf6d56)

## RESULT:
The program for implementing simple webserver is executed successfully.
