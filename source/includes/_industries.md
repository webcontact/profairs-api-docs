# Industries

## Get focus industries

```shell
curl --location --request GET '{baseurl}/industries/?fairtypeid=2' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "industries": [
        {
            "language": "de_DE",
            "industry": "Architektur",
            "industryid": 34,
            "parentid": 0,
            "ordernumber": 0
        },
        {
            "language": "de_DE",
            "industry": "Betriebswirtschaftslehre",
            "industryid": 35,
            "parentid": 0,
            "ordernumber": 0
        },
        {
            "language": "de_DE",
            "industry": "Maschinenbau",
            "industryid": 45,
            "parentid": 0,
            "ordernumber": 0
        },
        {
            "language": "de_DE",
            "industry": "Mathematik",
            "industryid": 46,
            "parentid": 0,
            "ordernumber": 0
        },
        {
            "language": "de_DE",
            "industry": "Technik- und Management ",
            "industryid": 54,
            "parentid": 0,
            "ordernumber": 0
        }
    ],
    "error": false
}
```

### HTTP request

`GET {baseurl}/industries/`

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairtypeid | numeric | true | |
language | string |false ||
parentid | numeric |true | 0 |
exhibitorid | numeric |false ||
showlocked | boolean |false ||

## Get industrie

```shell
curl --location --request GET '{baseurl}/industries/2/' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "industries": [
        {
            "language": "de_DE",
            "industry": "Webentwicklung",
            "industryid": 2,
            "parentid": 0,
            "ordernumber": 0
        }
    ],
    "error": false
}
```

### HTTP request

`GET {baseurl}/industries/{industryid}`

### URL Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
idustryid | numeric | true | |

### Query Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
language | string | false | | 

## Create industrie

```shell
curl --location --request POST '{baseurl}/industries/' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "parentid": 1,
    "ordernumber": 0,
    "fairtypeid": 1,
    "languages": [
        {
            "industry": "Musterbranch",
            "language": "de_DE"
        },
        {
            "industry": "Musterbranch EN",
            "language": "en_GB"
        }
    ]
}'
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "industryid": "68"
}
```

### HTTP request

`POST {baseurl}/industries/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
parentid | numeric | true | 0 | |
ordernumber | numeric | true | 0 | |
messetypid | numeric | true | | |
languages | array of objects | true | |

### Languages details

| Parameter            | Type    | required | Default | Description |
| -------------------- | ------- | -------- | ------- | ----------- |
| language            | string | true    |       |
| industry           | string | true    |         |

## Update industrie

```shell
curl --location --request PUT '{basepath}/industries/{idustryid}/' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "parentid": 1,
    "ordernumber": 0,
    "fairtypeid": 1,
    "languages": [
        {
            "industry": "Musterbranch Updated",
            "language": "de_DE"
        },
        {
            "industry": "Musterbranch EN Updated",
            "language": "en_GB"
        }
    ]
}'
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "industryid": 67
}
```

### HTTP request

`PUT {baseurl}/industries/{industryid}`

### URL Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
industryid | numeric | true | | |

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
parentid | numeric | true | 0 | |
ordernumber | numeric | true | 0 | |
messetypid | numeric | true | | |
languages | array of objects | true | |

### Languages details

| Parameter            | Type    | required | Default | Description |
| -------------------- | ------- | -------- | ------- | ----------- |
| language            | string | true    |       |
| industry           | string | true    |         |

## Delete industrie

```shell
curl --location --request DELETE '{baseurl}/industries/{industryid}/' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "industryid": 66,
    "deleted": true
}
```

### HTTP request

`DELETE {baseurl}/industries/{industryid}`

### Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
industryid | numeric | true | | |
