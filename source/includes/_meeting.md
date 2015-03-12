# Meetings

## Meeting model

### Meeting object

> Example of meeting object

```json
	{
      "object": "meeting",
      "id": "M-YW863",
      "uid": "217193FA-3383-4C83-9D61EDB07A69A844",
      "occurrenceId": "2015-02-18T16:00:00+01:00",
      "company": {
         "object": "corporate",
         "id": "CO-C202",
         "reference": null,
         "name": "SunFix",
         "timezone": "Europe/Brussels",
         "locale": "fr-BE",
         "phone": "+12125551423",
         "logoOriginal": "http://...",
         "logo24": "http://...",
         "logo36": "http://...",
         "logo64": "http://...",
         "logo128": "http://...",
         "logo192": "http://...",
         "createdAt": "2014-01-07T09:05:31Z",
         "lastModifiedAt": "2015-02-19T09:32:53Z",
         "countryCode": "BE",
         "latitude": 40.832176,
         "longitude": -74.111769,
         "status": "ACTIVATED"
      },
      "title": "shannon moore",
      "description": null,
      "startAt": "2015-02-18T16:00:00+01:00",
      "endAt": "2015-02-18T18:00:00+01:00",
      "host": {
         "object": "user",
         "id": "US-G606",
         "firstname": "Jordan",
         "lastname": "Gray",
         "companyName": "SunFix",
         "email": "jordan.gray@sunfix.com",
         "phone": "+447484396025",
         "mobile": "+447484396026",
         "language": {
            "code": "en",
            "name": "English",
            "displayName": "English"
         },
         "pictureOriginal": "http://...",
         "picture24": "http://...",
         "picture36": "http://...",
         "picture64": "http://...",
         "picture128": "http://...",
         "picture192": "http://...",
         "createdAt": "2014-01-07T09:05:31Z",
         "lastModifiedAt": "2015-02-18T14:52:51Z"
      },
      "visitors": [
         {
            "object": "visitor",
            "id": "V-EUA620",
            "firstname": "shannon",
            "lastname": "moore",
            "companyName": "Altran corp",
            "email": "shannon.moore@@sunfix.com",
            "phone": "",
            "mobile": "+12154789522",
            "mobileStatus": "UNKNOWN",
            "language": {
               "code": "en",
               "name": "English",
               "displayName": "English"
            },
            "pictureOriginal": "http://...",
            "picture24": "http://...",
            "picture36": "http://...",
            "picture64": "http://...",
            "picture128": "http://...",
            "picture192": "http://...",
            "function": null,
            "about": null,
            "licensePlate": null,
            "birthday": null,
            "frequent": false,
            "attachmentCount": 0,
            "customFields": [
               {
                  "object": "customFieldValue",
                  "id": 17,
                  "name": "passport number",
                  "value": "xxxx-yyyy-zzzz"
               }
            ],
            "smsReminder": 1,
            "mailReminder": 0
         }
      ],
      "recurrence": null,
      "timezone": "Europe/Brussels",
      "createdAt": "2015-02-18T14:57:32Z",
      "lastModifiedAt": "2015-02-18T14:57:30Z",
      "checkinNotificationUsers": null,
   	  "checkoutNotificationUsers": null,
      "checkoutReminderNotificationUsers": null
   }
   ```

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
lastModifiedAt | timestamp | the date of last modification of the meeting
checkinNotificationType | string | the type of notification of the meeting (for group meetings)
checkinNotificationUsers | list of objects | the list of user objects who will receive checkin notification for this meeting
checkoutReminderNotificationUsers | list of objects | the list of user objects who will receive checkout reminder notification for this meeting



## Get All meetings

```shell
curl "https:/api.proxyclick.com/v1/app/<companyId>/vm/meetings?from=<startDate>&to=<endDate>"
  -H "Authorization: Bearer <accessToken>"
```

> The above command returns JSON structured like this:

```json
[    
    {
      "object": "meeting",
      "id": "M-YW863",
      "uid": "217193FA-3383-4C83-9D61EDB07A69A844",
      "occurrenceId": "2015-02-18T16:00:00+01:00",
      "company": {
         "object": "corporate",
         "id": "CO-C202",
         "reference": null,
         "name": "SunFix",
         "timezone": "Europe/Brussels",
         "locale": "fr-BE",
         "phone": "+12125551423",
         "logoOriginal": "http://...",
         "logo24": "http://...",
         "logo36": "http://...",
         "logo64": "http://...",
         "logo128": "http://...",
         "logo192": "http://...",
         "createdAt": "2014-01-07T09:05:31Z",
         "lastModifiedAt": "2015-02-19T09:32:53Z",
         "countryCode": "BE",
         "latitude": 40.832176,
         "longitude": -74.111769,
         "status": "ACTIVATED"
      },
      "title": "shannon moore",
      "description": null,
      "startAt": "2015-02-18T16:00:00+01:00",
      "endAt": "2015-02-18T18:00:00+01:00",
      "host": {
         "object": "user",
         "id": "US-G606",
         "firstname": "Jordan",
         "lastname": "Gray",
         "companyName": "SunFix",
         "email": "jordan.gray@sunfix.com",
         "phone": "+447484396025",
         "mobile": "+447484396026",
         "language": {
            "code": "en",
            "name": "English",
            "displayName": "English"
         },
         "pictureOriginal": "http://...",
         "picture24": "http://...",
         "picture36": "http://...",
         "picture64": "http://...",
         "picture128": "http://...",
         "picture192": "http://...",
         "createdAt": "2014-01-07T09:05:31Z",
         "lastModifiedAt": "2015-02-18T14:52:51Z"
      },
      "visitors": [
         {
            "object": "visitor",
            "id": "V-EUA620",
            "firstname": "shannon",
            "lastname": "moore",
            "companyName": "Altran corp",
            "email": "shannon.moore@@sunfix.com",
            "phone": "",
            "mobile": "+12154789522",
            "mobileStatus": "UNKNOWN",
            "language": {
               "code": "en",
               "name": "English",
               "displayName": "English"
            },
            "pictureOriginal": "http://...",
            "picture24": "http://...",
            "picture36": "http://...",
            "picture64": "http://...",
            "picture128": "http://...",
            "picture192": "http://...",
            "function": null,
            "about": null,
            "licensePlate": null,
            "birthday": null,
            "frequent": false,
            "attachmentCount": 0,
            "customFields": [
               {
                  "object": "customFieldValue",
                  "id": 17,
                  "name": "passport number",
                  "value": "xxxx-yyyy-zzzz"
               }
            ],
            "smsReminder": 1,
            "mailReminder": 0
         }
      ],
      "recurrence": null,
      "timezone": "Europe/Brussels",
      "createdAt": "2015-02-18T14:57:32Z",
      "lastModifiedAt": "2015-02-18T14:57:30Z",
      "checkinNotificationUsers": null,
   	  "checkoutNotificationUsers": null,
      "checkoutReminderNotificationUsers": null
   },
    ...
]
```

This endpoint retrieves all meetings of a company.

### HTTP Request

`GET https:/api.proxyclick.com/v1/app/<companyId>/vm/meetings?from=<startDate>&to=<endDate>`

### Query Parameters

Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
companyId | true | string | The id of the company for which the meetings need to be retrieved
from | true | date | the result will only include meetings starting from this date
to | true | date | the result will only include meetings ending at this date



## Get a Specific meeting

```shell
curl "https:/api.proxyclick.com/v1/app/<companyId>/vm/meetings/<meetingId>"
  -H "Authorization: Bearer <accessToken>"
```

> The above command returns JSON structured like this:

```json
{
      "object": "meeting",
      "id": "M-YW863",
      "uid": "217193FA-3383-4C83-9D61EDB07A69A844",
      "occurrenceId": "2015-02-18T16:00:00+01:00",
      "company": {
         "object": "corporate",
         "id": "CO-C202",
         "reference": null,
         "name": "SunFix",
         "timezone": "Europe/Brussels",
         "locale": "fr-BE",
         "phone": "+12125551423",
         "logoOriginal": "http://...",
         "logo24": "http://...",
         "logo36": "http://...",
         "logo64": "http://...",
         "logo128": "http://...",
         "logo192": "http://...",
         "createdAt": "2014-01-07T09:05:31Z",
         "lastModifiedAt": "2015-02-19T09:32:53Z",
         "countryCode": "BE",
         "latitude": 40.832176,
         "longitude": -74.111769,
         "status": "ACTIVATED"
      },
      "title": "shannon moore",
      "description": null,
      "startAt": "2015-02-18T16:00:00+01:00",
      "endAt": "2015-02-18T18:00:00+01:00",
      "host": {
         "object": "user",
         "id": "US-G606",
         "firstname": "Jordan",
         "lastname": "Gray",
         "companyName": "SunFix",
         "email": "jordan.gray@sunfix.com",
         "phone": "+447484396025",
         "mobile": "+447484396026",
         "language": {
            "code": "en",
            "name": "English",
            "displayName": "English"
         },
         "pictureOriginal": "http://...",
         "picture24": "http://...",
         "picture36": "http://...",
         "picture64": "http://...",
         "picture128": "http://...",
         "picture192": "http://...",
         "createdAt": "2014-01-07T09:05:31Z",
         "lastModifiedAt": "2015-02-18T14:52:51Z"
      },
      "visitors": [
         {
            "object": "visitor",
            "id": "V-EUA620",
            "firstname": "shannon",
            "lastname": "moore",
            "companyName": "Altran corp",
            "email": "shannon.moore@@sunfix.com",
            "phone": "",
            "mobile": "+12154789522",
            "mobileStatus": "UNKNOWN",
            "language": {
               "code": "en",
               "name": "English",
               "displayName": "English"
            },
            "pictureOriginal": "http://...",
            "picture24": "http://...",
            "picture36": "http://...",
            "picture64": "http://...",
            "picture128": "http://...",
            "picture192": "http://...",
            "function": null,
            "about": null,
            "licensePlate": null,
            "birthday": null,
            "frequent": false,
            "attachmentCount": 0,
            "customFields": [
               {
                  "object": "customFieldValue",
                  "id": 17,
                  "name": "passport number",
                  "value": "xxxx-yyyy-zzzz"
               }
            ],
            "smsReminder": 1,
            "mailReminder": 0
         }
      ],
      "recurrence": null,
      "timezone": "Europe/Brussels",
      "createdAt": "2015-02-18T14:57:32Z",
      "lastModifiedAt": "2015-02-18T14:57:30Z",
      "checkinNotificationUsers": null,
   	  "checkoutNotificationUsers": null,
      "checkoutReminderNotificationUsers": null
   }
```

This endpoint retrieves a specific meeting.


### HTTP Request


`GET https:/api.proxyclick.com/v1/app/<companyId>/vm/meetings/<meetingId>`


### Query Parameters


Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
companyId | true | string | The id of the company for which the meeting needs to be retrieved
meetingId | true | string | The id of the meeting to retrieve



## Create a meeting


```shell
$ curl https:/api.proxyclick.com/v1/app/<companyId>/vm/meetings/ \
-X POST \
-H "Authorization: Bearer <accessToken>" \	
-H 'Accept: application/json' \
-H 'Content-Type: application/json' -d '
{
   "startAt": "",
   "hostId": "",
   "endAt": "",
   "recurrence": {},
   "title": "",
   "description": "",
   "visitors": [],
   "userIds": [],
   "checkinNotificationType": "",
   "checkoutNotificationUsers": [],
   "checkoutReminderNotificationUsers": [],
   "checkinNotificationUsers": []
}'
```     

This endpoint creates a new meeting and retrieves the newly created meeting.



### HTTP Request

`POST https:/api.proxyclick.com/v1/app/<companyId>/vm/meetings`



