# Examples of provisioned services exposed to applications running in containers


Example of web application with HTTP load balancer that terminates SSL with Dataporten integration.

```properties
HOST=myapplication.uninett-apps.no
TLS=true
TLS_EXPOSED=true
TLS_INTERNAL=false
HTTPLB=true
DATAPORTEN_CLIENTID=e0fa9bd1-9e50-466f-9114-98d117bbc44c
DATAPORTEN_CLIENTSECRET=d8ae42d9-ad9b-49f3-96b2-c658c963bf45
DATAPORTEN_SCOPES=openid,groups,userid
DATAPORTEN_CREATOR=57c8664f-0154-45d8-bb91-29348e9fa776
```

Authorization config in `/etc/appengine/authorization.json`:

```json
	{
		"access": {
			"any": true
		},
		"comment"{
			"authenticated": true
		},
		"editor": {
			"groups": [
				"fc:org:uninett", "c37c7bc2-c76c-48ad-9562-22869282a51b"
			]
		},
		"admin": {
			"groups": [
				"24bafc6d-a0bb-46b4-90f1-fbbfc634da6b"
			],
			"users": ["b1b89e6e-2e60-44e9-b5bd-d64e1884c6c4"]
		}
	}
```