# oidc-cli

A CLI for interacting with an [OpenID Connect](http://openid.net/connect/) provider.

`oidc -h`

```
Operate an OpenID Connect Provider

Usage:
  oidc (baseUrl) create-client
  oidc (baseUrl) save-client
  oidc [baseUrl] list-clients

Options:
  -h --help           Show this help.
  -k --insecure       Pass -k to cURL. Allow insecure SSL  

Patterns:
  oidc https://accounts.t402.livefyre.com create-client
  oidc https://accounts.t402.livefyre.com create-client --save
  oidc list-clients
  oidc https://accounts.t402.livefyre.com list-clients
```

## Usage

```
⚡ op=https://accounts.fy.re

⚡ oidc $op create-client --save
{"client_id_issued_at": 1444077276, "redirect_uris": ["https://bengo.com/oauth2/redirect"], "application_type": "web", "registration_client_uri": "accounts.fyre.co/registration?client_id=xCVkvrsOWxdQ", "registration_access_token": "91l30tzd1U2sSkP7i6zYgW1WkOpx5sIo", "client_id": "xCVkvrsOWxdQ", "client_secret": "d1a5a2a77dbcff171dfac4aa452a6e6184bd7b6fbcb3c15211fd816f", "client_secret_expires_at": 1444163676}

⚡ oidc $op list-clients
/Users/bengoering/dev/oidc-cli/clients/accounts.fy.re/xCVkvrsOWxdQ

⚡ oidc $op get-client | jq .
{
  "client_id_issued_at": 1444077276,
  "redirect_uris": [
    "https://bengo.com/oauth2/redirect"
  ],
  "application_type": "web",
  "registration_client_uri": "accounts.fyre.co/registration?client_id=xCVkvrsOWxdQ",
  "registration_access_token": "91l30tzd1U2sSkP7i6zYgW1WkOpx5sIo",
  "client_id": "xCVkvrsOWxdQ",
  "client_secret": "d1a5a2a77dbcff171dfac4aa452a6e6184bd7b6fbcb3c15211fd816f",
  "client_secret_expires_at": 1444163676
}
```
