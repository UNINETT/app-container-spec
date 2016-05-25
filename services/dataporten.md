# Service: Dataporten

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

User input:

```json
{
	"dataporten": {}
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

