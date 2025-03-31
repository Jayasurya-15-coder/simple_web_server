# EX01 Developing a Simple Webserver

# Date:
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Laptop Specifications</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: rgb(181, 176, 176);
          
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .specs-container {
            background-color:rgb(212, 205, 218);
            padding: 20px;
            border-radius: 10px;
            box-shadow: rgb(233, 232, 234);
            width: 400px;
        }
        h1 {
            text-align: center;
            color:rgb(20, 13, 53);
        }
        table {
            width: 100%;
            border-collapse: collapse;
        }
        th, td {
            padding: 10px;
            text-align: left;
            border-bottom: 1px solid rgb(243, 234, 234);
        }
        th {
            background-color: #b0b3d2;
        }
    </style>
</head>
<body>
    <div class="specs-container">
        <h1>🇱​🇦​🇵​🇹​🇴​🇵​ 🇸​🇵​🇪​🇨​🇮​🇫​🇮​🇨​🇦​🇹​🇮​🇴​🇳​🇸​</h1>
        <table>
            <tr>
                <th>Specification</th>
                <th>Details</th>
            </tr>
            <tr>
                <td>Brand</td>
                <td>ASUS</td>
            </tr>
            <tr>
                <td>Model</td>
                <td>TUF Gaming A15</td>
            </tr>
            <tr>
                <td>Processor</td>
                <td>AMD Ryzen 7 4800H</td>
            </tr>
            <tr>
                <td>RAM</td>
                <td>16 GB</td>
            </tr>
            <tr>
                <td>Storage</td>
                <td>512 GB</td>
            </tr>
            <tr>
                <td>Graphics</td>
                <td>GeForce RTX 3050</td>
            </tr>
            <tr>
                <td>Graphics</td>
                <td>4 GB</td> 
            <tr>
                <td>Display</td>
                <td>15.6inch Full HD</td>
            </tr>
            <tr>
                <td>Battery Life</td>
                <td>Up to 90 hours</td>
            </tr>
            <tr>
                <td>Operating System</td>
                <td>Windows 11</td>
            </tr>
            <tr>
                <td>Price</td>
                <td>61000 INR</td>
            </tr>
        </table>
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
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()

```
# OUTPUT:

![Screenshot (25)](https://github.com/user-attachments/assets/1abc31de-12a3-4a12-a601-c3d5c75e28a6)

![Screenshot 2025-03-31 183916](https://github.com/user-attachments/assets/4f2f1576-3469-49fc-af15-bd414b3d58ec)

# RESULT:
The program for implementing simple webserver is executed successfully.
