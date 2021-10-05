# Contacts

## Retreive contacts

```shell
curl
  --location --request GET 'http://profairs-api.tom.webcontact.de/rest/profairs-api/contacts/' \
  --header 'Content-Type: application/json' \
  --header 'X-API-Key: 941c8937-0b05-4530-939c-6981a2adadc8'
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

## Retreive contact

```shell
curl --location --request GET 'http://profairs-api.tom.webcontact.de/rest/profairs-api/contacts/1' \
--header 'Content-Type: application/json' \
--header 'X-API-Key: 941c8937-0b05-4530-939c-6981a2adadc8'
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

### Query parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
contactid | string | true |  |

## Create contact person

```shell
curl "{baseurl}/contacts/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
salutation | string | true |  |
title | string | false |  |
job_title | string | false |  |
firstname | string | true |  |
lastname | string | true |  |
exhibitor_id | numeric | true |  |
telephone | string | false |  |
mobile | string | false |  |
email | string | true |  |
has_newsletter_approval | boolean | true |  false |
comment | string | false |  |
company | string | false |  |
street | string | false |  |
additional_address | string | false |  |
postalcode | string | false |  |
city | string | false |  |
country | string | false |  |
fair_type_id | numeric | false |  |

## Upload contact person image

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`POST {baseurl}/contactpersons/upload/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
datasource | string | true |  |
file | binary | true |  |
image_name | string | true |  |
type | string | true |  |
contact_person_id | numeric | true |  |

## Update contact person

### HTTP request

`PUT {baseurl}/contactpersons/{contact_person_id}/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
datasource | string | true |  |
salutation | string | true |  |
title | string | false |  |
job_title | string | false |  |
firstname | string | true |  |
lastname | string | true |  |
exhibitor_id |numeric | true |  |
telephone | string | false |  |
mobile | string | false |  |
email | string | true |  |
has_newsletter_approval | boolean | true | false |
comment | string | false |  |
company | string | false |  |
street | string | false |  |
additional_address | string | false |  |
postalcode |string | false |  |
city | string | false |  |
country | string | false |  |
fair_type_id | numeric | false |  |

## Delete contact person

### HTTP request

`DELETE {baseurl}/contactperson/{contact_person_id}/`


### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
contact_person_id | numeric | true |  |
datasource | string | true |  |
forum_sync | boolean |  false | false |  |
