# An Application Container Specification for Services

An Application Container Specification for requested and provisioned services.

* Version: 0.1
* Feedback: 
  * GitHub Issue,
  * GitHub Pull request, or 
  * Contact <andreas.solberg@uninett.no> or <gurvinder.singh@uninett.no>.



## General model

Each available service specifies:

* Service Identifier
* Depenedencies to other services
* A request specfication
* A provisioned service specfication

## Services

* [Host](services/host.md)
* [Certificates](services/cert.md)
* [L7 Loadbalancer](services/httpLB.md)
* [Dataporten](services/dataporten.md)
* [Dataporten API Gatekeeper](services/dataportenAPI.md)
* [Dataporten Authorization](services/dataportenAuthz.md)
* [SQL Storage](services/sql.md)



## Example applications:



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
		"http": {
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
	"id": "wordpress-1023"
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






