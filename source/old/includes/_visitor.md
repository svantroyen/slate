# Visitors

## Visitor model

### Visitor object

> Example of visitor object

```json
{
   "object": "visitor",
   "id": "V-ETZ519",
   "firstname": "fe",
   "lastname": "fap",
   "companyName": "ddd",
   "email": "",
   "phone": "",
   "mobile": "",
   "language": {
       "code": "en",
       "name": "English",
       "displayName": "English"
    }
}    
```
A visitor object contains the following fields


Attribute | Type | Description
--------- | ---- | -----------
object | string | value is "visitor" 
id | string | the id of the visitor
firstname | string | the firstname of the visitor
lastname | string | the lastname of the visitor
companyName | string | the name of the company of the visitor
email | string | the email of the visitor
phone | string | the phone number of the visitor (international format)
mobile | string | the mobile number of the visitor (international format)
language | object | the language object of the visitor