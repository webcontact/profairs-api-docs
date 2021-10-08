# Visitors

## Get visitors

```shell
curl --location --request GET '{baseurl}/visitors/' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "visitors": [
        {
            "zip": "1111",
            "telephone": "",
            "mobil": "",
            "codeid": 550,
            "longitude": "",
            "firstname": "Martin",
            "street": "XXX, 1",
            "email": "test5@expodat.pro",
            "company": "Test5 GmbH",
            "city": "Test Stadt",
            "country": "",
            "salutation": "Herr",
            "lastname": "Test",
            "newsletter": false,
            "title": "",
            "id": 85,
            "latitude": "",
            "externalid": ""
        }
    ]
}
```

### HTTP request

`GET {baseurl}/visitors/`

### Query parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairid | numeric | false | |

## Get visitor

```shell
curl --location --request GET '{baseurl}/visitors/{visitorid}' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "zip": "12345",
    "telephone": "+49 12345 6789",
    "mobil": "+49 12345 67890",
    "codeid": 1,
    "visitorid": 110,
    "longitude": "7.56737",
    "firstname": "Max",
    "street": "Musterstraße 123",
    "email": "max.mustermann@gmail.com",
    "company": "Muster GmbH 2",
    "city": "Mustercity",
    "country": "Deutschland",
    "salutation": "Herr",
    "lastname": "Mustermann",
    "newsletter": true,
    "title": "Dr.",
    "error": "false",
    "latitude": "-48.62420",
    "externalid": "A1C2"
}
```

### HTTP request

`GET {baseurl}/visitors/{visitorid}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
visitorid | numeric | true | |

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairid | numeric | false | |
external | boolean | false | false |

## Create visitor

```shell
curl --location --request POST '{baseurl}/visitors/' \
--header 'Content-Type: application/json' \
--header 'X-API-Key: {API-Key}' \
--data-raw '{
    "external_id": "A1C2",
    "company": "Muster GmbH",
    "title": "Dr.",
    "salutation": "Herr",
    "firstname": "Max",
    "lastname": "Mustermann",
    "street": "Musterstraße 123",
    "postalcode": "12345",
    "city": "Mustercity",
    "country": "Deutschland",
    "latitude": "-48.62420",
    "longitude": "7.56737",
    "telephone": "+49 12345 6789",
    "mobil": "+49 12345 67890",
    "email": "max.mustermann@gmail.com",
    "codeid": "1",
    "newsletter": true
}'
```

> The above command returns JSON structured like this:

```json
{
    "visitorid": "108",
    "error": "false"
}
```

### HTTP request

`POST {baseurl}/visitors/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
external_id | string | false | |
codeid | numeric | false | |
company | string | false |  |
title | string | false |  |
salutation | string | false |  |
firstname | string | false |  |
lastname | string | false |  |
street | string | false |  |
postalcode | string | false |  |
city | string | false |  |
country | string | false | Deutschland |
telephone | string | false |  |
mobil | string | false |  |
latitude | string | false |  |
longitude | string | false |  |
email | string | false |  |
newsletter | boolean | false | false |

## Update visitor

```shell
curl --location --request PUT '{baseurl}/visitors/{visitorid}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: text/plain' \
--data-raw '{
    "externalid": "A1C2",
    "company": "Muster GmbH 2",
    "title": "Dr.",
    "salutation": "Herr",
    "firstname": "Max",
    "lastname": "Mustermann",
    "street": "Musterstraße 123",
    "postalcode": "12345",
    "city": "Mustercity",
    "country": "Deutschland",
    "latitude": "-48.62420",
    "longitude": "7.56737",
    "telephone": "+49 12345 6789",
    "mobil": "+49 12345 67890",
    "email": "max.mustermann@gmail.com",
    "codeid": "1",
    "newsletter": true
}'
```

> The above command returns JSON structured like this:

```json
{
    "visitorid": "110",
    "error": "false"
}
```

### HTTP request

`PUT {baseurl}/visitors/{visitorid}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
visitorid | numeric | true |  |

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
external | boolean | true | false |
codeid | numeric | true | |
company | string | false |  |
title | string | false |  |
salutation | string | false |  |
firstname | string | false |  |
lastname | string | false |  |
street | string | false |  |
postalcode | string | false |  |
city | string | false |  |
country | string | false | Deutschland |
telephone | string | false |  |
mobil | string | false |  |
latitude | string | false |  |
longitude | string | false |  |
email | string | false |  |
newsletter | boolean | false | false |

## Delete visitor

```shell
curl --location --request DELETE '{baseurl}/visitors/{visitorid}' \
--header 'Content-Type: application/json' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns this:

```json
{
    "visitorid": "111",
    "error": false,
    "deleted": true
}
```

### HTTP request

`DELETE {baseurl}/visitors/{visitorid}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
visitorid | numeric | true | |

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
external | boolean | true | false |
