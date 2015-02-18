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
        "locale": "en-US",
        "phone": "+12125551423",
        "logoUrl": "https:/api.proxyclick.com/v1/app/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6D91D4A804D241715CCCC8E08C9CEFF13E2E6D4AA07DD064016D017D8C8/2-192x46-la.png",
        "createdAt": "2014-01-07T09:05:31Z",
        "lastModifiedAt": "2015-02-18T14:37:14Z",
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
        "pictureUrl": "https:/api.proxyclick.com/v1/app/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6DE144A804D241715CCCC8E08C9CEFF13E2E6D4AA07DD064016D017D8C8/6-120x120-po.png",
        "createdAt": "2014-01-07T09:05:31Z",
        "lastModifiedAt": "2015-02-18T14:52:51Z",
        "function": "Business analyst",
        "about": null,
        "licensePlate": null,
        "birthday": "2015-04-17",
        "entryDate": null,
        "lastLoggedAt": "2015-02-18T14:37:53Z",
        "assistant": {
            "object": "user",
            "id": "US-PS837",
            "firstname": "deanna",
            "lastname": "may",
            "companyName": "SunFix",
            "email": "deanna.may@sunfix.com",
            "phone": "",
            "mobile": "+447263938712",
            "language": {
                "code": "en",
                "name": "English",
                "displayName": "English"
            },
            "pictureUrl": "https:/api.proxyclick.com/v1/app/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6D91C4A804D241715CCCC8E08C9CEFF13E2E6D4AA06DD034916D51ED8C8/328-120x120-po.png",
            "createdAt": "2014-05-22T08:12:58Z",
            "lastModifiedAt": "2015-02-18T14:52:51Z"
        },
        "isAssistantOf": []
    },
    "users": null,
    "visitors": [
        {
            "object": "visitor",
            "id": "V-EUA620",
            "firstname": "shannon",
            "lastname": "moore",
            "companyName": "Altran corp",
            "email": "shannon.moore@sunfix.com",
            "phone": "",
            "mobile": "+12154789522",
            "mobileStatus": "UNKNOWN",
            "language": {
                "code": "en",
                "name": "English",
                "displayName": "English"
            },
            "pictureUrl": "http:/static-local.proxyclick.com:80/_/app/img/unknown-visitor.jpg",
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
                    "name": "rfreferfe",
                    "value": "zefzef"
                }
            ],
            "smsReminder": 1,
            "mailReminder": 0
        }
    ],
    "recurrence": null,
    "timezone": "Europe/Brussels",
    "createdAt": "2015-02-18T14:57:32Z",
    "createdBy": {
        "type": "USER",
        "object": "user",
        "id": "US-G606",
        "name": "Jordan Gray"
    },
    "createdVia": {
        "type": "APPLICATION",
        "name": "Proxyclick customer application"
    },
    "lastModifiedAt": "2015-02-18T14:57:30Z",
    "checkinNotificationType": "FIRST_LAST",
    "checkinNotificationUsers": null,
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
createdVia | object | the object defining how the meeting was created
lastModifiedAt | timestamp | the date of last modification of the meeting
checkinNotificationType | string | the type of notification of the meeting (for group meetings)
checkinNotificationUsers | list of objects | the list of user objects who will receive checkin notification for this meeting
checkoutReminderNotificationUsers | list of objects | the list of user objects who will receive checkout reminder notification for this meeting



## Get All meetings

```shell
curl "https:/api.proxyclick.com/v1/app/<companyId>/vm/meetings?from=<startDate>&to=<endDate>"
  -H "Authorization: Bearer <accessToken>"
```

```python
import requests
headers = {'Authorization': 'Bearer <accessToken>'}
url = 'https:/api.proxyclick.com/v1/app/<companyId>/vm/meetings?from=<startDate>&to=<endDate>'
r = requests.get(url, params=None, headers, cookies=None, auth=None, timeout=None)
```

