# Tickets

## Ticket model

### Ticket object


> Example of ticket object

```json
{
    "object": "ticket",
    "type": "Ticket",
    "id": "T-MC672",
    "reference": null,
    "title": "Ventilation not working",
    "description": "Ventilation is not working anymore on 3rd floor. ",
    "company": {
        "object": "corporate",
        "id": "CO-C202",
        "reference": null,
        "name": "SunFix",
        "timezone": "Europe/Brussels",
        "locale": "en-US",
        "phone": "+12125551423",
        "logoUrl": "https://api.proxyclick.com/v1/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6D91D4A804D241715CCCC8E08C9CEFF13E2E6D4AA06DD074D16D51FD8C8/2-192x46-la.png",
        "createdAt": "2014-01-07T09:05:31Z",
        "lastModifiedAt": "2015-02-18T14:37:14Z",
        "countryCode": "BE",
        "latitude": 40.832176,
        "longitude": -74.111769,
        "status": "ACTIVATED"
    },
    "creator": {
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
        "pictureUrl": "https://api.proxyclick.com/v1/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6DE144A804D241715CCCC8E08C9CEFF13E2E6D4AA06DD074D16D51FD8C8/6-120x120-po.png",
        "createdAt": "2014-01-07T09:05:31Z",
        "lastModifiedAt": "2015-02-18T14:52:51Z"
    },
    "notifier": {
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
        "pictureUrl": "https://api.proxyclick.com/v1/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6DE144A804D241715CCCC8E08C9CEFF13E2E6D4AA06DD074D16D51FD8C8/6-120x120-po.png",
        "createdAt": "2014-01-07T09:05:31Z",
        "lastModifiedAt": "2015-02-18T14:52:51Z"
    },
    "category": {
        "id": 5,
        "parentId": 4,
        "name": "Ventilation Systems",
        "path": [
            "Building Maintenance",
            "Ventilation Systems"
        ]
    },
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
    "agent": {
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
        "pictureUrl": "https://api.proxyclick.com/v1/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6D91C4A804D241715CCCC8E08C9CEFF13E2E6D4AA06DD074D16D51FD8C8/328-120x120-po.png",
        "createdAt": "2014-05-22T08:12:58Z",
        "lastModifiedAt": "2015-02-18T14:52:51Z"
    },
    "supplier": {
        "object": "supplier",
        "id": "SU-LR561",
        "reference": null,
        "name": "Fresh Air",
        "timezone": "Europe/Brussels",
        "locale": "en",
        "phone": "",
        "logoUrl": null,
        "createdAt": "2015-02-18T15:42:55Z",
        "lastModifiedAt": "2015-02-18T15:42:55Z",
        "countryCode": "BE",
        "latitude": 50.503887,
        "longitude": 4.469936,
        "status": "ACTIVATED"
    },
    "supplierLastReadAt": null,
    "supplierLastNotificationSentAt": null,
    "dueAt": "2015-03-12T00:00:00+01:00",
    "reopened": false,
    "archived": false,
    "favorite": false,
    "commentCount": 0,
    "logCount": 1,
    "attachmentCount": 0,
    "relatedTicketCount": 0,
    "customFields": null,
    "createdAt": "2015-02-18T15:43:32Z",
    "lastStatusChangedAt": "2015-02-18T15:43:32Z",
    "lastModifiedAt": "2015-02-18T15:43:32Z",
    "sendRequesterSolved": 1,
    "rating": null
}
```

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

## Get All tickets

```shell
curl "https:/api.proxyclick.com/v1/app/<companyId>/sd/tickets"
  -H "Authorization: Bearer <accessToken>"
```

```python
import requests
headers = {'Authorization': 'Bearer <accessToken>'}
url = 'https:/api.proxyclick.com/v1/app/<companyId>/sd/tickets'
r = requests.get(url, params=None, headers, cookies=None, auth=None, timeout=None)
```

