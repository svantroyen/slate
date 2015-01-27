---
title: Proxyclick API Reference

language_tabs:
  - cUrl
  - python
  - php

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://api.proxyclick.com/docs'>Documentation Powered by Proxyclick</a>

includes:
  - errors

---

# Introduction

Welcome to the Proxyclick API! You can use our API to access Proxyclick API endpoints.

We have language bindings in Shell, Python and PHP! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Summary

This part will explain shortly how the API needs to be consumed


# Authentication

> To authorize, use this code:


```cUrl
curl "api_endpoint_here"
  -H "Authorization: Bearer <accessToken>"
```

```python
curl "api_endpoint_here"
  -H "Authorization: Bearer <accessToken>"
```

```php
curl "api_endpoint_here"
  -H "Authorization: Bearer <accessToken>"
```


> Make sure to replace `<accessToken>` with your access token.

THis section describes the authentication needed to be able to use the api

Proxyclick expects for the access token to be included in all API requests to the server in a header that looks like the following:

`Authorization: Bearer <accessToken>`

<aside class="notice">
You must replace `<accessToken>` with your personal access token.
</aside>


# Meetings

## Meeting model

### Meeting object

A meeting object contains the following fields

Attribute | Type | Description
--------- | ---- | -----------
object | string | value is "meeting" 
id | string | the id of the meeting
uid | string | the uid of the meeting
occurenceId | string | the occurence id of the meeting (if recurrent)
company | object | the company object of the meeting
title | string | the title of the meeting
description | string | the description of the meeting
startAt | timestamp | the date at which the meeting starts
endAt | timestamp | the date at which the meeting ends
host | object | the host (user) object of the meeting
users | list of objects | the list of user objects linked to the meeting
visitors | list of objects | the list of visitor (user) objects attending to the meeting
recurrence | string | the recurrence of the meeting
timezone | string | the timezone defining the start and end dates of the meeting
createdAt | timestamp | the date of creation of the meeting
createdBy | object | the creator object of the meeting : a simplified version of the user object
createdVia | object | the object defining how the meeting was created
lastModifiedAt | timestamp | the date of last modification of the meeting
checkinNotificationType | string | the type of notification of the meeting (for group meetings)
checkinNotificationUsers | list of objects | the list of user objects who will receive checkin notification for this meeting
checkoutNotificationUsers | list of objects | the list of user objects who will receive checkout notification for this meeting

Example of meeting object

```json
{
	"object":"meeting",
	"id":"M-TF325",
	"uid":"8A604C12-94A0-4B20-A7FCECC3EB7EF4DF",
	"occurrenceId":null,
	"company": {
		"object":"corporate",
		"id":"CO-C202",
		"reference":null,
		"name":"L'Oreal",
		"timezone":"Europe\/Brussels",
		"locale":"en-US",
		"phone":"+12125551423",
		"logoUrl":"http:\/\/api-local.proxyclick.com\/documents\/CD4A034116D11ED8C8\/2-192x53-a.png",
		"createdAt":"2014-01-07T09:05:31Z",
		"lastModifiedAt":"2015-01-06T11:45:51Z",
		"countryCode":"BE",
		"latitude":50.680992,
		"longitude":4.395790,
		"status":"ACTIVATED"
	},
	"title":"zdeazd zeadzed",
	"description":null,
	"startAt":"2014-12-01T12:00:00+01:00",
	"endAt":"2014-12-01T14:00:00+01:00",
	"host": {
		"object":"user",
		"id":"US-G606",
		"firstname":"Yo",
		"lastname":"Da",
		"companyName":"L'Oreal",
		"email":"svantroyen@proxyclick.com",
		"phone":"023333201",
		"mobile":"+442077774331",
		"language":{"code":"fr","name":"fran\u00e7ais","displayName":"fran\u00e7ais"},
		"pictureUrl":"http:\/\/api-local.proxyclick.com\/documents\/0D4F1AFF5CCA5DA8D50982\/6-120x118-la.png",
		"createdAt":"2014-01-07T09:05:31Z",
		"lastModifiedAt":"2014-12-16T14:44:09Z",
		"function":"web developer",
		"about":"Star wars fan, new technologies addict",
		"licensePlate":"aaaaaaa",
		"birthday":null,
		"entryDate":null,
		"lastLoggedAt":"2015-01-12T09:22:06Z",
		"assistant": {
			"object":"user",
			"id":"US-KP935",
			"firstname":"trterte",
			"lastname":"eterterte",
			"companyName":"Ecode23",
			"email":"svtff@yopmail.com",
			"phone":"",
			"mobile":"",
			"language":{
				"code":"fr",
				"name":"fran\u00e7ais",
				"displayName":"fran\u00e7ais"
			},
			"pictureUrl":"http:\/\/static-local.proxyclick.com:80\/user\/profile\/ppic-defaultuser-man.png",
			"createdAt":"2014-04-16T14:42:54Z",
			"lastModifiedAt":"2014-05-07T13:43:35Z"
		},
		"isAssistantOf": [
			{
				"object":"user",
				"id":"US-KQ036",
				"firstname":"retstet",
				"lastname":"hfhfhfhf",
				"companyName":"Ecode23",
				"email":"resvt@yopmail.com",
				"phone":"",
				"mobile":"",
				"language": {
					"code":"fr",
					"name":"fran\u00e7ais",
					"displayName":"fran\u00e7ais"
				},
				"pictureUrl":null,
				"createdAt":"2014-04-16T14:44:43Z",
				"lastModifiedAt":"2014-12-16T14:44:09Z"
			}
		]
	},
	"users":null,
	"visitors":[
		{
			"object":"visitor",
			"id":"V-ELJ230",
			"firstname":"zdeazd",
			"lastname":"zeadzed",
			"companyName":"adeazdeazed",
			"email":"",
			"phone":"",
			"mobile":"",
			"mobileStatus":"UNKNOWN",
			"language": {
				"code":"fr",
				"name":"fran\u00e7ais",
				"displayName":"fran\u00e7ais"
			},
			"pictureUrl":null,
			"function":null,
			"about":null,
			"licensePlate":null,
			"birthday":null,
			"frequent":false,
			"attachmentCount":0,
			"customFields":null,
			"smsReminder":0,
			"mailReminder":0
		}
	],
	"recurrence":null,
	"timezone":"Europe\/Brussels",
	"createdAt":"2014-12-01T11:35:13Z",
	"createdBy": {
		"type":"USER",
		"object":"user",
		"id":"US-G606",
		"name":"Yo Da"
	},
	"createdVia": {
		"type":"APPLICATION",
		"name":"Proxyclick customer application"
	},
	"lastModifiedAt":"2014-12-01T11:35:13Z",
	"checkinNotificationType":"FIRST_LAST",
	"checkinNotificationUsers":null,
	"checkoutNotificationUsers":null
}
```



