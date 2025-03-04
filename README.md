# Developing a Simple Webserver

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

HTML content creation is done

### Step 2:

Design of webserver workflow

### Step 3:

Implementation using Python code

### Step 4:

Serving the HTML pages.

### Step 5:

Testing the webserver

## PROGRAM:
```python
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<h1>Top Five Web Application Development Frameworks</h1>
<h2>1.Django</h2>
<h2>2. MEAN Stack</h2>
<h2>3. React </h2>
<h2>4. Ruby On Rails </h2>
<h2>5. ASP.NET </h2>
</body>
</html>
'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```


## OUTPUT:

### Client Output
![Screenshot (108)](https://github.com/ShanmathiShanmugam/webserver/assets/121243595/577e424a-6ed8-4129-8f86-889656d03f66)


###  Server Output
![Screenshot 2023-06-08 114331](https://github.com/ShanmathiShanmugam/webserver/assets/121243595/318e9559-433d-4caa-8ef0-77903e4e7f1a)


## RESULT:
The program is executed succesfully
