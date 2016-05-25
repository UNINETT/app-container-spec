

# Service: Dataporten API Gatekeeper

Identifier: `dataportenAPI`

Request specification:

```json
{
	"dataportenAPI": {
		"path": "/",
		"policy": "auto",
		"subscopes": {
			"write": {
				"title": "Write access",
				"policy": "moderate"
			}
		}
	}
}
```


User input: none

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


Exposed through environment variables:

* `DATAPORTEN_API_USER=dataporten`
* `DATAPORTEN_API_PASS=db0ed7ec-f759-454e-8deb-7ba3c0b98be7`
