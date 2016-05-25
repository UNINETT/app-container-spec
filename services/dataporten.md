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

User input: none


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

Exposed through environment variables:

* `DATAPORTEN_CLIENTID=e0fa9bd1-9e50-466f-9114-98d117bbc44c`
* `DATAPORTEN_CLIENTSECRET=d8ae42d9-ad9b-49f3-96b2-c658c963bf45`
* `DATAPORTEN_REDIRECTURI=https://myapplication.uninett-apps.no/callback`
* `DATAPORTEN_SCOPES=openid,groups,userid`
* `DATAPORTEN_CREATOR=57c8664f-0154-45d8-bb91-29348e9fa776`



DATAPORTEN_CREATOR identifies the userID of the user that registered and created the App. Might be useful for bootstrapping in some cases, when the Dataporten Authorization module is not used.