## Get All meetings

```curl
curl "https://api.proxyclick.com/app/<companyId>/vm/meetings"
  -H "Authorization: Bearer <accessToken>"
```

```python
import urllib2

headers = {'Authorization': 'Bearer <accessToken>'}

url = 'https://api.proxyclick.com/app/<companyId>/vm/meetings'      
req = urllib2.Request(url, None, headers)

resp = urllib2.urlopen(req).read()
```

```php
$service_url = 'https://api.proxyclick.com/app/<companyId>/vm/meetings';
$curl = curl_init($service_url);
$curl_post_data = array("Authorization" => 'Bearer <accessToken>');

curl_setopt($curl, CURLOPT_RETURNTRANSFER, true);
curl_setopt($curl, CURLOPT_POST, true);
curl_setopt($curl, CURLOPT_POSTFIELDS, $curl_post_data);
$curl_response = curl_exec($curl);
curl_close($curl);
```

> The above command returns JSON structured like this:

```json
[{"object":"meeting","id":"M-TF325","uid":"8A604C12-94A0-4B20-A7FCECC3EB7EF4DF","occurrenceId":null,"company":{"object":"corporate","id":"CO-C202","reference":null,"name":"L'Oreal","timezone":"Europe\/Brussels","locale":"en-US","phone":"+12125551423","logoUrl":"http:\/\/api-local.proxyclick.com\/documents\/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6DD1A4A804D241715CCCC8E08C9CEFC13E2ECD4AA00DD034116D11ED8C8\/2-192x53-la.png","createdAt":"2014-01-07T09:05:31Z","lastModifiedAt":"2015-01-06T11:45:51Z","countryCode":"BE","latitude":50.680992,"longitude":4.395790,"status":"ACTIVATED"},"title":"zdeazd zeadzed","description":null,"startAt":"2014-12-01T12:00:00+01:00","endAt":"2014-12-01T14:00:00+01:00","host":{"object":"user","id":"US-G606","firstname":"Yo","lastname":"Da","companyName":"L'Oreal","email":"svantroyen@proxyclick.com","phone":"023333201","mobile":"+442077774331","language":{"code":"fr","name":"fran\u00e7ais","displayName":"fran\u00e7ais"},"pictureUrl":"http:\/\/api-local.proxyclick.com\/documents\/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D2DD514D8F4A771000CECD8A10D4CFE00FE1FEC5A809D70B4318D50982\/6-120x118-la.png","createdAt":"2014-01-07T09:05:31Z","lastModifiedAt":"2014-12-16T14:44:09Z","function":"web developer","about":"Star wars fan, new technologies addict","licensePlate":"aaaaaaa","birthday":null,"entryDate":null,"lastLoggedAt":"2015-01-12T09:22:06Z","assistant":{"object":"user","id":"US-KP935","firstname":"trterte","lastname":"eterterte","companyName":"Ecode23","email":"svtff@yopmail.com","phone":"","mobile":"","language":{"code":"fr","name":"fran\u00e7ais","displayName":"fran\u00e7ais"},"pictureUrl":"http:\/\/static-local.proxyclick.com:80\/user\/profile\/ppic-defaultuser-man.png","createdAt":"2014-04-16T14:42:54Z","lastModifiedAt":"2014-05-07T13:43:35Z"},"isAssistantOf":[{"object":"user","id":"US-KQ036","firstname":"retstet","lastname":"hfhfhfhf","companyName":"Ecode23","email":"resvt@yopmail.com","phone":"","mobile":"","language":{"code":"fr","name":"fran\u00e7ais","displayName":"fran\u00e7ais"},"pictureUrl":"http:\/\/static-local.proxyclick.com:80\/user\/profile\/ppic-defaultuser-man.png","createdAt":"2014-04-16T14:44:43Z","lastModifiedAt":"2014-12-16T14:44:09Z"}]},"users":null,"visitors":[{"object":"visitor","id":"V-ELJ230","firstname":"zdeazd","lastname":"zeadzed","companyName":"adeazdeazed","email":"","phone":"","mobile":"","mobileStatus":"UNKNOWN","language":{"code":"fr","name":"fran\u00e7ais","displayName":"fran\u00e7ais"},"pictureUrl":"http:\/\/static-local.proxyclick.com:80\/_\/app\/img\/vm-visitor-img-placeholder-man.png","function":null,"about":null,"licensePlate":null,"birthday":null,"frequent":false,"attachmentCount":0,"customFields":null,"smsReminder":0,"mailReminder":0}],"recurrence":null,"timezone":"Europe\/Brussels","createdAt":"2014-12-01T11:35:13Z","createdBy":{"type":"USER","object":"user","id":"US-G606","name":"Yo Da"},"createdVia":{"type":"APPLICATION","name":"Proxyclick customer application"},"lastModifiedAt":"2014-12-01T11:35:13Z","checkinNotificationType":"FIRST_LAST","checkinNotificationUsers":null,"checkoutNotificationUsers":null},...]
```

