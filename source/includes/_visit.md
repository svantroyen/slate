# Visits

## Visit model

### Visit object

> Example of visit object

```json
{
    "object": "visit",
    "id": "2015-02-18/M-YW863/V-EUA620",
    "visitor": {
        "object": "visitor",
        "id": "V-EUA620",
        "firstname": "shannon",
        "lastname": "moore",
        "companyName": "Altran corp",
        "email": "shannon.moore@sunfix.com",
        "phone": "",
        "mobile": "+12154789522",
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
                "name": "rfreferfe",
                "value": "zefzef"
            }
        ]
    },
    "meeting": {
        "object": "meeting",
        "id": "M-YW863",
        "title": "shannon moore",
        "recurrence": null
    },
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
        "lastModifiedAt": "2015-03-09T11:20:11Z",
        "countryCode": "BE",
        "latitude": 40.832176,
        "longitude": -74.111769,
        "status": "ACTIVATED"
    },
    "visiting": {
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
        }
    },
    "partOfGroup": false,
    "status": {
        "object": "status",
        "id": 1,
        "value": "Expected"
    },
    "commentCount": 0,
    "logCount": 1,
    "attachmentCount": 0,
    "timezone": "Europe/Brussels",
    "expectedAt": "2015-02-18T16:00:00+01:00",
    "leavingAt": "2015-02-18T18:00:00+01:00",
    "lastInvitationSentAt": "2015-02-18T14:57:32Z",
    "lastReminderSentAt": null,
    "arrivedAt": null,
    "leftAt": null,
    "customFields": null,
    "createdAt": "2015-02-18T14:57:32Z",
    "lastModifiedAt": "2015-02-18T14:57:32Z",
    "agreesToTerms": 0,
    "rating": null,
    "smsReminder": 1
    }
```


A visit object contains the following fields

Attribute | Type | Description
--------- | ---- | -----------
object | string | value is "visit" 
id | string | the id of the visit
visitor | object | the visitor object of the visit
company | object | the company object of the visit
visiting | object | the host (user) object of the visit
partOfGroup | boolean | flag to indicate if the visit is part of group
status | object | the status object of a visit
commentCount | numeric | the number of comments posted on the visit
logCount | numeric | the number of logs on the visist
attachmentCount | numeric | the number of atachments on the visit
timezone | string | the timezone of the visit
expectedAt | timestamp | the expected start date and time of the visit
leavingAt | timestamp | the expected end date and time of the visit
lastInvitationSentAt | timestamp | date and time when last invitation has been sent
lastReminderSentAt | timestamp | date and time when last reminder has been sent
arrivedAt | timestamp | date and time when visitor has checked in
leftAt  | timestamp | date and time when visitor checked out
customFields | object | the object of custom fields defined for the visit
createdAt | timestamp | date and time when visit has been created
lastModifiedAt | timestamp | date and time when visit has been last modified
agreesToTerms | boolean | flag to indicate if visitor has accepted the terms and conditions
rating | numeric | the rating of the visit by the visitor
smsReminder | boolean | flag to indicate if a sms reminder should be sent


## Get all visits of a specific date

```shell
curl "https:/api.proxyclick.com/v1/app/<companyId>/vm/visits/<date>"
  -H "Authorization: Bearer <accessToken>"
```

> The above command returns JSON structured like this:

```json
{
    "total": 1,
    "limit": 1,
    "visits": [
        {
            "object": "visit",
            "id": "2015-02-18/M-YW863/V-EUA620",
            "visitor": {
                "object": "visitor",
                "id": "V-EUA620",
                "firstname": "shannon",
                "lastname": "moore",
                "companyName": "Altran corp",
                "email": "shannon.moore@sunfix.com",
                "phone": "",
                "mobile": "+12154789522",
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
                        "name": "rfreferfe",
                        "value": "zefzef"
                    }
                ]
            },
            "meeting": {
                "object": "meeting",
                "id": "M-YW863",
                "title": "shannon moore",
                "recurrence": null
            },
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
                "lastModifiedAt": "2015-03-09T11:20:11Z",
                "countryCode": "BE",
                "latitude": 40.832176,
                "longitude": -74.111769,
                "status": "ACTIVATED"
            },
            "visiting": {
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
            }
        },
        "partOfGroup": false,
        "status": {
            "object": "status",
            "id": 1,
            "value": "Expected"
        },
        "commentCount": 0,
        "logCount": 1,
        "attachmentCount": 0,
        "timezone": "Europe/Brussels",
        "expectedAt": "2015-02-18T16:00:00+01:00",
        "leavingAt": "2015-02-18T18:00:00+01:00",
        "lastInvitationSentAt": "2015-02-18T14:57:32Z",
        "lastReminderSentAt": null,
        "arrivedAt": null,
        "leftAt": null,
        "customFields": null,
        "createdAt": "2015-02-18T14:57:32Z",
        "lastModifiedAt": "2015-02-18T14:57:32Z",
        "agreesToTerms": 0,
        "rating": null,
        "smsReminder": 1        
    }
]
}
```

This endpoint retrieves all visits of a company for a specific day.

### HTTP Request

`GET https:/api.proxyclick.com/v1/app/<companyId>/vm/visits/<date>`

### Query Parameters

Parameter | Required | Type | Description | Default
--------- | -------- | ---- | ----------- | -------
companyId | true | string | The id of the company for which the visits need to be retrieved | 
date | true | date | the date for which the visits need to be retrieved | 
sortBy | false | string | the sort element to use when retrieving the visits | time
sort | false | the sort direction to use when retrieving the visits | asc
page | false | numeric | the page number of the retrieved visits | 1
pageSize | false | numeric | the page size (number of elements per page) of the retrieved visits | 10
status | false | string | the status to filter the search of visits (see below for more details)
q | false | string | the filter element that will be applied to refine the search of visits (see below for more details) | 

As mentionned in the above table, the visits may be filtered by various elements:

* status: is a comma (,) delimited list of status (integer). The different statuses are 
	1. EXPECTED
	2. CHECKED-IN
	3. CHECKED-OUT
* q: is a space ( ) delimited list of strings to filter down the results of the visits. Every element of the list will be used to check match against:
	* visitor firstname
	* visitor lastname
	* visitor name of company
	* visitor licenseplate
	* meeting title
	* host firstname
	* host lastname
	
	
