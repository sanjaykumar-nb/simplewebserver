# EX01 Developing a Simple Webserver
## Date:23-02-2024

## AIM:
To develop a simple webserver to serve html pages.

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
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
    <head>
        <title align="center">Top Software Companies</title>
    </head>
    <body>
        <h1 align="center">Top Software Companies in the World!</h1><br/>
        <table border="2" cellspacing="2" cellpading="2" height="100" width="750" align="center">
            <tr align="center">
                <th>S.No</th>
                <th>Company Name</th>
                <th>Country</th>
            </tr>
            <tr align="center">
                <td>1.</td>
                <td>Microsoft</td>
                <td>United States</td>

            </tr>
            <tr align="center">
                <td>2.</td>
                <td>Oracle</td>
                <td>United States</td>
            </tr>
            <tr align="center">
                <td>3.</td>
                <td>SAP</td>
                <td>Germany</td>
            </tr>
            <tr align="center">
                <td>4.</td>
                <td>Salesforce</td>
                <td>United States</td>
            </tr>
            <tr align="center">
                <td>5.</td>
                <td>Adobe Inc.</td>
                <td>United States</td>
            </tr>
            <tr align="center">
                <td>6.</td>
                <td>VMware</td>
                <td>United States</td>
            </tr>
            <tr align="center">
                <td>7.</td>
                <td>Dassault Systemes</td>
                <td>France</td>
            </tr>
            

        </table>
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
![alt text](<Screenshot 2024-03-15 034629.png>)
![alt text](<Screenshot 2024-03-15 034816.png>)
## RESULT:
The program for implementing simple webserver is executed successfully.