This endpoint retrieves all meetings of a company.

### HTTP Request

`GET https://api.proxyclick.com/app/<companyId>/vm/meetings`

### URL Parameters

Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
companyId | true | string | The id of the company for which the meetings need to be retrieved


### Body Parameters

Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
from | true | date | the result will only include meetings starting from this date
to | true | date | the result will only include meetings ending at this date

<aside class="success">Remember — a happy kitten is an authenticated kitten!</aside>

<aside class="warning">If you're not using an administrator API key, note that some kittens will return 403 Forbidden if they are hidden for admins only.</aside>

## Get a Specific meeting

```curl
curl "http://example.com/api/kittens/3"
  -H "Authorization: meowmeowmeow"
```

```python
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```php
import 'kittn'

api = Kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

> The above command returns JSON structured like this:

```json
{
   "object": "meeting",
   "id": "M-VJ476",
   "uid": "84CF7EBA-A81F-4028-A46428F93784CC49",
   "occurrenceId": null,
   "company": {
      "object": "corporate",
      "id": "CO-C202",
      "reference": null,
      "name": "L'Oreal",
      "timezone": "Europe/Brussels",
      "locale": "en-US",
      "phone": "+12125551423",
      "logoUrl": "http://api-local.proxyclick.com/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6DD1A4A804D241715CCCC8E08C9CEFC13E2ECD4AA06DD074116D51DD8C8/2-192x53-la.png",
      "createdAt": "2014-01-07T09:05:31Z",
      "lastModifiedAt": "2015-01-06T11:45:51Z",
      "countryCode": "BE",
      "latitude": 50.680992,
      "longitude": 4.39579,
      "status": "ACTIVATED"
   },
   "title": "John Doe",
   "description": null,
   "startAt": "2015-01-12T15:00:00+01:00",
   "endAt": "2015-01-12T17:00:00+01:00",
   "host": {
      "object": "user",
      "id": "US-G606",
      "firstname": "Yo",
      "lastname": "Da",
      "companyName": "L'Oreal",
      "email": "svantroyen@proxyclick.com",
      "phone": "023333201",
      "mobile": "+442077774331",
      "language": {
         "code": "fr",
         "name": "français",
         "displayName": "français"
      },
      "pictureUrl": "http://api-local.proxyclick.com/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D2DD514D8F4A771000CECD8A10D4CFE00FE1FEC5AE09D30B431CD60982/6-120x118-la.png",
      "createdAt": "2014-01-07T09:05:31Z",
      "lastModifiedAt": "2014-12-16T14:44:09Z",
      "function": "web developer",
      "about": "Star wars fan, new technologies addict",
      "licensePlate": "aaaaaaa",
      "birthday": null,
      "entryDate": null,
      "lastLoggedAt": "2015-01-12T09:22:06Z",
      "assistant": {
         "object": "user",
         "id": "US-KP935",
         "firstname": "trterte",
         "lastname": "eterterte",
         "companyName": "Ecode23",
         "email": "svtff@yopmail.com",
         "phone": "",
         "mobile": "",
         "language": {
            "code": "fr",
            "name": "français",
            "displayName": "français"
         },
         "pictureUrl": "http://static-local.proxyclick.com:80/user/profile/ppic-defaultuser-man.png",
         "createdAt": "2014-04-16T14:42:54Z",
         "lastModifiedAt": "2014-05-07T13:43:35Z"
      },
      "isAssistantOf": [
         {
            "object": "user",
            "id": "US-KQ036",
            "firstname": "retstet",
            "lastname": "hfhfhfhf",
            "companyName": "Ecode23",
            "email": "resvt@yopmail.com",
            "phone": "",
            "mobile": "",
            "language": {
               "code": "fr",
               "name": "français",
               "displayName": "français"
            },
            "pictureUrl": "http://static-local.proxyclick.com:80/user/profile/ppic-defaultuser-man.png",
            "createdAt": "2014-04-16T14:44:43Z",
            "lastModifiedAt": "2014-12-16T14:44:09Z"
         }
      ]
   },
   "users": null,
   "visitors": [
      {
         "object": "visitor",
         "id": "V-EQK930",
         "firstname": "John",
         "lastname": "Doe",
         "companyName": "Mega corporate",
         "email": "johndoe@yopmail.com",
         "phone": "",
         "mobile": "",
         "mobileStatus": "UNKNOWN",
         "language": {
            "code": "fr",
            "name": "français",
            "displayName": "français"
         },
         "pictureUrl": "http://static-local.proxyclick.com:80/_/app/img/vm-visitor-img-placeholder-man.png",
         "function": null,
         "about": null,
         "licensePlate": null,
         "birthday": null,
         "frequent": false,
         "attachmentCount": 0,
         "customFields": null,
         "smsReminder": 0,
         "mailReminder": 0
      }
   ],
   "recurrence": null,
   "timezone": "Europe/Brussels",
   "createdAt": "2015-01-12T14:53:41Z",
   "createdBy": {
      "type": "USER",
      "object": "user",
      "id": "US-G606",
      "name": "Yo Da"
   },
   "createdVia": {
      "type": "APPLICATION",
      "name": "Proxyclick customer application"
   },
   "lastModifiedAt": "2015-01-12T14:53:41Z",
   "checkinNotificationType": "FIRST_LAST",
   "checkinNotificationUsers": null,
   "checkoutNotificationUsers": null
}
```

This endpoint retrieves a specific meeting.

### HTTP Request

`GET https://api.proxyclick.com/app/<companyId>/vm/meetings/<meetingId>`

