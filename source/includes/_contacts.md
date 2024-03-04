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
contacttypeid | numeric | false |  |

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

`POST {baseurl}/contacts/upload/`

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

`PUT {baseurl}/contacts/{contactid}/`

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
contacttypeid | numeric | false |  |

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

`DELETE {baseurl}/contacts/{contactid}/`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
contactid | numeric | true |  |

## Get Contact Types

If you want to work with the contact types separated from the contacts, you can use the following endpoints:

```shell
curl --location --request GET '{baseurl}/contacts/types/' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:
  
  ```json
{
  "error": false,
  "error_message": {},
  "contact_types": [
    {
      "en_GB": "Regular",
      "contacttypeid": 5,
      "de_DE": "Allgemein",
      "fairtypeid": 1
    },
    {
      "en_GB": "invoice recipient",
      "contacttypeid": 6,
      "de_DE": "Ansprechpartner Rechnungswesen",
      "fairtypeid": 1
    },
    {
      "en_GB": "Messebau",
      "contacttypeid": 7,
      "de_DE": "Messebau",
      "fairtypeid": 1
    },
    {
      "en_GB": "Regular",
      "contacttypeid": 8,
      "de_DE": "Allgemein",
      "fairtypeid": 2
    },
    {
      "en_GB": "invoice recipient",
      "contacttypeid": 9,
      "de_DE": "Ansprechpartner Rechnungswesen",
      "fairtypeid": 2
    },
    {
      "en_GB": "Messebau",
      "contacttypeid": 10,
      "de_DE": "Messebau",
      "fairtypeid": 2
    },
    {
      "en_GB": "Regular",
      "contacttypeid": 11,
      "de_DE": "Allgemein",
      "fairtypeid": 3
    }
  ]
}
```

### HTTP request

`GET {baseurl}/contacts/types/`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
contactid | numeric | false |  |
fairtypeid | numeric | false |  |
contacttypeid | numeric | false |  |

## Create Contact Types

```shell
curl --location --request POST '{baseurl}/contacts/types/' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
  "fairtypeid": 1,
  "default": false,
  "translations": [
    {
      "language": "de_DE",
      "text": "Messebau"
    },
    {
      "language": "en_GB",
      "text": "Exhibition construction"
    }
  ]
}'
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "created": {
    "default": false,
    "fairtypeid": 1,
    "translations": [
      {
        "language": "de_DE",
        "text": "Messebau"
      },
      {
        "language": "en_GB",
        "text": "Exhibition construction"
      }
    ]
  },
  "error_message": {},
  "contacttypeid": "35"
}
```

### HTTP request

`POST {baseurl}/contacts/types/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairtypeid | numeric | true |  |
default | boolean | false | false |
translations | array | true |  |

#### translations

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
language | string | true |  |
text | string | true |  |

## Update Contact Types

```shell
curl --location --request PUT '{baseurl}/contacts/types/{contacttypeid}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
  "fairtypeid": 1,
  "default": false,
  "translations": [
    {
      "language": "de_DE",
      "text": "Messebau changed"
    }
  ]
}'
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "updated": {
    "default": false,
    "fairtypeid": 1,
    "translations": [
      {
        "language": "de_DE",
        "text": "Messebau changed"
      }
    ]
  },
  "error_message": {},
  "contacttypeid": "35"
}
```

### HTTP request

`PUT {baseurl}/contacts/types/{contacttypeid}/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairtypeid | numeric | false |  |
default | boolean | false | |
translations | array | false |  |

#### translations

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
language | string | true |  |
text | string | true |  |

## Delete Contact Types

```shell
curl --location --request DELETE '{baseurl}/contacts/types/{contacttypeid}' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
  "deleted": true,
  "error": false,
  "contacttypeid": "35"
}
```

### HTTP request

`DELETE {baseurl}/contacts/types/{contacttypeid}/`
