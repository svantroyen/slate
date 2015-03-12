# Companies

## Company model

### Company object

> Example of a company object

```json
{
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
}
```

A company object contains the following fields

Attribute | Type | Description
--------- | ---- | -----------
object | string | value is "corporate"
id | string | the id of the company
reference | string | the reference of the company
name | string | the name of the company
timezone | string | the timezone of the company
locale | string | the locale of the company
phone | string | the general phone number of the company
logoUrl | string | the url of the logo of the company
createdAt | timestamp | the creation date of the company
lastModifiedAt | timestamp | the last modification date of the company
countryCode | string | the code of the country of the company
latitude | string | the latitude of the company's office
longitude | string | the longitude of the company's office
status | string | the status of the company (values can be 'ACTIVATED','DEACTIVATED','PENDING')