### URL Parameters

Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
companyId | true | string | The id of the company for which the meeting needs to be retrieved
meetingId | true | string | The ID of the meeting to retrieve


## Create a meeting

```curl
curl "http://example.com/api/kittens/3"
  -H "Authorization: meowmeowmeow"
```

```python
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```php
import 'kittn'

api = Kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

> The above command returns JSON structured like this:

```json
{
   "object": "meeting",
   "id": "M-VK577",
   "uid": "5F6669B5-C5E2-4716-A4758FF637DA922D",
   "occurrenceId": null,
   "company": {
      "object": "corporate",
      "id": "CO-C202",
      "reference": null,
      "name": "L'Oreal",
      "timezone": "Europe/Brussels",
      "locale": "en-US",
      "phone": "+12125551423",
      "logoUrl": "http://api-local.proxyclick.com/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6DD1A4A804D241715CCCC8E08C9CEFC13E2ECD4AA06DD064916D016D8C8/2-192x53-la.png",
      "createdAt": "2014-01-07T09:05:31Z",
      "lastModifiedAt": "2015-01-06T11:45:51Z",
      "countryCode": "BE",
      "latitude": 50.680992,
      "longitude": 4.39579,
      "status": "ACTIVATED"
   },
   "title": "John Doel",
   "description": null,
   "startAt": "2015-01-12T16:00:00+01:00",
   "endAt": "2015-01-12T18:00:00+01:00",
   "host": {
      "object": "user",
      "id": "US-G606",
      "firstname": "Yo",
      "lastname": "Da",
      "companyName": "L'Oreal",
      "email": "svantroyen@proxyclick.com",
      "phone": "023333201",
      "mobile": "+442077774331",
      "language": {
         "code": "fr",
         "name": "français",
         "displayName": "français"
      },
      "pictureUrl": "http://api-local.proxyclick.com/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D2DD514D8F4A771000CECD8A10D4CFE00FE1FEC5AE09D2034319DD0982/6-120x118-la.png",
      "createdAt": "2014-01-07T09:05:31Z",
      "lastModifiedAt": "2014-12-16T14:44:09Z",
      "function": "web developer",
      "about": "Star wars fan, new technologies addict",
      "licensePlate": "aaaaaaa",
      "birthday": null,
      "entryDate": null,
      "lastLoggedAt": "2015-01-12T09:22:06Z",
      "assistant": {
         "object": "user",
         "id": "US-KP935",
         "firstname": "trterte",
         "lastname": "eterterte",
         "companyName": "Ecode23",
         "email": "svtff@yopmail.com",
         "phone": "",
         "mobile": "",
         "language": {
            "code": "fr",
            "name": "français",
            "displayName": "français"
         },
         "pictureUrl": "http://static-local.proxyclick.com:80/user/profile/ppic-defaultuser-man.png",
         "createdAt": "2014-04-16T14:42:54Z",
         "lastModifiedAt": "2014-05-07T13:43:35Z"
      },
      "isAssistantOf": [
         {
            "object": "user",
            "id": "US-KQ036",
            "firstname": "retstet",
            "lastname": "hfhfhfhf",
            "companyName": "Ecode23",
            "email": "resvt@yopmail.com",
            "phone": "",
            "mobile": "",
            "language": {
               "code": "fr",
               "name": "français",
               "displayName": "français"
            },
            "pictureUrl": "http://static-local.proxyclick.com:80/user/profile/ppic-defaultuser-man.png",
            "createdAt": "2014-04-16T14:44:43Z",
            "lastModifiedAt": "2014-12-16T14:44:09Z"
         }
      ]
   },
   "users": null,
   "visitors": [
      {
         "object": "visitor",
         "id": "V-EQL031",
         "firstname": "John",
         "lastname": "Doel",
         "companyName": "Mega corporate",
         "email": "johndoel@yopmail.com",
         "phone": "",
         "mobile": "",
         "mobileStatus": "UNKNOWN",
         "language": {
            "code": "fr",
            "name": "français",
            "displayName": "français"
         },
         "pictureUrl": "http://static-local.proxyclick.com:80/_/app/img/vm-visitor-img-placeholder-man.png",
         "function": null,
         "about": null,
         "licensePlate": null,
         "birthday": null,
         "frequent": false,
         "attachmentCount": 0,
         "customFields": null,
         "smsReminder": 0,
         "mailReminder": 0
      }
   ],
   "recurrence": null,
   "timezone": "Europe/Brussels",
   "createdAt": "2015-01-12T15:50:58Z",
   "createdBy": {
      "type": "USER",
      "object": "user",
      "id": "US-G606",
      "name": "Yo Da"
   },
   "createdVia": {
      "type": "APPLICATION",
      "name": "Proxyclick customer application"
   },
   "lastModifiedAt": "2015-01-12T15:50:58Z",
   "checkinNotificationType": "FIRST_LAST",
   "checkinNotificationUsers": null,
   "checkoutNotificationUsers": null
}
```

This endpoint creates a new meeting and retrieve the newly created meeting.

### HTTP Request

`POST https://api.proxyclick.com/app/<companyId>/vm/meetings`

### URL Parameters

Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
companyId | true | string | The id of the company for which the meeting needs to be created

###  Body Parameters (meeting)

Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
title | true | string | the title of the meeting (usually a concatenation of visitor firstname and lastname)
description | false | string | the description of the meeting
hostId | true | string | the id of the host of the meeting
userIds | false | array | an array of user ids attending the meeting 
visitors | false | array | an array of visitor object(s), see below for more info
startAt | true | string | start date of meeting (formated as follows : "2015-01-12T15:00:00+01:00")
endAt | true | string | end date of meeting (formated as follows : "2015-01-12T15:00:00+01:00")
recurrence | false | object | recurrence
checkinNotificationUsers | false | array | an array of user ids who will be notified upon visitor(s) checkin
checkoutNotificationUsers | false | array | an array of user ids who will be notified upon visitor(s) checkout 

