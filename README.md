# EX01 Developing a Simple Webserver
## Date: 26.09.2024

## AIM:
To develop a simple webserver to display the configuration details of my laptop.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import BaseHTTPRequestHandler, HTTPServer

# HTML content to serve
content = '''<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Web Server</title>
    <style>
        body {
            background-color: #f5f5f5;
        }
        table {
            background-color: antiquewhite;
            border-collapse: collapse;
            margin: 20px auto;
        }
        th, td {
            padding: 10px;
            border: 2px solid black;
            text-align: left;
        }
        th {
            background-color: #e0e0e0;
        }
        h1 {
            color: black;
        }
    </style>
</head>
<body>
    <center>
        <h1>My Laptop Configuration</h1>
        <h1>DIVYASHREE V 212223230051</h1>
    </center>
    <table>
        <tr>
            <th>DEVICE SPECIFICATION</th>
            <th>DETAILS</th>
        </tr>
        <tr>
            <td>BRAND</td>
            <td>LENOVO</td>
        </tr>
        <tr>
            <td>MODEL NAME</td>
            <td>E15 GEN 4</td>
        </tr>
        <tr>
            <td>SCREEN SIZE</td>
            <td>15.6 inches</td>
        </tr>
        <tr>
            <td>COLOR</td>
            <td>BLACK</td>
        </tr>
        <tr>
            <td>RAM</td>
            <td>16GB</td>
        </tr>
        <tr>
            <td>PROCESSOR</td>
            <td>CORE i5</td>
        </tr>
        <tr>
            <td>GRAPHICS CARD</td>
            <td>NVIDIA</td>
        </tr>
        <tr>
            <td>SYSTEM TYPE</td>
            <td>64 BIT-OS, x64</td>
        </tr>
    </table>
</body>
</html>
'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200)
        self.send_header("Content-type", "text/html")
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver")
server_address = ('', 8000)
httpd = HTTPServer(server_address, MyServer)
httpd.serve_forever()
```
## OUTPUT:

![Screenshot 2024-09-23 132810](https://github.com/user-attachments/assets/a2ad8aa6-c110-4433-9a89-42445e07b717)

![image](https://github.com/user-attachments/assets/4dbfc472-cf9d-4f06-a36e-130ad7a9c229)


## RESULT:
The program for implementing simple webserver is executed successfully.
