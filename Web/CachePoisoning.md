> From the PortSwigger very good article:\
> https://portswigger.net/web-security/web-cache-poisoning

## What is cache poisoning

Cache poisoning is a technique that allows an attacker **to cache malicious web pages and serve them to website users**. This can lead to XSS, Openredirection, etc.

## Headers (server response)

- Cache-Control
```
Cache-Control: max-age=30       The cache lifetime in seconds
Cache-Control: no-cache         The response can be cached but it is validated before every use
Cache-Control: private          The response can be cached in a private cache only
Cache-Control: no-store         No response can be cached 		
```

- X-Cache
```
X-Cache: hit          Means you are loading content from a cache server (CDN)
X-Cache: miss         Means you are loading content from the webserver itself
```

- Age
```
Age: 5      Age of the cache
```

- Vary
```
Vary: User-Agent         Means that the User-Agent header will determine the cache response
Vary: Accept             Means that the Accept header will determine the cache response
```
