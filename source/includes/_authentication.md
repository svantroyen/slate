# Authentication

This section describes the needed authentication to use the API.
Proxyclick uses oAuth2 authentication to grant access to API. 

## Prerequisites

You first need to register your application in Proxyclick system. You can do so by clicking [request API access](https://www.proxyclick.com/api-access-request) and fill in the form.

Once your application is registered to use Proxyclick API, you will receive a clientId and a clientSecret that will allo you to request an access token. 

## Retrieving an access token

Request an access token by posting clientId, clientSecret, userName, password and grant_type to "https://api.proxyclick.com/oauth/token". Note that only POST HTTP verb is accepted to retrieve an access token.

### HTTP Request

```shell
$ curl https:/api.proxyclick.com/oauth/token \
-X POST \
-H 'Accept: application/json' \
-H 'Content-Type: application/json' -d '
{
   "clientId": "",
   "clientSecret": "",
   "userName": "",
   "password": "",
   "grant_type": "password"
}'

Response

HTTP/1.1 200 Ok

{
  "access_token" : token,
  "token_type" : "Bearer"
}

AuthenticationException

HTTP/1.1 401 Unauthorized

{
  "error" : "invalid_client",
  "error_description" : error_message	
}

InvalidGrantException

HTTP/1.1 400 Bad Request

{
  "error" : "invalid_grant",
  "error_description" : error_message	
}

UnauthorizedClientException

HTTP/1.1 400 Bad Request

{
  "error" : "unauthorized_client"
}

UnsupportedGrantTypeException

HTTP/1.1 400 Bad Request

{
  "error" : "unsupported_grant_type"
}

InvalidRequestException

HTTP/1.1 400 Bad Request

{
  "error" : "invalid_request",
  "error_description" : error_message	
}
```

`POST https:/api.proxyclick.com/oauth/token`

### Body parameters

Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
clientId | true | string | The clientId defined when application was registered
clientSecret | true | string | The clientSecret defined when application was registered
userName | true | string | The user name to authenticate with
password | true | string | The password to authenticate with
grant_type | true | string |value is "password"
  


## Verifying an access token

Tokens received from the API MUST be explicitly validated. Failure to verify tokens makes your application more vulnerable to the confused deputy problem. 

When verifying a token, it is critical to ensure the audience field in the response exactly matches the clientId that you obtained when registering your application. It is absolutely vital to perform this step, because it is the mitigation for the confused deputy issue. 

Verify an access token validity by sending the token to "https://api.proxyclick.com/oauth/verify".
POST and GET are accepted verbs for this request.

### HTTP GET Request

```shell
$ curl https:/api.proxyclick.com/oauth/verify?token=<accesstoken> \
```

`GET https:/api.proxyclick.com/oauth/verify?token=<accesstoken>`

### Query Parameters

Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
token | true | string | The token to be verified


### HTTP POST Request

```shell
$ curl https:/api.proxyclick.com/oauth/verify \
-X POST \
-H 'Accept: application/json' \
-H 'Content-Type: application/json' -d '
{
   "token": "<accesstoken>"
}'

Response

HTTP/1.1 200 Ok

{
   "audience": "<clientId>"
}

HTTP/1.1 400 Bad Request

{
  "error" : "invalid_token"
}

HTTP/1.1 400 Bad Request

{
  "error" : "invalid_request",
  "error_description" : error_message
}
```

`POST https:/api.proxyclick.com/oauth/verify`

### Body parameters

Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
token | true | string | The token to be verified 


## Revoking an access token

Revoke an access token by sending it to "https://api.proxyclick.com/oauth/revoke".
POST and GET are accepted verbs for this request.
   
### HTTP GET Request

```shell
$ curl https:/api.proxyclick.com/oauth/revoke?token=<accesstoken> \
```

`GET https:/api.proxyclick.com/oauth/revoke?token=<accesstoken>`

### Query parameters

Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
token | true | string | The token to be revoked


### HTTP POST Request

```shell
$ curl https:/api.proxyclick.com/oauth/revoke \
-X POST \
-H 'Accept: application/json' \
-H 'Content-Type: application/json' -d '
{
   "token": "<accesstoken>"
}'
Response

HTTP/1.1 204

{
}

HTTP/1.1 400 Bad Request

{
  "error" : "invalid_token"
}

HTTP/1.1 400 Bad Request

{
  "error" : "invalid_request",
  "error_description" : error_message
}
```

`POST https:/api.proxyclick.com/oauth/revoke`

### Body parameters

Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
token | true | string | The token to be revoked


## API Requests

Proxyclick expects the access token to be included in all API requests to the server in a header that looks like the following:

`Authorization: Bearer <accessToken>`

<aside class="notice">
You must replace `<accessToken>` with your personal access token.
</aside>