> Example of a meeting

```json
{ "title": "John Doe", "startAt": "2015-01-12T15:00:00+01:00", "endAt": "2015-01-12T17:00:00+01:00", "hostId": "US-G606", "checkinNotificationUsers" : [], "checkoutNotificationUsers" : [], "visitors":[ { "firstName":"John", "lastName":"Doe", "email":"johndoe@yopmail.com", "phone":"", "mobile":"", "companyName":"Mega corporate ", "function":"", "language":"fr", "licensePlate":"" , "about":"", "birthday":"", "frequent": "0", "token": "", "smsReminder" : 0, "mailReminder" : 1 } ] }
```

### Body Parameters (visitors)

The array of visitor contained in the parameters of the meeting are the following:


Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
firstName | true | string | the visitor's firstname
lastName | true | string | the visitor's lastname
email | false | string | the visitor's email address
phone | false | string | the visitor's phone number (international format)
mobile | false | string | the visitor's mobile number (international format)
companyName | false | string | the visitor's company name
function | false | string | the visitor's function
language | false | string | the visitor's language (must be one of the available languages of application) 
licensePlate | false | string | the visitor's car license plate
about | false | string | some information about the visitor
smsReminder | false | boolean | flag to send sms invitation to visitor (only if mobile number is filled in)
mailReminder | false | boolean | flag to send email invitation to visitor (only if email address is filled in)

> Example of a visitors' array

```json
[ { "firstName":"John", "lastName":"Doe", "email":"johndoe@yopmail.com", "phone":"", "mobile":"", "companyName":"Mega corporate ", "function":"", "language":"fr", "licensePlate":"" , "about":"", "birthday":"", "frequent": "0", "token": "", "smsReminder" : 0, "mailReminder" : 1 } ]
```

# Visitors

## Visitor model

A visitor object contains the following fields


Attribute | Type | Description
--------- | ---- | -----------
object | string | value is "visitor" 


# Tickets

## Ticket model

A ticket object contains the following fields

Attribute | Type | Description
--------- | ---- | -----------
object | string | value is "ticket"
id | string | the id of the ticket
reference | string | the reference of the ticket
title | string | the title of the ticket
description | string | the description of the ticket
company | object | the company object of the ticket
creator | object | the creator (user) object of the ticket
notifier | object | the notifier (user) object of the ticket
category | object | the category object of the ticket 
priority | object | the priority object of the ticket
status | object | the status object of the ticket
agent | object | the agent object of the ticket
supplier | object | the supplier object of the ticket
supplierLastRead | timestamp | the last date the supplier read the ticket


```json
{
         "object": "ticket",
         "type": "Ticket",
         "id": "T-LX167",
         "reference": null,
         "title": "ffff",
         "description": "sqdfsqfqsfd",
         "company": {
            "object": "corporate",
            "id": "CO-C202",
            "reference": null,
            "name": "L'Oreal",
            "timezone": "Europe/Brussels",
            "locale": "en-US",
            "phone": "+12125551423",
            "logoUrl": "http://api-local.proxyclick.com/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6DD1A4A804D241715CCCC8E08C9CEFC13E1ECD4AA02DD014116D71ED8C8/2-192x53-la.png",
            "createdAt": "2014-01-07T09:05:31Z",
            "lastModifiedAt": "2015-01-14T16:18:17Z",
            "countryCode": "BE",
            "latitude": 50.680992,
            "longitude": 4.39579,
            "status": "ACTIVATED"
         },
         "creator": {
            "object": "user",
            "id": "US-G606",
            "firstname": "Stephen",
            "lastname": "Allen",
            "companyName": "L'Oreal",
            "email": "svantroyen@proxyclick.com",
            "phone": "023333201",
            "mobile": "+442077774331",
            "language": {
               "code": "en",
               "name": "English",
               "displayName": "English"
            },
            "pictureUrl": "http://api-local.proxyclick.com/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D2DD514D8F4A771000CECD8A10D4CFE00CE1FEC5AA09D50B431ED50982/6-120x118-la.png",
            "createdAt": "2014-01-07T09:05:31Z",
            "lastModifiedAt": "2015-01-21T11:02:31Z"
         },
         "notifier": {
            "object": "user",
            "id": "US-G606",
            "firstname": "Stephen",
            "lastname": "Allen",
            "companyName": "L'Oreal",
            "email": "svantroyen@proxyclick.com",
            "phone": "023333201",
            "mobile": "+442077774331",
            "language": {
               "code": "en",
               "name": "English",
               "displayName": "English"
            },
            "pictureUrl": "http://api-local.proxyclick.com/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D2DD514D8F4A771000CECD8A10D4CFE00CE1FEC5AA09D50B431ED50982/6-120x118-la.png",
            "createdAt": "2014-01-07T09:05:31Z",
            "lastModifiedAt": "2015-01-21T11:02:31Z"
         },
         "category": null,
         "priority": {
            "object": "priority",
            "id": 2,
            "value": "Medium"
         },
         "status": {
            "object": "status",
            "id": 1,
            "action": "unqualify",
            "value": "Requested"
         },
         "agent": null,
         "supplier": null,
         "supplierLastReadAt": null,
         "supplierLastNotificationSentAt": null,
         "dueAt": null,
         "reopened": false,
         "archived": false,
         "favorite": false,
         "commentCount": 0,
         "logCount": 1,
         "attachmentCount": 0,
         "relatedTicketCount": 0,
         "customFields": null,
         "createdAt": "2015-01-05T10:51:42Z",
         "lastStatusChangedAt": "2015-01-05T10:51:42Z",
         "lastModifiedAt": "2015-01-05T10:51:42Z",
         "sendRequesterSolved": 1,
         "rating": null
      }
```

