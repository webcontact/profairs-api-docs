# Contacts

## Get contacts

```shell
curl
  --location --request GET '{baseurl}/contacts/' \
  --header 'Content-Type: application/json' \
  --header 'X-API-Key: {API-Key}'
```

> The above command returns JSON structured like this:

```json
{
    "contacts": [
      {
        "postalcode": "12345",
        "telephone": "+497082-98616282",
        "job_title": "Developer",
        "firstname": "Max",
        "street": "Musterstraße 4",
        "email": "max@mustermann.de",
        "comment": "",
        "company": "",
        "contactid": 1,
        "city": "Musterstadt",
        "country": "Deutschland",
        "salutation": "Herr",
        "lastname": "Mustermann",
        "fairtypeid": "1",
        "title": "Dr.",
        "additional_address": "Etage 1",
        "hasnewsletterapproval": false,
        "exhibitorid": 1,
        "mobile": "+49176-98616282"
      }
    ]
    "error": false
}
```

### HTTP request

`GET {baseurl}/contacts/`

### Query parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorid | numeric | false |  |
contactid | numeric | false |  |
typeid | numeric | false |  |
language | String | false | "de_DE" |
receivesNewsletter | Boolean | false | false |
fairtypeid | numeric | false ||

## Retreive contact

```shell
curl --location --request GET '{baseurl}/contacts/{contactid}' \
--header 'Content-Type: application/json' \
--header 'X-API-Key: {API-Key}'
```

> The above command returns JSON structured like this:

```json
{
    "contacts": [
        {
            "postalcode": "",
            "telephone": "",
            "job_title": "",
            "firstname": "Kevin",
            "street": "",
            "email": "kevin@webcontact.de",
            "contactid": 1,
            "comment": "",
            "company": "",
            "city": "",
            "country": "Deutschland",
            "salutation": "Herr",
            "lastname": "Thiel",
            "fairtypeid": "",
            "title": "",
            "additional_address": "",
            "hasnewsletterapproval": false,
            "exhibitorid": 1,
            "mobile": "017684407551"
        }
    ],
    "error": false
}
```

### HTTP request

`GET {baseurl}/contacts/{contactid}`

### URL parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
contactid | string | true |  |

## Create contact person
### HTTP request

`POST {baseurl}/contacts/`

```shell
curl --location --request POST '{baseurl}/contacts/' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "salutation" : "Herr",
    "title" : "Dr.",
    "job_title" : "Developer",
    "firstname" : "Max",
    "lastname" : "Mustermann",
    "exhibitorid" : "1337",
    "telephone" : "+49 12345 6789",
    "mobile" : "+49 1234567890",
    "email" : "max.mustermann@gmail.com",
    "newsletter" : true,
    "comment" : "Lorem Ipsum",
    "company" : "Muster GmbH",
    "street" : "Musterstraße 123",
    "additional_address" : "Lorem Ipsum",
    "postalcode" : "12345",
    "city" : "Mustercity",
    "country" : "Deutschland",
    "fairtypeid" : "1"
}'
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "contactid": "2840"
}
```

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
salutation | string | true |  |
title | string | false |  |
job_title | string | false |  |
firstname | string | true |  |
lastname | string | true |  |
exhibitorid | numeric | true |  |
telephone | string | false |  |
mobile | string | false |  |
email | string | true |  |
newsletter | boolean | true |  false |
comment | string | false |  |
company | string | false |  |
street | string | false |  |
additional_address | string | false |  |
postalcode | string | false |  |
city | string | false |  |
country | string | false |  |
fairtypeid | numeric | false |  |

## Upload contact person image

```shell
curl --location --request POST '{baseurl}/contacts/upload/' \
--header 'X-API-Key: {API-Key}' \
--form 'file=@"{file_path}"' \
--form 'file_name="{file_name}"' \
--form 'contactid="{contactid}"' \
--form 'type="image"'
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "contactid": "2838"
}
```

### HTTP request

`POST {baseurl}/contactpersons/upload/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
contactid | numeric | true |  |
file | binary | true |  |
file_name | string | true |  |
type | string | true |  |

## Update contact person
```shell
curl --location --request PUT '{baseurl}/contacts/{contactid}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "salutation" : "Herr",
    "title" : "Dr.",
    "job_title" : "Developer",
    "firstname" : "Max",
    "lastname" : "Mustermann",
    "exhibitorid" : "1337",
    "telephone" : "+49 12345 6789",
    "mobile" : "+49 1234567890",
    "email" : "max.mustermann@gmail.com",
    "newsletter" : true,
    "comment" : "Lorem Ipsum",
    "company" : "Muster GmbH",
    "street" : "Musterstraße 123",
    "additional_address" : "Lorem Ipsum",
    "postalcode" : "12345",
    "city" : "Mustercity",
    "country" : "Deutschland",
    "fairtypeid" : "1"
}'
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "contactid": 2838
}
```

### HTTP request

`PUT {baseurl}/contactpersons/{contactid}/`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
contactid | numeric | true |  |

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
salutation | string | true |  |
title | string | false |  |
job_title | string | false |  |
firstname | string | true |  |
lastname | string | true |  |
exhibitorid |numeric | true |  |
telephone | string | false |  |
mobile | string | false |  |
email | string | true |  |
newsletter | boolean | true | false |
comment | string | false |  |
company | string | false |  |
street | string | false |  |
additional_address | string | false |  |
postalcode |string | false |  |
city | string | false |  |
country | string | false |  |
fairtypeid | numeric | false |  |

## Delete contact person

```shell
curl --location --request DELETE '{baseurl}/contacts/{contactid}' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "contactid": 2838
}
```

### HTTP request

`DELETE {baseurl}/contactperson/{contactid}/`


### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
contactid | numeric | true |  |