```php
$service_url = 'https:/api.proxyclick.com/v1/app/<companyId>/vm/meetings?from=<startDate>&to=<endDate>';
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
        "locale": "en-US",
        "phone": "+12125551423",
        "logoUrl": "https:/api.proxyclick.com/v1/app/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6D91D4A804D241715CCCC8E08C9CEFF13E2E6D4AA07DD064016D017D8C8/2-192x46-la.png",
        "createdAt": "2014-01-07T09:05:31Z",
        "lastModifiedAt": "2015-02-18T14:37:14Z",
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
        "pictureUrl": "https:/api.proxyclick.com/v1/app/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6DE144A804D241715CCCC8E08C9CEFF13E2E6D4AA07DD064016D017D8C8/6-120x120-po.png",
        "createdAt": "2014-01-07T09:05:31Z",
        "lastModifiedAt": "2015-02-18T14:52:51Z",
        "function": "Business analyst",
        "about": null,
        "licensePlate": null,
        "birthday": "2015-04-17",
        "entryDate": null,
        "lastLoggedAt": "2015-02-18T14:37:53Z",
        "assistant": {
            "object": "user",
            "id": "US-PS837",
            "firstname": "deanna",
            "lastname": "may",
            "companyName": "SunFix",
            "email": "deanna.may@sunfix.com",
            "phone": "",
            "mobile": "+447263938712",
            "language": {
                "code": "en",
                "name": "English",
                "displayName": "English"
            },
            "pictureUrl": "https:/api.proxyclick.com/v1/app/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6D91C4A804D241715CCCC8E08C9CEFF13E2E6D4AA06DD034916D51ED8C8/328-120x120-po.png",
            "createdAt": "2014-05-22T08:12:58Z",
            "lastModifiedAt": "2015-02-18T14:52:51Z"
        },
        "isAssistantOf": []
    },
    "users": null,
    "visitors": [
        {
            "object": "visitor",
            "id": "V-EUA620",
            "firstname": "shannon",
            "lastname": "moore",
            "companyName": "Altran corp",
            "email": "shannon.moore@sunfix.com",
            "phone": "",
            "mobile": "+12154789522",
            "mobileStatus": "UNKNOWN",
            "language": {
                "code": "en",
                "name": "English",
                "displayName": "English"
            },
            "pictureUrl": "http:/static-local.proxyclick.com:80/_/app/img/unknown-visitor.jpg",
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
                    "name": "rfreferfe",
                    "value": "zefzef"
                }
            ],
            "smsReminder": 1,
            "mailReminder": 0
        }
    ],
    "recurrence": null,
    "timezone": "Europe/Brussels",
    "createdAt": "2015-02-18T14:57:32Z",
    "createdBy": {
        "type": "USER",
        "object": "user",
        "id": "US-G606",
        "name": "Jordan Gray"
    },
    "createdVia": {
        "type": "APPLICATION",
        "name": "Proxyclick customer application"
    },
    "lastModifiedAt": "2015-02-18T14:57:30Z",
    "checkinNotificationType": "FIRST_LAST",
    "checkinNotificationUsers": null,
    "checkoutReminderNotificationUsers": null
},
    ...
]
```

This endpoint retrieves all meetings of a company.

### HTTP Request

`GET https:/api.proxyclick.com/v1/app/<companyId>/vm/meetings`

### URL Parameters

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

```python
import requests
headers = {'Authorization': 'Bearer <accessToken>'}
url = 'https:/api.proxyclick.com/v1/app/<companyId>/vm/meetings/<meetingId>'
r = requests.get(url, params=None, headers, cookies=None, auth=None, timeout=None)
```

```php
$service_url = 'https:/api.proxyclick.com/v1/app/<companyId>/vm/meetings/<meetingId>';
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
        "locale": "en-US",
        "phone": "+12125551423",
        "logoUrl": "https:/api.proxyclick.com/v1/app/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6D91D4A804D241715CCCC8E08C9CEFF13E2E6D4AA07DD064016D017D8C8/2-192x46-la.png",
        "createdAt": "2014-01-07T09:05:31Z",
        "lastModifiedAt": "2015-02-18T14:37:14Z",
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
        "pictureUrl": "https:/api.proxyclick.com/v1/app/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6DE144A804D241715CCCC8E08C9CEFF13E2E6D4AA07DD064016D017D8C8/6-120x120-po.png",
        "createdAt": "2014-01-07T09:05:31Z",
        "lastModifiedAt": "2015-02-18T14:52:51Z",
        "function": "Business analyst",
        "about": null,
        "licensePlate": null,
        "birthday": "2015-04-17",
        "entryDate": null,
        "lastLoggedAt": "2015-02-18T14:37:53Z",
        "assistant": {
            "object": "user",
            "id": "US-PS837",
            "firstname": "deanna",
            "lastname": "may",
            "companyName": "SunFix",
            "email": "deanna.may@sunfix.com",
            "phone": "",
            "mobile": "+447263938712",
            "language": {
                "code": "en",
                "name": "English",
                "displayName": "English"
            },
            "pictureUrl": "https:/api.proxyclick.com/v1/app/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6D91C4A804D241715CCCC8E08C9CEFF13E2E6D4AA06DD034916D51ED8C8/328-120x120-po.png",
            "createdAt": "2014-05-22T08:12:58Z",
            "lastModifiedAt": "2015-02-18T14:52:51Z"
        },
        "isAssistantOf": []
    },
    "users": null,
    "visitors": [
        {
            "object": "visitor",
            "id": "V-EUA620",
            "firstname": "shannon",
            "lastname": "moore",
            "companyName": "Altran corp",
            "email": "shannon.moore@sunfix.com",
            "phone": "",
            "mobile": "+12154789522",
            "mobileStatus": "UNKNOWN",
            "language": {
                "code": "en",
                "name": "English",
                "displayName": "English"
            },
            "pictureUrl": "http:/static-local.proxyclick.com:80/_/app/img/unknown-visitor.jpg",
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
                    "name": "rfreferfe",
                    "value": "zefzef"
                }
            ],
            "smsReminder": 1,
            "mailReminder": 0
        }
    ],
    "recurrence": null,
    "timezone": "Europe/Brussels",
    "createdAt": "2015-02-18T14:57:32Z",
    "createdBy": {
        "type": "USER",
        "object": "user",
        "id": "US-G606",
        "name": "Jordan Gray"
    },
    "createdVia": {
        "type": "APPLICATION",
        "name": "Proxyclick customer application"
    },
    "lastModifiedAt": "2015-02-18T14:57:30Z",
    "checkinNotificationType": "FIRST_LAST",
    "checkinNotificationUsers": null,
    "checkoutReminderNotificationUsers": null
}
```

