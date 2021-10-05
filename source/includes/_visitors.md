# Visitors

## Get visitors

```shell
curl --location --request GET 'http://profairs-api.tom.webcontact.de/rest/profairs-api/visitors/' \
--header 'X-API-KEY: 941c8937-0b05-4530-939c-6981a2adadc8' \
--header 'Cookie: CFID=61183; CFTOKEN=1836a8b27a83e72d-ECE47375-C2CC-3014-50DB7B77F688753A; JSESSIONID=85ABDC901794201705BBA688BCE5E9D8.cfusion'
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
curl --location --request GET 'http://profairs-api.tom.webcontact.de/rest/profairs-api/visitors/110' \
--header 'X-API-KEY: 941c8937-0b05-4530-939c-6981a2adadc8' \
--header 'Cookie: CFID=61183; CFTOKEN=1836a8b27a83e72d-ECE47375-C2CC-3014-50DB7B77F688753A; JSESSIONID=85ABDC901794201705BBA688BCE5E9D8.cfusion'
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

`GET {baseurl}/visitors/{visitor_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
visitor_id | numeric | true | |
datasource | string | true | |
fair_id | numeric | false | |
external | boolean | false | false |

## Create visitor

```shell
curl --location --request POST 'http://profairs-api.tom.webcontact.de/rest/profairs-api/visitors/' \
--header 'Content-Type: application/json' \
--header 'X-API-Key: 941c8937-0b05-4530-939c-6981a2adadc8' \
--header 'Cookie: CFID=61183; CFTOKEN=1836a8b27a83e72d-ECE47375-C2CC-3014-50DB7B77F688753A; JSESSIONID=7D2D77B5921E545A2E2A757DD6357EBF.cfusion' \
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
datasource | string | false | |
external_id | string | false | |
code_id | numeric | false | |
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
curl --location --request PUT 'http://profairs-api.tom.webcontact.de/rest/profairs-api/visitors/110' \
--header 'X-API-Key: 941c8937-0b05-4530-939c-6981a2adadc8' \
--header 'Content-Type: text/plain' \
--header 'Cookie: CFID=61183; CFTOKEN=1836a8b27a83e72d-ECE47375-C2CC-3014-50DB7B77F688753A; JSESSIONID=85ABDC901794201705BBA688BCE5E9D8.cfusion' \
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

`PUT {baseurl}/visitors/{visitor_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
external | boolean | true | false |
datasource | string | true | |
code_id | numeric | true | |
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
curl --location --request DELETE 'http://profairs-api.tom.webcontact.de/rest/profairs-api/visitors/2830' \
--header 'Content-Type: application/json' \
--header 'X-API-Key: 941c8937-0b05-4530-939c-6981a2adadc8' \
--header 'Cookie: CFID=61183; CFTOKEN=1836a8b27a83e72d-ECE47375-C2CC-3014-50DB7B77F688753A; JSESSIONID=85ABDC901794201705BBA688BCE5E9D8.cfusion'
```

> The above command returns this:

```json
Visitor deleted
```

### HTTP request

`DELETE {baseurl}/visitors/{visitor_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
visitor_id | numeric | true | |
datasource | string | true | |
external | boolean | true | false |
