# Service: Dataporten Authorization

Identifier: `dataportenAuthz`

Request specification:

```json
{
	"dataportenAuthz": {
		"definitions": {
			"access": "Read access to blog",
			"comment": "Access to comment",
			"editor": "Editor may write new blog entries",
			"admin": "Blog administrators"
		}
	}
}
```

User Input

```json
{
	"dataportenAuthz": {
		"acl": {
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
	}
}
```


Response specification: No extra values.


Exposes to application through configuration file:

`/etc/appengine/authorization.json`

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