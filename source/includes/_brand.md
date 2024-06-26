# Brands

## Get brands

```shell
curl --location --request GET '{baseurl}/brands?fairtypeid=1' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "brands": [
    {
      "language": "de_DE",
      "groupid": 11,
      "name": "Deutz",
      "id": 12
    },
    {
      "language": "de-DE",
      "name": "John Deer",
      "groupid": 11,
      "id": 13
    }
  ]
}
```

### HTTP request

`GET {baseurl}/brands`

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairtypeid | numeric | true |
language | string | false 


## Get brand by Id
```shell
curl --location --request GET '{baseurl}/brands/{brand_id}' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "brands": {
    "language": "de_DE",
    "groupid": 11,
    "name": "Deutz",
    "id": 12
  }
}
```

### HTTP request

`GET {baseurl}/brands/{brand_id}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
brand_id | numeric | true |

## Create brand

```shell
curl --location --request POST '{baseurl}/brands' \
--header 'X-API-KEY: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
  "fairtypeid": "1",
  "name": "Test Marke",
  "language": "de_DE",
  "groupid": "15"
}'
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "id": 144,
  "groupid": 15,
  "error_message": {}
}
```

### HTTP request

`POST {baseurl}/brands/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairtypeid | numeric | true | | |
name | numeric | true | | |
language | string | true | |
groupid | numeric | false | |


## Update brand

```shell
curl --location --request PUT '{baseurl}/brands/{brand_id}' \
--header 'X-API-KEY: {API-Key}' \
--header 'Content-Type: text/json' \
--data-raw '{
  "fairtypeid": "1",
  "name": "John Deer",
  "language": "de-DE"
}'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "id": 14,
  "error_message": {}
}
```

### HTTP request

`PUT {baseurl}/brands/{brand_id}`

### URL Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
brand_id | numeric | true |


### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairtypeid | numeric | true | | |
name | string | true | | |
language | string | true | |

## Delete brand

```shell
curl --location --request DELETE '{baseurl}/brands/{brand_id}' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "id": 16,
  "error_message": {}
}
```

### HTTP request

`DELETE {baseurl}/brands/{brand_id}`

### URL Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
brand_id | numeric | true |
