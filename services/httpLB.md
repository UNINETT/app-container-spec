
# Service: L7 Loadbalancer

* Identifier: `httpLB`



Request specification:

```json
{
	"httpLB": {
		"exposeHTTP": true,
		"exposeHTTPS": true,
		"redirectToHTTPS": true,
		"probe": "/healthz"
	}
}
```

User input: No extra

Exposed environment variables:


```properties
HTTPLB=true
```