```php
$service_url = 'https:/api.proxyclick.com/v1/app/<companyId>/sd/tickets';
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
    "id": "T-MC672",
    "reference": null,
    "title": "Ventilation not working",
    "description": "Ventilation is not working anymore on 3rd floor. ",
    "company": {
        "object": "corporate",
        "id": "CO-C202",
        "reference": null,
        "name": "SunFix",
        "timezone": "Europe/Brussels",
        "locale": "en-US",
        "phone": "+12125551423",
        "logoUrl": "https://api.proxyclick.com/v1/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6D91D4A804D241715CCCC8E08C9CEFF13E2E6D4AA06DD074D16D51FD8C8/2-192x46-la.png",
        "createdAt": "2014-01-07T09:05:31Z",
        "lastModifiedAt": "2015-02-18T14:37:14Z",
        "countryCode": "BE",
        "latitude": 40.832176,
        "longitude": -74.111769,
        "status": "ACTIVATED"
    },
    "creator": {
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
        "pictureUrl": "https://api.proxyclick.com/v1/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6DE144A804D241715CCCC8E08C9CEFF13E2E6D4AA06DD074D16D51FD8C8/6-120x120-po.png",
        "createdAt": "2014-01-07T09:05:31Z",
        "lastModifiedAt": "2015-02-18T14:52:51Z"
    },
    "notifier": {
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
        "pictureUrl": "https://api.proxyclick.com/v1/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6DE144A804D241715CCCC8E08C9CEFF13E2E6D4AA06DD074D16D51FD8C8/6-120x120-po.png",
        "createdAt": "2014-01-07T09:05:31Z",
        "lastModifiedAt": "2015-02-18T14:52:51Z"
    },
    "category": {
        "id": 5,
        "parentId": 4,
        "name": "Ventilation Systems",
        "path": [
            "Building Maintenance",
            "Ventilation Systems"
        ]
    },
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
    "agent": {
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
        "pictureUrl": "https://api.proxyclick.com/v1/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6D91C4A804D241715CCCC8E08C9CEFF13E2E6D4AA06DD074D16D51FD8C8/328-120x120-po.png",
        "createdAt": "2014-05-22T08:12:58Z",
        "lastModifiedAt": "2015-02-18T14:52:51Z"
    },
    "supplier": {
        "object": "supplier",
        "id": "SU-LR561",
        "reference": null,
        "name": "Fresh Air",
        "timezone": "Europe/Brussels",
        "locale": "en",
        "phone": "",
        "logoUrl": null,
        "createdAt": "2015-02-18T15:42:55Z",
        "lastModifiedAt": "2015-02-18T15:42:55Z",
        "countryCode": "BE",
        "latitude": 50.503887,
        "longitude": 4.469936,
        "status": "ACTIVATED"
    },
    "supplierLastReadAt": null,
    "supplierLastNotificationSentAt": null,
    "dueAt": "2015-03-12T00:00:00+01:00",
    "reopened": false,
    "archived": false,
    "favorite": false,
    "commentCount": 0,
    "logCount": 1,
    "attachmentCount": 0,
    "relatedTicketCount": 0,
    "customFields": null,
    "createdAt": "2015-02-18T15:43:32Z",
    "lastStatusChangedAt": "2015-02-18T15:43:32Z",
    "lastModifiedAt": "2015-02-18T15:43:32Z",
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
companyId | true | string | The id of the company from which the tickets need to be retrieved


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
dueDateFrom | false | date | the result will only include tickets with due date starting from this date
dueDateTo | false | date | the result will only include tickets with due date ending at this date



## Get a specific ticket

```shell
curl "https:/api.proxyclick.com/v1/app/<companyId>/sd/tickets/<ticketId>"
  -H "Authorization: Bearer <accessToken>"