### Query Parameters

Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
companyId | true | string | The id of the company for which the meeting needs to be created



###  Body Parameters (meeting)

Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
title | true | string | the title of the meeting (usually a concatenation of visitor firstname and lastname)
description | false | string | the description of the meeting
hostId | true | string | the id of the host of the meeting
visitors | false | array | an array of visitor object(s), see below for more info
startAt | true | string | start date of meeting (formated as follows : "2015-01-12T15:00:00+01:00")
endAt | true | string | end date of meeting (formated as follows : "2015-01-12T15:00:00+01:00")
recurrence | false | object | the recurrence object of the meeting, see below for more info
checkinNotificationUsers | false | array | an array of user ids who will be notified upon visitor(s) checkin
checkoutReminderNotificationUsers | false | array | an array of user ids who will be reminded about visitor(s) checkout (if checkout has been done within given time)
checkoutNotificationUsers  | false | array | an array of user ids who will be notified upon visitor(s) checkout 

> Example of a meeting

```json
{
    "title": "John Doe",
    "startAt": "2015-01-12T15:00:00+01:00",
    "endAt": "2015-01-12T17:00:00+01:00",
    "hostId": "US-G606",
    "checkinNotificationUsers": [],
    "checkoutNotificationUsers": [],
    "checkoutReminderNotificationUsers": [],
    "visitors": [
        {
            "firstName": "John",
            "lastName": "Doe",
            "email": "johndoe@sunrise.com",
            "phone": "",
            "mobile": "",
            "companyName": "SunRise ltd",
            "function": "",
            "language": "fr",
            "licensePlate": "",
            "about": "",
            "birthday": "",
            "frequent": "0",
            "token": "",
            "smsReminder": 0,
            "mailReminder": 1
        }
    ]
}
```

### Body Parameters (recurrence)

