# Authentication

This section describes the needed authentication to use the API.
Proxyclick uses oAuth2 authentication to grant access to API. 

## Prerequisites

You first need to register your application in Proxyclick system. You can do so by clicking [request API access](https://www.proxyclick.com/api-access-request) and fill in the form.

Once your application is registered to use Proxyclick API, you will receive a clientId and a clientSecret that will allo you to request an access token. 

## Retrieving an access token

Request an access token by posting clientId, clientSecret, userName, password and grant_type to "https://api.proxyclick.com/oauth/token". Note that only POST HTTP verb is accepted to retrieve an access token.

### HTTP Request

`POST https:/api.proxyclick.com/oauth/token`

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
```  

## Verifying an access token

Tokens received from the API MUST be explicitly validated. Failure to verify tokens makes your application more vulnerable to the confused deputy problem. 

When verifying a token, it is critical to ensure the audience field in the response exactly matches the clientId that you obtained when registering your application. It is absolutely vital to perform this step, because it is the mitigation for the confused deputy issue. 

Verify an access token validity by sending the token to "https://api.proxyclick.com/oauth/verify".
POST and GET verbs are accepted for this request.

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
   "token": ""
}'
```

`POST https:/api.proxyclick.com/oauth/verify`

### Body parameters

Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
token | true | string | The token to be verified 

### Response

HTTP/1.1 200 Ok

`{
   "audience": ""
}`

## Revoking an access token

Revoke an access token by sending it to "https://api.proxyclick.com/oauth/revoke".
POST and GET verbs are accepted for this request.
   
### HTTP Request

`GET https:/api.proxyclick.com/oauth/revoke?token=<accesstoken>`

`POST https:/api.proxyclick.com/oauth/token`

```shell
$ curl https:/api.proxyclick.com/oauth/revoke \
-X POST \
-H 'Accept: application/json' \
-H 'Content-Type: application/json' -d '
{
   "token": ""
}'
``` 

## API Requests

Proxyclick expects the access token to be included in all API requests to the server in a header that looks like the following:

`Authorization: Bearer <accessToken>`

<aside class="notice">
You must replace `<accessToken>` with your personal access token.
</aside>

