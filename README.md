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


* [services/host]
* [services/cert]
* [services/httpLB]
* [services/dataporten]
* [services/dataportenAPI]
* [services/dataportenAuthz]
* [services/sql]



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






