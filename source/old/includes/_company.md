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
    "locale": "en-US",
    "phone": "+12125551423",
    "logoUrl": "https://api.proxyclick.com/v1/documents/0D4F1AFF5CCA5DA4E7BBC032B6A5A1CA9D24D90EF92AA69B57C888AFD9ACE2D58C94EADFE5CAD65365D6D91D4A804D241715CCCC8E08C9CEFF13E2E6D4AA05DD034916D717D8C8/2-192x46-la.png",
    "createdAt": "2014-01-07T09:05:31Z",
    "lastModifiedAt": "2015-02-18T14:37:14Z",
    "countryCode": "US",
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
status | string | the status of the company (it can be 'ACTIVATED','DEACTIVATED','PENDING')