This endpoint retrieves a specific meeting.

### HTTP Request

`GET https:/api.proxyclick.com/v1/app/<companyId>/vm/meetings/<meetingId>`

### URL Parameters

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

```python
import requests
headers = {'Authorization': 'Bearer <accessToken>', 'Content-type': 'application/x-www-form-urlencoded', 'Accept': 'text/plain'}
url = 'https:/api.proxyclick.com/v1/app/<companyId>/vm/meetings'      
payload = {"startAt": "", "hostId": "", "endAt": "", "recurrence": {}, "title": "", "description": "", "visitors": [], "userIds": [], "checkinNotificationType": "", "checkoutNotificationUsers": [], "checkoutReminderNotificationUsers": [], "checkinNotificationUsers": []}
r = requests.post(url, data=payload, headers)
```

```php
$url = 'https:/api.proxyclick.com/v1/app/<companyId>/vm/meetings';
$data = array("startAt"=> "", "hostId"=> "", "endAt"=> "", "recurrence"=> {}, "title"=> "", "description"=> "", "visitors"=> [], "userIds"=> [], "checkinNotificationType"=> "", "checkoutNotificationUsers"=> [], "checkoutReminderNotificationUsers"=> [], "checkinNotificationUsers"=> []);
$options = array(
    'http' => array(
        'header'  => "Authorization: Bearer <accessToken>, Content-type: application/x-www-form-urlencoded\r\n",
        'method'  => 'POST',
        'content' => http_build_query($data),
    ),
);
$context  = stream_context_create($options);
$result = file_get_contents($url, false, $context);
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
        "locale": "en-US",
        "phone": "+12125551423",
        "logoUrl": "https:/api.proxyclick.com/v1/app/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6D91D4A804D241715CCCC8E08C9CEFF13E2E6D4AA07DD064016D017D8C8/2-192x46-la.png",
        "createdAt": "2014-01-07T09:05:31Z",
        "lastModifiedAt": "2015-02-18T14:37:14Z",
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
        "pictureUrl": "https:/api.proxyclick.com/v1/app/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6DE144A804D241715CCCC8E08C9CEFF13E2E6D4AA07DD064016D017D8C8/6-120x120-po.png",
        "createdAt": "2014-01-07T09:05:31Z",
        "lastModifiedAt": "2015-02-18T14:52:51Z",
        "function": "Business analyst",
        "about": null,
        "licensePlate": null,
        "birthday": "2015-04-17",
        "entryDate": null,
        "lastLoggedAt": "2015-02-18T14:37:53Z",
        "assistant": {
            "object": "user",
            "id": "US-PS837",
            "firstname": "deanna",
            "lastname": "may",
            "companyName": "SunFix",
            "email": "deanna.may@sunfix.com",
            "phone": "",
            "mobile": "+447263938712",
            "language": {
                "code": "en",
                "name": "English",
                "displayName": "English"
            },
            "pictureUrl": "https:/api.proxyclick.com/v1/app/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6D91C4A804D241715CCCC8E08C9CEFF13E2E6D4AA06DD034916D51ED8C8/328-120x120-po.png",
            "createdAt": "2014-05-22T08:12:58Z",
            "lastModifiedAt": "2015-02-18T14:52:51Z"
        },
        "isAssistantOf": []
    },
    "users": null,
    "visitors": [
        {
            "object": "visitor",
            "id": "V-EUA620",
            "firstname": "shannon",
            "lastname": "moore",
            "companyName": "Altran corp",
            "email": "shannon.moore@sunfix.com",
            "phone": "",
            "mobile": "+12154789522",
            "mobileStatus": "UNKNOWN",
            "language": {
                "code": "en",
                "name": "English",
                "displayName": "English"
            },
            "pictureUrl": "http:/static-local.proxyclick.com:80/_/app/img/unknown-visitor.jpg",
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
                    "name": "rfreferfe",
                    "value": "zefzef"
                }
            ],
            "smsReminder": 1,
            "mailReminder": 0
        }
    ],
    "recurrence": null,
    "timezone": "Europe/Brussels",
    "createdAt": "2015-02-18T14:57:32Z",
    "createdBy": {
        "type": "USER",
        "object": "user",
        "id": "US-G606",
        "name": "Jordan Gray"
    },
    "createdVia": {
        "type": "APPLICATION",
        "name": "Proxyclick customer application"
    },
    "lastModifiedAt": "2015-02-18T14:57:30Z",
    "checkinNotificationType": "FIRST_LAST",
    "checkinNotificationUsers": null,
    "checkoutReminderNotificationUsers": null
}
```

This endpoint creates a new meeting and retrieve the newly created meeting.

### HTTP Request

`POST https:/api.proxyclick.com/v1/app/<companyId>/vm/meetings`

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
]```
