

## Example API requests:



Example of a Wordpress blog specification:

```json
{
	"id": "wordpress",
	"name": "Wordpress blog",
	"servicesRequest": {
		"host": {
		},
		"cert": {
			"terminate": true
		},
		"httpLB": {
			"tls": true,
			"exposeHTTP": true,
			"redirectToHTTPS": true,
			"probe": "/healthz"
		},
		""
	}
}
```

Requested application instance:

```json
{
	"applicationId": "wordpress",
	"name": "Bobs blog",
	"servicesRequest": {
		"host": {
			"host: "bob.uninett-apps.no"
		}	
	}
}
```

Response to provisioned application:

```json
{
	"id": "wordpress-1023",
	"name": "Bobs blog",
	"services": {
		"http": {
			"tls": true,
			"exposeHTTP": true,
			"redirectToHTTPS": true,
			"probe": "/healthz"
		}
	}
}
```

