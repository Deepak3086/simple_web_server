# EX01 Developing a Simple Webserver

# Date:9/10/24
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

~~~
from django.shortcuts import render,HttpResponse
from http.server import HTTPServer,BaseHTTPRequestHandler
content='''
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>properties</title>
    <style>
        *{
             background-color: azure;
        }
        table {
            width: 50%;
            border-collapse: collapse;
            margin: 80px 0;
           
        }
        th, td {
            border: 1px solid #1c211f;
            padding: 8px;
            text-align: left;
        }
        th {
            background-color: #5e645e;
        }
        .head{
            text-align: center;
            font-size: 50px;
            
        }

           
            
        
        
    </style>
</head> 
<body>
    <div class="head">
        <b>DEVICE PROPERTIES</b>
    </div>
<center>
    <table style="border: 5px;">
        <tr>
            <th>DEVICE NAME</th>
            <td>Deepak</td>
        </tr>
        <tr>
            <th>PROCESSOR</th>
            <td>13th Gen Intel(R) Core(TM) i7-1335U   1.30 GHz</td>
        </tr>
        <tr>
            <th>Installed RAM</th>
            <td>16.0 GB (15.7 GB usable)</td>
        </tr>
        <tr>
            <th>DEVICES ID</th>
            <td>15EEA3B2-7EF5-4DEC-903D-577382C3C005</td>
        </tr>
        <tr>
            <th>PRODUCT ID</th>
            <td>00342-42708-95366-AAOEM</td>
        </tr>
        <tr>
            <tr>
                <th>SYSTEM TYPE</th>
                <td>64-bit operating system, x64-based processor</td>
        </tr>
        <tr>
            <th>PEN AND TOUCH</th>
            <td>touch support with 3 touch points</td>
        </tr>                            
    </table>
    </center>

</body>
</html>
'''
class Myserver(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200)
        self.send_header("content-type","text/html")
        self.end_headers()
        self.wfile.write(content.encode())
print("This is my webserver")
serveraddress=('',8000)
httpd = HTTPServer(serveraddress,Myserver)
httpd.serve_forever()
~~~

# OUTPUT:

![Screenshot 2024-12-02 132700](https://github.com/user-attachments/assets/db0edc64-01dc-4536-967a-6705c3f100cb)
![Screenshot 2024-12-02 132712](https://github.com/user-attachments/assets/b247eaae-df96-4965-83e3-5bf798fd6264)

# RESULT:
The program for implementing simple webserver is executed successfully.
