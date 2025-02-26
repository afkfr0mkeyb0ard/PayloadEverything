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
