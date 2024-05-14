![312299314-dc0da145-92b6-4b1b-a8c2-d9f17cb05086](https://github.com/dhinesh87/simplewebserver/assets/146917182/f0918aed-0d6a-4304-a74e-5119d0190c1e)# EX01 Developing a Simple Webserver
## Date:11.05.14

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
<!DOCTYPE html>
<html>
<head>
<title>Software Companies</title>
</head>
<body bgcolor="cyan">
<table border="4" cellspacing="1" cellpadling="1" height="300" width="700" bgcolor="white">
<caption>TOP SOFTWARE COMPANIES WITH REVENUE</caption>
		<tr>
			<th>COMPANY</th>
			<th>REVENUE</th>
			<th>PERCENTAGE</th>
		</tr>
		<tr>
			<td>Google</td>
			<td>4541397</td>
			<td>1</td>
		</tr>

		<tr>
			<td>Meta</td>
			<td>3216464</td>
			<td>2</td>
		</tr>

		<tr>
			<td>SAMSUNG</td>
			<td>1649465</td>
			<td>3</td>
		</tr>
                 <tr>
			<td>TCS</td>
			<td>51918518</td>
			<td>4</td>
		</tr>

                 <tr>
			<td>Infosys</td>
			<td>5191587</td>
			<td>5</td>
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
![312299396-6c35e1b2-501f-4188-b204-34200f4fb595](https://github.com/dhinesh87/simplewebserver/assets/146917182/863962b7-36cc-471c-b0e3-29db8672da01)

![312299314-dc0da145-92b6-4b1b-a8c2-d9f17cb05086](https://github.com/dhinesh87/simplewebserver/assets/146917182/0e3bc40d-c670-4d62-922f-3bcb3d2a8c80)


## RESULT:
The program for implementing simple webserver is executed successfully.
