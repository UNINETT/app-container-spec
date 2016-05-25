# Service: TLS Web Certificate

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

* `/etc/certs/appengine/key.pem`
* `/etc/certs/appengine/cert.pem`

Certificate will only be exposed through configuration files if TLS it not terminated.



Exposed through environment variables:

* `TLS=true`
* `TLS_EXPOSED=true`
* `TLS_INTERNAL=false`

