# Kill framework

```
curl -v -d'frameworkId=ee6367e9-6c6b-4508-8df0-ff1a1ab15d10-0000' -X POST http://192.168.2.52:5050/master/teardown
```

```
 curl -vk http://10.10.10.10:5050/master/state
*   Trying 10.10.10.10...
* Connected to 10.10.10.10 (10.10.10.10) port 5050 (#0)
> GET /master/state HTTP/1.1
> Host: 10.10.10.10:5050
> User-Agent: curl/7.47.0
> Accept: */*
> 
< HTTP/1.1 307 Temporary Redirect
< Date: Fri, 16 Nov 2018 06:11:36 GMT
< Location: //10.175.221.224:5050/master/state
< Content-Length: 0
< 
* Connection #0 to host 10.10.10.10 left intact

```