The recurrence is an object containing following properties, as defined by rfc5545 (see <a href="https://tools.ietf.org/html/rfc5545" target="_blank">https://tools.ietf.org/html/rfc5545</a> for more details):


Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
rrule | true | string | the recurrence rule defining the recurrence of the meeting
exrule | false | string | the recurrence rule defining the exceptions in the recurrence rule of the meeting
rdate | false | string | the date(s) of occurrence(s) to be included (added) to the recurrence of the meeting
exdate | false | string | the date(s) of occurrence(s) to be excluded (removed) from the recurrence of the meeting


> Example of a recurrence object 

```json
	{"rrule" : "FREQ=DAILY;BYDAY=MO,TU,WE,TH,FR;UNTIL=20150315T230000Z"}
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
language | false | string | the visitor's language (must be one of the available languages supported by the Proxyclick application)
licensePlate | false | string | the visitor's car license plate
about | false | string | some information about the visitor
smsReminder | false | boolean | flag to send SMS invitation to visitor (only if mobile number is filled in)
mailReminder | false | boolean | flag to send email invitation to visitor (only if email address is filled in)

> Example of a visitors' array

```json
[
    {
        "firstName": "John",
        "lastName": "Doe",
        "email": "johndoe@sunrise.com",
        "phone": "",
        "mobile": "",
        "companyName": "SunRise ltd",
        "function": "",
        "language": "fr",
        "licensePlate": "",
        "about": "",
        "birthday": "",
        "frequent": "0",
        "token": "",
        "smsReminder": 0,
        "mailReminder": 1
    }
]
```

> The above command returns JSON structured like this:

```json
{
      "object": "meeting",
      "id": "M-YW863",
      "uid": "217193FA-3383-4C83-9D61EDB07A69A844",
      "occurrenceId": "2015-02-18T16:00:00+01:00",
      "company": {
         "object": "corporate",
         "id": "CO-C202",
         "reference": null,
         "name": "SunFix",
         "timezone": "Europe/Brussels",
         "locale": "fr-BE",
         "phone": "+12125551423",
         "logoOriginal": "http://...",
         "logo24": "http://...",
         "logo36": "http://...",
         "logo64": "http://...",
         "logo128": "http://...",
         "logo192": "http://...",
         "createdAt": "2014-01-07T09:05:31Z",
         "lastModifiedAt": "2015-02-19T09:32:53Z",
         "countryCode": "BE",
         "latitude": 40.832176,
         "longitude": -74.111769,
         "status": "ACTIVATED"
      },
      "title": "shannon moore",
      "description": null,
      "startAt": "2015-02-18T16:00:00+01:00",
      "endAt": "2015-02-18T18:00:00+01:00",
      "host": {
         "object": "user",
         "id": "US-G606",
         "firstname": "Jordan",
         "lastname": "Gray",
         "companyName": "SunFix",
         "email": "jordan.gray@sunfix.com",
         "phone": "+447484396025",
         "mobile": "+447484396026",
         "language": {
            "code": "en",
            "name": "English",
            "displayName": "English"
         },
         "pictureOriginal": "http://...",
         "picture24": "http://...",
         "picture36": "http://...",
         "picture64": "http://...",
         "picture128": "http://...",
         "picture192": "http://...",
         "createdAt": "2014-01-07T09:05:31Z",
         "lastModifiedAt": "2015-02-18T14:52:51Z"
      },
      "visitors": [
         {
            "object": "visitor",
            "id": "V-EUA620",
            "firstname": "shannon",
            "lastname": "moore",
            "companyName": "Altran corp",
            "email": "shannon.moore@@sunfix.com",
            "phone": "",
            "mobile": "+12154789522",
            "mobileStatus": "UNKNOWN",
            "language": {
               "code": "en",
               "name": "English",
               "displayName": "English"
            },
            "pictureOriginal": "http://...",
            "picture24": "http://...",
            "picture36": "http://...",
            "picture64": "http://...",
            "picture128": "http://...",
            "picture192": "http://...",
            "function": null,
            "about": null,
            "licensePlate": null,
            "birthday": null,
            "frequent": false,
            "attachmentCount": 0,
            "customFields": [
               {
                  "object": "customFieldValue",
                  "id": 17,
                  "name": "passport number",
                  "value": "xxxx-yyyy-zzzz"
               }
            ],
            "smsReminder": 1,
            "mailReminder": 0
         }
      ],
      "recurrence": null,
      "timezone": "Europe/Brussels",
      "createdAt": "2015-02-18T14:57:32Z",
      "lastModifiedAt": "2015-02-18T14:57:30Z",
      "checkinNotificationUsers": null,
   	  "checkoutNotificationUsers": null,
      "checkoutReminderNotificationUsers": null
   }
```

## Update a meeting

```shell
$ curl https:/api.proxyclick.com/v1/app/<companyId>/vm/meetings/<meetingId> \
-X PUT \
-H "Authorization: Bearer <accessToken>" \	
-H 'Accept: application/json' \
-H 'Content-Type: application/json' -d '
{
   "startAt": "",
   "hostId": "",
   "endAt": "",
   "recurrence": {},
   "title": "",
   "description": "",
   "visitors": [],
   "userIds": [],
   "checkinNotificationType": "",
   "checkoutNotificationUsers": [],
   "checkoutReminderNotificationUsers": [],
   "checkinNotificationUsers": []
}'
```     

This endpoint updates a meeting and retrieves the updated meeting.

<aside class="notice">
When a recurrent meeting needs to be updated, the process of might be different, see <a href="#note-about-meeting-recurrence">Note about meeting recurrence</a> for more information
</aside>


### HTTP Request

`PUT https:/api.proxyclick.com/v1/app/<companyId>/vm/meeting/<meetingId>`



### Query Parameters

Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
companyId | true | string | The id of the company for which the meeting needs to be updated
meetingId | true | string | The id of the meeting to be updated



###  Body Parameters (meeting)

Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
title | true | string | the title of the meeting (usually a concatenation of visitor firstname and lastname)
description | false | string | the description of the meeting
hostId | true | string | the id of the host of the meeting
visitors | false | array | an array of visitor object(s), see below for more info
startAt | true | string | start date of meeting (formated as follows : "2015-01-12T15:00:00+01:00")
endAt | true | string | end date of meeting (formated as follows : "2015-01-12T15:00:00+01:00")
recurrence | false | object | the recurrence object of the meeting, see below for more info
checkinNotificationUsers | false | array | an array of user ids who will be notified upon visitor(s) checkin
checkoutReminderNotificationUsers | false | array | an array of user ids who will be reminded about visitor(s) checkout (if checkout has been done within given time)
checkoutNotificationUsers  | false | array | an array of user ids who will be notified upon visitor(s) checkout 

> Example of a meeting

```json
{
    "title": "John Doe",
    "startAt": "2015-01-12T15:00:00+01:00",
    "endAt": "2015-01-12T17:00:00+01:00",
    "hostId": "US-G606",
    "checkinNotificationUsers": [],
    "checkoutNotificationUsers": [],
    "checkoutReminderNotificationUsers": [],
    "visitors": [
        {
            "firstName": "John",
            "lastName": "Doe",
            "email": "johndoe@sunrise.com",
            "phone": "",
            "mobile": "",
            "companyName": "SunRise ltd",
            "function": "",
            "language": "fr",
            "licensePlate": "",
            "about": "",
            "birthday": "",
            "frequent": "0",
            "token": "",
            "smsReminder": 0,
            "mailReminder": 1
        }
    ]
}
```

### Body Parameters (recurrence)

The recurrence is an object containing following properties, as defined by rfc5545 (see <a href="https://tools.ietf.org/html/rfc5545" target="_blank">https://tools.ietf.org/html/rfc5545</a> for more details):


Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
rrule | true | string | the recurrence rule defining the recurrence of the meeting
exrule | false | string | the recurrence rule defining the exceptions in the recurrence rule of the meeting
rdate | false | string | the date(s) of occurrence(s) to be included (added) to the recurrence of the meeting
exdate | false | string | the date(s) of occurrence(s) to be excluded (removed) from the recurrence of the meeting


> Example of a recurrence object 

```json
	{"rrule" : "FREQ=DAILY;BYDAY=MO,TU,WE,TH,FR;UNTIL=20150315T230000Z"}
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
language | false | string | the visitor's language (must be one of the available languages supported by the Proxyclick application)
licensePlate | false | string | the visitor's car license plate
about | false | string | some information about the visitor
smsReminder | false | boolean | flag to send SMS invitation to visitor (only if mobile number is filled in)
mailReminder | false | boolean | flag to send email invitation to visitor (only if email address is filled in)

> Example of a visitors' array

```json
[
    {
        "firstName": "John",
        "lastName": "Doe",
        "email": "johndoe@sunrise.com",
        "phone": "",
        "mobile": "",
        "companyName": "SunRise ltd",
        "function": "",
        "language": "fr",
        "licensePlate": "",
        "about": "",
        "birthday": "",
        "frequent": "0",
        "token": "",
        "smsReminder": 0,
        "mailReminder": 1
    }
]
```

> The above command returns JSON structured like this:

```json
{
      "object": "meeting",
      "id": "M-YW863",
      "uid": "217193FA-3383-4C83-9D61EDB07A69A844",
      "occurrenceId": "2015-02-18T16:00:00+01:00",
      "company": {
         "object": "corporate",
         "id": "CO-C202",
         "reference": null,
         "name": "SunFix",
         "timezone": "Europe/Brussels",
         "locale": "fr-BE",
         "phone": "+12125551423",
         "logoOriginal": "http://...",
         "logo24": "http://...",
         "logo36": "http://...",
         "logo64": "http://...",
         "logo128": "http://...",
         "logo192": "http://...",
         "createdAt": "2014-01-07T09:05:31Z",
         "lastModifiedAt": "2015-02-19T09:32:53Z",
         "countryCode": "BE",
         "latitude": 40.832176,
         "longitude": -74.111769,
         "status": "ACTIVATED"
      },
      "title": "shannon moore",
      "description": null,
      "startAt": "2015-02-18T16:00:00+01:00",
      "endAt": "2015-02-18T18:00:00+01:00",
      "host": {
         "object": "user",
         "id": "US-G606",
         "firstname": "Jordan",
         "lastname": "Gray",
         "companyName": "SunFix",
         "email": "jordan.gray@sunfix.com",
         "phone": "+447484396025",
         "mobile": "+447484396026",
         "language": {
            "code": "en",
            "name": "English",
            "displayName": "English"
         },
         "pictureOriginal": "http://...",
         "picture24": "http://...",
         "picture36": "http://...",
         "picture64": "http://...",
         "picture128": "http://...",
         "picture192": "http://...",
         "createdAt": "2014-01-07T09:05:31Z",
         "lastModifiedAt": "2015-02-18T14:52:51Z"
      },
      "visitors": [
         {
            "object": "visitor",
            "id": "V-EUA620",
            "firstname": "shannon",
            "lastname": "moore",
            "companyName": "Altran corp",
            "email": "shannon.moore@@sunfix.com",
            "phone": "",
            "mobile": "+12154789522",
            "mobileStatus": "UNKNOWN",
            "language": {
               "code": "en",
               "name": "English",
               "displayName": "English"
            },
            "pictureOriginal": "http://...",
            "picture24": "http://...",
            "picture36": "http://...",
            "picture64": "http://...",
            "picture128": "http://...",
            "picture192": "http://...",
            "function": null,
            "about": null,
            "licensePlate": null,
            "birthday": null,
            "frequent": false,
            "attachmentCount": 0,
            "customFields": [
               {
                  "object": "customFieldValue",
                  "id": 17,
                  "name": "passport number",
                  "value": "xxxx-yyyy-zzzz"
               }
            ],
            "smsReminder": 1,
            "mailReminder": 0
         }
      ],
      "recurrence": null,
      "timezone": "Europe/Brussels",
      "createdAt": "2015-02-18T14:57:32Z",
      "lastModifiedAt": "2015-02-18T14:57:30Z",
      "checkinNotificationUsers": null,
   	  "checkoutNotificationUsers": null,
      "checkoutReminderNotificationUsers": null
   }
```


## Note about Meeting recurrence

### Updating a meeting with recurrence

When a meeting is recurrent, updating it can be slightly different than just using the update method described above. Two cases can happen :

1. The meeting has not started yet (start date is greater than time of update): use the update method as described above
2. The meeting has already started (at least one visit has occurred before the time of update): in this case, the meeting needs to be closed first (see 'Close a meeting' below), and recreated with the update values (see 'create a meeting' above).


## Close a meeting

When a recurrent meeting needs to be updated but has already started, it first needs to be closed, and then recreated with the update values.

```shell
$ curl https:/api.proxyclick.com/v1/app/<companyId>/vm/meeting/<meetingId>/close \
-X POST \
-H "Authorization: Bearer <accessToken>" \	
-H 'Accept: application/json' \
```     

This endpoint closes a meeting


### HTTP Request

`POST https:/api.proxyclick.com/v1/app/<companyId>/vm/meeting/<meetingId>/close`



### Query Parameters

Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
companyId | true | string | The id of the company for which the meeting needs to be closed
meetingId | true | string | The id of the meeting to be closed


## Delete a meeting

```shell
$ curl https:/api.proxyclick.com/v1/app/<companyId>/vm/meeting/<meetingId> \
-X DELETE \
-H "Authorization: Bearer <accessToken>" \	
-H 'Accept: application/json' \
```     

This endpoint closes a meeting


### HTTP Request

`DELETE https:/api.proxyclick.com/v1/app/<companyId>/vm/meeting/<meetingId>`


### Query Parameters

Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
companyId | true | string | The id of the company for which the meeting needs to be deleted
meetingId | true | string | The id of the meeting to be deleted

