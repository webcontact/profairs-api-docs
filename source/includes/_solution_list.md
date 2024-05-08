# Solution Lists

## Get solutions

```shell
curl --location --request GET '{baseurl}/solutions?fairtypeid=1' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "solutions": [
    {
      "language": "de_DE",
      "name": "Lösung 1",
      "id": 143
    },
    {
      "language": "en_GB",
      "name": "Lösung 1 EN",
      "id": 143
    },
    {
      "language": "de_DE",
      "name": "Lösung 2",
      "id": 144
    },
    {
      "language": "en_GB",
      "name": "Lösung 2 EN",
      "id": 144
    }
  ]
}
```

### HTTP request

`GET {baseurl}/solutions`

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairtypeid | numeric | true |
parentid | numeric | true | 0
language | string | false
exhibitorid | numeric | false
showlocked | boolean | false | false 


## Get solution by ID
```shell
curl --location --request GET '{baseurl}/solutions/{solutionid}' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "solutions": [
    {
      "language": "de_DE",
      "name": "Lösung 1",
      "id": 143
    },
    {
      "language": "en_GB",
      "name": "Lösung 1 EN",
      "id": 143
    }
  ]
}
```

### HTTP request

`GET {baseurl}/solutions/{solutionid}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
solutionid | numeric | true |
language | string | false |

## Create solution

```shell
curl --location --request POST '{baseurl}/solutions' \
--header 'X-API-KEY: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "parentid": 0,
    "fairtypeid": 1,
    "languages": [
        {
            "solution": "Lorem Ipsum",
            "language": "de_DE"
        },
        {
            "solution": "Lorem Ipsum EN",
            "language": "en_GB"
        }
    ]
}'
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "solution": 144,
  "error_message": {}
}
```

### HTTP request

`POST {baseurl}/solutions/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
parentid | numeric | true | | 0 |
fairtypeid | numeric | true | | |
languages | array of objects | true | |

### Languages details

| Parameter            | Type    | required | Default | Description |
| -------------------- | ------- | -------- | ------- | ----------- |
| language            | string | true    |       |
| solution           | string | true    |         |

## Update solution

```shell
curl --location --request PUT '{baseurl}/solutions/{solutionid}' \
--header 'X-API-KEY: {API-Key}' \
--header 'Content-Type: text/json' \
--data-raw '{
    "parentid": 0,
    "fairtypeid": 1,
    "languages": [
        {
            "solution": "Lösung 3",
            "language": "de_DE"
        },
        {
            "solution": "Lösung 3 EN",
            "language": "en_GB"
        }
    ]
}'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "solution": 143,
  "error_message": {}
}
```

### HTTP request

`PUT {baseurl}/solutions/{solutionid}`

### URL Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
solutionid | numeric | true |


### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
parentid | numeric | true | | 0 |
fairtypeid | numeric | true | | |
languages | array of objects | true | |

### Languages details

| Parameter            | Type    | required | Default | Description |
| -------------------- | ------- | -------- | ------- | ----------- |
| language            | string | true    |       |
| solution           | string | true    |         |

## Delete solution

```shell
curl --location --request DELETE '{baseurl}/solutions/{solutionid}' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "solution": 143,
  "error_message": {}
}
```

### HTTP request

`DELETE {baseurl}/solutions/{solutionid}`

### URL Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
solutionid | numeric | true |