## Get All tickets

```curl
curl "https://api.proxyclick.com/app/<companyId>/sd/tickets"
  -H "Authorization: Bearer <accessToken>"
```

```python
import urllib2

headers = {'Authorization': 'Bearer <accessToken>'}

url = 'https://api.proxyclick.com/app/<companyId>/sd/tickets'      
req = urllib2.Request(url, None, headers)

resp = urllib2.urlopen(req).read()
```

```php
$service_url = 'https://api.proxyclick.com/app/<companyId>/sd/tickets';
$curl = curl_init($service_url);
$curl_post_data = array("Authorization" => 'Bearer <accessToken>');

curl_setopt($curl, CURLOPT_RETURNTRANSFER, true);
curl_setopt($curl, CURLOPT_POST, true);
curl_setopt($curl, CURLOPT_POSTFIELDS, $curl_post_data);
$curl_response = curl_exec($curl);
curl_close($curl);
```

> The above command returns JSON structured like this:

```json
{
   "total": 22,
   "limit": 10,
   "tickets": [
      {
         "object": "ticket",
         "type": "Ticket",
         "id": "T-KG228",
         "reference": null,
         "title": "titre pour voir",
         "description": "description",
         "company": {
            "object": "corporate",
            "id": "CO-C202",
            "reference": null,
            "name": "Ecode23",
            "timezone": "Europe/Brussels",
            "locale": "fr-BE",
            "phone": "+323333201",
            "logoUrl": "http://api-local.proxyclick.com/documents/0D4B68F829CE53D1E9BBCB33C3D4D7C19A20AC04FE29A5E726C28AA8A5AA96D689E8EADAEBC6D12665D0D8514D8F4A771000CECD8A10D4CFE00FE6FEC5AF09D20B4319DC0982/2-192x125-la.png",
            "createdAt": "2014-01-07T09:05:31Z",
            "lastModifiedAt": "2015-01-15T10:29:45Z",
            "countryCode": "BE",
            "latitude": 50.681145,
            "longitude": 4.395756,
            "status": "ACTIVATED"
         },
         "creator": {
            "object": "user",
            "id": "US-G606",
            "firstname": "Stéphane",
            "lastname": "Vantroyen",
            "companyName": "Ecode23",
            "email": "svantroyen@proxyclick.com",
            "phone": "+3223333201",
            "mobile": "+32473170878",
            "language": {
               "code": "en",
               "name": "English",
               "displayName": "English"
            },
            "pictureUrl": "http://api-local.proxyclick.com/documents/0D4B68F829CE53D1E9BBCB33C3D4D7C19A20AC04FE29A5E726C28AA8A5AA96D689E8EADAEBC6D12665D0DA514D8F4A771000CECD8A10D4CFE00FE6FEC5AF09D20B4319DC0982/6-120x118-la.png",
            "createdAt": "2014-01-07T09:05:31Z",
            "lastModifiedAt": "2014-12-11T10:29:36Z"
         },
         "notifier": {
            "object": "user",
            "id": "US-G606",
            "firstname": "Stéphane",
            "lastname": "Vantroyen",
            "companyName": "Ecode23",
            "email": "svantroyen@proxyclick.com",
            "phone": "+3223333201",
            "mobile": "+32473170878",
            "language": {
               "code": "en",
               "name": "English",
               "displayName": "English"
            },
            "pictureUrl": "http://api-local.proxyclick.com/documents/0D4B68F829CE53D1E9BBCB33C3D4D7C19A20AC04FE29A5E726C28AA8A5AA96D689E8EADAEBC6D12665D0DA514D8F4A771000CECD8A10D4CFE00FE6FEC5AF09D20B4319DC0982/6-120x118-la.png",
            "createdAt": "2014-01-07T09:05:31Z",
            "lastModifiedAt": "2014-12-11T10:29:36Z"
         },
         "category": null,
         "priority": {
            "object": "priority",
            "id": 2,
            "value": "Medium"
         },
         "status": {
            "object": "status",
            "id": 1,
            "action": "unqualify",
            "value": "Requested"
         },
         "agent": null,
         "supplier": null,
         "supplierLastReadAt": null,
         "supplierLastNotificationSentAt": null,
         "dueAt": null,
         "reopened": false,
         "archived": false,
         "favorite": false,
         "commentCount": 0,
         "logCount": 1,
         "attachmentCount": 0,
         "relatedTicketCount": 0,
         "customFields": null,
         "createdAt": "2014-12-16T21:40:56Z",
         "lastStatusChangedAt": "2014-12-16T21:40:56Z",
         "lastModifiedAt": "2014-12-16T21:40:56Z",
         "sendRequesterSolved": 1,
         "rating": null
      },...]}
```

This endpoint retrieves all tickets of a company.

### HTTP Request

`GET https://api.proxyclick.com/app/<companyId>/sd/tickets`

### URL Parameters

Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
companyId | true | string | The id of the company for which the tickets need to be retrieved


### Body Parameters

Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
sortBy | false | string | the sorting type of the list of tickets (default: activity)
sort | false | string | the sorting order of the list of tickets (default: desc)
page | false | numeric | the page number to start the list with (default: 1)
pageSize | false | numeric | the number of tickets to retrieve per page (default: 10)
q | false | string | the filter to be used when retrieving the list of tickets. It will be used to check the ticket title, ticket id or the ticket description
status | false | string | the status of the ticket 
agentId | false | string| the id of the agent assigned to the ticket 
priority | false | numeric | the priority of the ticket
category | false | numeric | the category of the ticket 
supplierId | false | string | the id of the supplier of the ticket
mode | false | string | if specified to "me", the list will only contain the tickets created by the current user (not really in situation of api use right???)
dueDateFrom | false | date | the result will only include tickets with due date starting from this date
dueDateTo | false | date | the result will only include tickets with due date ending at this date