```

```python
import requests
headers = {'Authorization': 'Bearer <accessToken>'}
url = 'https:/api.proxyclick.com/v1/app/<companyId>/sd/tickets/<ticketId>'
r = requests.get(url, params=None, headers, cookies=None, auth=None, timeout=None)
```

```php
$service_url = 'https:/api.proxyclick.com/v1/app/<companyId>/sd/tickets/<ticketId>';
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
    "object": "ticket",
    "type": "Ticket",
    "id": "T-MC672",
    "reference": null,
    "title": "Ventilation not working",
    "description": "Ventilation is not working anymore on 3rd floor. ",
    "company": {
        "object": "corporate",
        "id": "CO-C202",
        "reference": null,
        "name": "SunFix",
        "timezone": "Europe/Brussels",
        "locale": "en-US",
        "phone": "+12125551423",
        "logoUrl": "https://api.proxyclick.com/v1/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6D91D4A804D241715CCCC8E08C9CEFF13E2E6D4AA06DD074D16D51FD8C8/2-192x46-la.png",
        "createdAt": "2014-01-07T09:05:31Z",
        "lastModifiedAt": "2015-02-18T14:37:14Z",
        "countryCode": "BE",
        "latitude": 40.832176,
        "longitude": -74.111769,
        "status": "ACTIVATED"
    },
    "creator": {
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
        "pictureUrl": "https://api.proxyclick.com/v1/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6DE144A804D241715CCCC8E08C9CEFF13E2E6D4AA06DD074D16D51FD8C8/6-120x120-po.png",
        "createdAt": "2014-01-07T09:05:31Z",
        "lastModifiedAt": "2015-02-18T14:52:51Z"
    },
    "notifier": {
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
        "pictureUrl": "https://api.proxyclick.com/v1/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6DE144A804D241715CCCC8E08C9CEFF13E2E6D4AA06DD074D16D51FD8C8/6-120x120-po.png",
        "createdAt": "2014-01-07T09:05:31Z",
        "lastModifiedAt": "2015-02-18T14:52:51Z"
    },
    "category": {
        "id": 5,
        "parentId": 4,
        "name": "Ventilation Systems",
        "path": [
            "Building Maintenance",
            "Ventilation Systems"
        ]
    },
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
    "agent": {
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
        "pictureUrl": "https://api.proxyclick.com/v1/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6D91C4A804D241715CCCC8E08C9CEFF13E2E6D4AA06DD074D16D51FD8C8/328-120x120-po.png",
        "createdAt": "2014-05-22T08:12:58Z",
        "lastModifiedAt": "2015-02-18T14:52:51Z"
    },
    "supplier": {
        "object": "supplier",
        "id": "SU-LR561",
        "reference": null,
        "name": "Fresh Air",
        "timezone": "Europe/Brussels",
        "locale": "en",
        "phone": "",
        "logoUrl": null,
        "createdAt": "2015-02-18T15:42:55Z",
        "lastModifiedAt": "2015-02-18T15:42:55Z",
        "countryCode": "BE",
        "latitude": 50.503887,
        "longitude": 4.469936,
        "status": "ACTIVATED"
    },
    "supplierLastReadAt": null,
    "supplierLastNotificationSentAt": null,
    "dueAt": "2015-03-12T00:00:00+01:00",
    "reopened": false,
    "archived": false,
    "favorite": false,
    "commentCount": 0,
    "logCount": 1,
    "attachmentCount": 0,
    "relatedTicketCount": 0,
    "customFields": null,
    "createdAt": "2015-02-18T15:43:32Z",
    "lastStatusChangedAt": "2015-02-18T15:43:32Z",
    "lastModifiedAt": "2015-02-18T15:43:32Z",
    "sendRequesterSolved": 1,
    "rating": null
}
```

This endpoint retrieves a specific ticket.

### HTTP Request

`GET https://api.proxyclick.com/v1/app/<companyId>/sd/tickets/<ticketId>`

### URL Parameters

Parameter | Required | Type | Description
--------- | -------- | ---- | -----------
companyId | true | string | The id of the company for which the meeting needs to be retrieved
ticketId | true | string | The id of the ticket to retrieve


## Create a ticket

```shell
$ curl https:/api.proxyclick.com/v1/app/<companyId>/sd/tickets/ \
-X POST \
-H "Authorization: Bearer <accessToken>" \	
-H 'Accept: application/json' \
-H 'Content-Type: application/json' -d '
{
    "notifierId": "",
    "dueDate": "",
    "categoryId": "",
    "sendRequesterSolved": 0,
    "agentId": "",
    "reference": "",
    "supplierId": "",
    "sendRequesterCopy": 0,
    "customFields": [],
    "title": "",
    "priorityId": "",
    "creatorId": "",
    "description": ""
}'
```     

