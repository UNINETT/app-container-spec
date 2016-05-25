# Service: Dataporten Authorization

Identifier: `dataportenAuthz`

Request specification:

```json
{
	"dataportenAuthz": {
		"items": [
			{
				"id": "access",
				"title": "Read access to blog"	
			},
			{
				"id": "comment",
				"title": "Access to comment"	
			},
			{
				"id": "write",
				"title": "Editor may write new blog entries"
			},
			{
				"id": "admin",
				"title": "Blog administrators"
			}
		]
	}
}
```

Response specification:

```json
{
	"dataporten": {
		"authentication": {
			"username": "dataporten",
			"password": "db0ed7ec-f759-454e-8deb-7ba3c0b98be7"
		}
	}
}
```

