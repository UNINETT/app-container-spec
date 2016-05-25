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



## Service: DNS Hostname

Identifier: `host`


Request specification:

```json
{
	"host": {
		"host": "myapplication.uninett-apps.no"		
	}
}
```


Response specification:

```json
{
	"host": {
		"host": "myapplication.uninett-apps.no"		
	}
}
```

Exposed through Environment variable:

* `HOST=myapplication.uninett-apps.no`


## Service: TLS Web Certificate

Identifier: `cert`

Depends on: `host`.

Request specification:

```json
{
	"cert": {
	}
}
```


Response specification:

```json
{
	"cert": {
		"host": "myapplication.uninett-apps.no",
		"expires": 1495696621,
		"certificate": "YmFzZTY[base64]0LWVuY29kZWQtY2VydGlmaWNhdGU=",
		"key": "YmFzZTY[base64]0LWVuY29kZWQta2V5"
	}
}
```

Exposed through configuration files:

* `/etc/certs/appengine/`

Certificate will only be exposed through configuration files if TLS it not terminated.



Exposed through environment variables:

* `TLS_EXPOSED=true`
* `TLS_INTERNAL=false`




## Service: L7 Loadbalancer

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


## Service: Dataporten

* Identifier: `dataporten`
* Depends on: `host` and `cert`.


Request specification:

```json
{
	"dataporten": {
		"redirectURIpath": "/callback",
		"scopes": ["openid", "groups", "userid"]
	}
}
```



Response specification:

```json
{
	"dataporten": {
		"clientId": "e0fa9bd1-9e50-466f-9114-98d117bbc44c",
		"clientSecret": "d8ae42d9-ad9b-49f3-96b2-c658c963bf45",
		"redirectURI": "/callback",
		"org": "fc:org:uninett.no",
		"scopes": ["openid", "groups", "userid"]
	}
}
```





## Service: Dataporten API Gatekeeper

Identifier: `dataportenAPI`

Request specification:

```json
{
	"dataportenAPI": {
		"tls": true,
		"exposeHTTP": true,
		"redirectToHTTPS": true,
		"probe": "/healthz"
	}
}
```





## Service: Dataporten Authorization

Identifier: `dataportenAuthz`


## Service: Dataporten Authorization



## Service: SQL

Identifier: `sql`




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