```python
import requests
headers = {'Authorization': 'Bearer <accessToken>', 'Content-type': 'application/x-www-form-urlencoded', 'Accept': 'text/plain'}
url = 'https:/api.proxyclick.com/v1/app/<companyId>/sd/tickets/'      
payload = {"notifierId": "", "dueDate": "", "categoryId": "", "sendRequesterSolved": 0, "agentId": "", "reference": "", "supplierId": "", "sendRequesterCopy": 0, "customFields": [], "title": "", "priorityId": "", "creatorId": "", "description": ""}
r = requests.post(url, data=payload, headers)
```

```php
$url = 'https:/api.proxyclick.com/v1/app/<companyId>/sd/tickets/';
$data = array("notifierId"=> "", "dueDate"=> "", "categoryId"=> "", "sendRequesterSolved"=> 0, "agentId"=> "", "reference"=> "", "supplierId"=> "", "sendRequesterCopy"=> 0, "customFields"=> [], "title"=> "", "priorityId"=> "", "creatorId"=> "", "description"=> "");
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
    "object": "ticket",
    "type": "Ticket",
    "id": "T-MC672",
    "reference": null,
    "title": "Ventilation not working",
    "description": "Ventilation is not working anymore on 3rd floor. ",
    "company": {
        "object": "corporate",
        "id": "CO-C202",
        "reference": null,
        "name": "SunFix",
        "timezone": "Europe/Brussels",
        "locale": "en-US",
        "phone": "+12125551423",
        "logoUrl": "https://api.proxyclick.com/v1/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6D91D4A804D241715CCCC8E08C9CEFF13E2E6D4AA06DD074D16D51FD8C8/2-192x46-la.png",
        "createdAt": "2014-01-07T09:05:31Z",
        "lastModifiedAt": "2015-02-18T14:37:14Z",
        "countryCode": "BE",
        "latitude": 40.832176,
        "longitude": -74.111769,
        "status": "ACTIVATED"
    },
    "creator": {
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
        "pictureUrl": "https://api.proxyclick.com/v1/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6DE144A804D241715CCCC8E08C9CEFF13E2E6D4AA06DD074D16D51FD8C8/6-120x120-po.png",
        "createdAt": "2014-01-07T09:05:31Z",
        "lastModifiedAt": "2015-02-18T14:52:51Z"
    },
    "notifier": {
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
        "pictureUrl": "https://api.proxyclick.com/v1/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6DE144A804D241715CCCC8E08C9CEFF13E2E6D4AA06DD074D16D51FD8C8/6-120x120-po.png",
        "createdAt": "2014-01-07T09:05:31Z",
        "lastModifiedAt": "2015-02-18T14:52:51Z"
    },
    "category": {
        "id": 5,
        "parentId": 4,
        "name": "Ventilation Systems",
        "path": [
            "Building Maintenance",
            "Ventilation Systems"
        ]
    },
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
    "agent": {
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
        "pictureUrl": "https://api.proxyclick.com/v1/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6D91C4A804D241715CCCC8E08C9CEFF13E2E6D4AA06DD074D16D51FD8C8/328-120x120-po.png",
        "createdAt": "2014-05-22T08:12:58Z",
        "lastModifiedAt": "2015-02-18T14:52:51Z"
    },
    "supplier": {
        "object": "supplier",
        "id": "SU-LR561",
        "reference": null,
        "name": "Fresh Air",
        "timezone": "Europe/Brussels",
        "locale": "en",
        "phone": "",
        "logoUrl": null,
        "createdAt": "2015-02-18T15:42:55Z",
        "lastModifiedAt": "2015-02-18T15:42:55Z",
        "countryCode": "BE",
        "latitude": 50.503887,
        "longitude": 4.469936,
        "status": "ACTIVATED"
    },
    "supplierLastReadAt": null,
    "supplierLastNotificationSentAt": null,
    "dueAt": "2015-03-12T00:00:00+01:00",
    "reopened": false,
    "archived": false,
    "favorite": false,
    "commentCount": 0,
    "logCount": 1,
    "attachmentCount": 0,
    "relatedTicketCount": 0,
    "customFields": null,
    "createdAt": "2015-02-18T15:43:32Z",
    "lastStatusChangedAt": "2015-02-18T15:43:32Z",
    "lastModifiedAt": "2015-02-18T15:43:32Z",
    "sendRequesterSolved": 1,
    "rating": null
}
```

This endpoint creates a new ticket and retrieves the newly created ticket.

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