## Get a Specific ticket

```curl
curl "http://example.com/api/kittens/3"
  -H "Authorization: meowmeowmeow"
```

```python
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```php
import 'kittn'

api = Kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

> The above command returns JSON structured like this:

```json
{
   "object": "meeting",
   "id": "M-VJ476",
   "uid": "84CF7EBA-A81F-4028-A46428F93784CC49",
   "occurrenceId": null,
   "company": {
      "object": "corporate",
      "id": "CO-C202",
      "reference": null,
      "name": "L'Oreal",
      "timezone": "Europe/Brussels",
      "locale": "en-US",
      "phone": "+12125551423",
      "logoUrl": "http://api-local.proxyclick.com/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6DD1A4A804D241715CCCC8E08C9CEFC13E2ECD4AA06DD074116D51DD8C8/2-192x53-la.png",
      "createdAt": "2014-01-07T09:05:31Z",
      "lastModifiedAt": "2015-01-06T11:45:51Z",
      "countryCode": "BE",
      "latitude": 50.680992,
      "longitude": 4.39579,
      "status": "ACTIVATED"
   },
   "title": "John Doe",
   "description": null,
   "startAt": "2015-01-12T15:00:00+01:00",
   "endAt": "2015-01-12T17:00:00+01:00",
   "host": {
      "object": "user",
      "id": "US-G606",
      "firstname": "Yo",
      "lastname": "Da",
      "companyName": "L'Oreal",
      "email": "svantroyen@proxyclick.com",
      "phone": "023333201",
      "mobile": "+442077774331",
      "language": {
         "code": "fr",
         "name": "français",
         "displayName": "français"
      },
      "pictureUrl": "http://api-local.proxyclick.com/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D2DD514D8F4A771000CECD8A10D4CFE00FE1FEC5AE09D30B431CD60982/6-120x118-la.png",
      "createdAt": "2014-01-07T09:05:31Z",
      "lastModifiedAt": "2014-12-16T14:44:09Z",
      "function": "web developer",
      "about": "Star wars fan, new technologies addict",
      "licensePlate": "aaaaaaa",
      "birthday": null,
      "entryDate": null,
      "lastLoggedAt": "2015-01-12T09:22:06Z",
      "assistant": {
         "object": "user",
         "id": "US-KP935",
         "firstname": "trterte",
         "lastname": "eterterte",
         "companyName": "Ecode23",
         "email": "svtff@yopmail.com",
         "phone": "",
         "mobile": "",
         "language": {
            "code": "fr",
            "name": "français",
            "displayName": "français"
         },
         "pictureUrl": "http://static-local.proxyclick.com:80/user/profile/ppic-defaultuser-man.png",
         "createdAt": "2014-04-16T14:42:54Z",
         "lastModifiedAt": "2014-05-07T13:43:35Z"
      },
      "isAssistantOf": [
         {
            "object": "user",
            "id": "US-KQ036",
            "firstname": "retstet",
            "lastname": "hfhfhfhf",
            "companyName": "Ecode23",
            "email": "resvt@yopmail.com",
            "phone": "",
            "mobile": "",
            "language": {
               "code": "fr",
               "name": "français",
               "displayName": "français"
            },
            "pictureUrl": "http://static-local.proxyclick.com:80/user/profile/ppic-defaultuser-man.png",
            "createdAt": "2014-04-16T14:44:43Z",
            "lastModifiedAt": "2014-12-16T14:44:09Z"
         }
      ]
   },
   "users": null,
   "visitors": [
      {
         "object": "visitor",
         "id": "V-EQK930",
         "firstname": "John",
         "lastname": "Doe",
         "companyName": "Mega corporate",
         "email": "johndoe@yopmail.com",
         "phone": "",
         "mobile": "",
         "mobileStatus": "UNKNOWN",
         "language": {
            "code": "fr",
            "name": "français",
            "displayName": "français"
         },
         "pictureUrl": "http://static-local.proxyclick.com:80/_/app/img/vm-visitor-img-placeholder-man.png",
         "function": null,
         "about": null,
         "licensePlate": null,
         "birthday": null,
         "frequent": false,
         "attachmentCount": 0,
         "customFields": null,
         "smsReminder": 0,
         "mailReminder": 0
      }
   ],
   "recurrence": null,
   "timezone": "Europe/Brussels",
   "createdAt": "2015-01-12T14:53:41Z",
   "createdBy": {
      "type": "USER",
      "object": "user",
      "id": "US-G606",
      "name": "Yo Da"
   },
   "createdVia": {
      "type": "APPLICATION",
      "name": "Proxyclick customer application"
   },
   "lastModifiedAt": "2015-01-12T14:53:41Z",
   "checkinNotificationType": "FIRST_LAST",
   "checkinNotificationUsers": null,
   "checkoutNotificationUsers": null
}
```

This endpoint retrieves a specific ticket.

### HTTP Request

`GET https://api.proxyclick.com/app/<companyId>/sd/tickets/<ticketId>`

### URL Parameters

Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
companyId | true | string | The id of the company for which the meeting needs to be retrieved
ticketId | true | string | The ID of the ticket to retrieve


## Create a ticket

```curl
curl "http://example.com/api/kittens/3"
  -H "Authorization: meowmeowmeow"
```

```python
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```php
import 'kittn'

api = Kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

> The above command returns JSON structured like this:

```json
{
   "object": "meeting",
   "id": "M-VK577",
   "uid": "5F6669B5-C5E2-4716-A4758FF637DA922D",
   "occurrenceId": null,
   "company": {
      "object": "corporate",
      "id": "CO-C202",
      "reference": null,
      "name": "L'Oreal",
      "timezone": "Europe/Brussels",
      "locale": "en-US",
      "phone": "+12125551423",
      "logoUrl": "http://api-local.proxyclick.com/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6DD1A4A804D241715CCCC8E08C9CEFC13E2ECD4AA06DD064916D016D8C8/2-192x53-la.png",
      "createdAt": "2014-01-07T09:05:31Z",
      "lastModifiedAt": "2015-01-06T11:45:51Z",
      "countryCode": "BE",
      "latitude": 50.680992,
      "longitude": 4.39579,
      "status": "ACTIVATED"
   },
   "title": "John Doel",
   "description": null,
   "startAt": "2015-01-12T16:00:00+01:00",
   "endAt": "2015-01-12T18:00:00+01:00",
   "host": {
      "object": "user",
      "id": "US-G606",
      "firstname": "Yo",
      "lastname": "Da",
      "companyName": "L'Oreal",
      "email": "svantroyen@proxyclick.com",
      "phone": "023333201",
      "mobile": "+442077774331",
      "language": {
         "code": "fr",
         "name": "français",
         "displayName": "français"
      },
      "pictureUrl": "http://api-local.proxyclick.com/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D2DD514D8F4A771000CECD8A10D4CFE00FE1FEC5AE09D2034319DD0982/6-120x118-la.png",
      "createdAt": "2014-01-07T09:05:31Z",
      "lastModifiedAt": "2014-12-16T14:44:09Z",
      "function": "web developer",
      "about": "Star wars fan, new technologies addict",
      "licensePlate": "aaaaaaa",
      "birthday": null,
      "entryDate": null,
      "lastLoggedAt": "2015-01-12T09:22:06Z",
      "assistant": {
         "object": "user",
         "id": "US-KP935",
         "firstname": "trterte",
         "lastname": "eterterte",
         "companyName": "Ecode23",
         "email": "svtff@yopmail.com",
         "phone": "",
         "mobile": "",
         "language": {
            "code": "fr",
            "name": "français",
            "displayName": "français"
         },
         "pictureUrl": "http://static-local.proxyclick.com:80/user/profile/ppic-defaultuser-man.png",
         "createdAt": "2014-04-16T14:42:54Z",
         "lastModifiedAt": "2014-05-07T13:43:35Z"
      },
      "isAssistantOf": [
         {
            "object": "user",
            "id": "US-KQ036",
            "firstname": "retstet",
            "lastname": "hfhfhfhf",
            "companyName": "Ecode23",
            "email": "resvt@yopmail.com",
            "phone": "",
            "mobile": "",
            "language": {
               "code": "fr",
               "name": "français",
               "displayName": "français"
            },
            "pictureUrl": "http://static-local.proxyclick.com:80/user/profile/ppic-defaultuser-man.png",
            "createdAt": "2014-04-16T14:44:43Z",
            "lastModifiedAt": "2014-12-16T14:44:09Z"
         }
      ]
   },
   "users": null,
   "visitors": [
      {
         "object": "visitor",
         "id": "V-EQL031",
         "firstname": "John",
         "lastname": "Doel",
         "companyName": "Mega corporate",
         "email": "johndoel@yopmail.com",
         "phone": "",
         "mobile": "",
         "mobileStatus": "UNKNOWN",
         "language": {
            "code": "fr",
            "name": "français",
            "displayName": "français"
         },
         "pictureUrl": "http://static-local.proxyclick.com:80/_/app/img/vm-visitor-img-placeholder-man.png",
         "function": null,
         "about": null,
         "licensePlate": null,
         "birthday": null,
         "frequent": false,
         "attachmentCount": 0,
         "customFields": null,
         "smsReminder": 0,
         "mailReminder": 0
      }
   ],
   "recurrence": null,
   "timezone": "Europe/Brussels",
   "createdAt": "2015-01-12T15:50:58Z",
   "createdBy": {
      "type": "USER",
      "object": "user",
      "id": "US-G606",
      "name": "Yo Da"
   },
   "createdVia": {
      "type": "APPLICATION",
      "name": "Proxyclick customer application"
   },
   "lastModifiedAt": "2015-01-12T15:50:58Z",
   "checkinNotificationType": "FIRST_LAST",
   "checkinNotificationUsers": null,
   "checkoutNotificationUsers": null
}
```

This endpoint creates a new ticket and retrieve the newly created ticket.

### HTTP Request

`POST https://api.proxyclick.com/app/<companyId>/sd/tickets`

### URL Parameters

Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
companyId | true | string | The id of the company for which the ticket needs to be created

###  Body Parameters 

Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
reference | false | string | the reference of the ticket
title | true | string | the title of the ticket
description | false | string | the description of the ticket
creatorId | false | string | the id of the creator of the ticket
notifierId | true | string | the id of the notifier of the ticket
agentId | false | string | the id of the agent assigned to the ticket
supplierId | false | string | the id of the supplier defined for the ticket
categoryId | false | string | the id of the category of the ticket
priorityId | false | string | the id of the priority of the ticket
dueDate | false | date | the due date of the ticket
sendRequesterSolved | false | boolean | flag to send a notification to requester of the ticket when the ticket is solved
sendRequesterCopy | false | boolean | flag to send a notification with details of ticket to the requester
customFields | false | array | the custom fields of the ticket

> Example of a ticket

```json
{ "title": "John Doe", "startAt": "2015-01-12T15:00:00+01:00", "endAt": "2015-01-12T17:00:00+01:00", "hostId": "US-G606", "checkinNotificationUsers" : [], "checkoutNotificationUsers" : [], "visitors":[ { "firstName":"John", "lastName":"Doe", "email":"johndoe@yopmail.com", "phone":"", "mobile":"", "companyName":"Mega corporate ", "function":"", "language":"fr", "licensePlate":"" , "about":"", "birthday":"", "frequent": "0", "token": "", "smsReminder" : 0, "mailReminder" : 1 } ] }
```

# Companies

## Company model

### Company object




