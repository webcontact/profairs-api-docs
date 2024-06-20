# Product Groups

## Get product groups

```shell
curl --location --request GET '{baseurl}/product-groups?fairtypeid=1' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "product_groups": [
    {
      "language": "de_DE",
      "parentid": 0,
      "ordernumber": 0,
      "name": "Agrarprodukte",
      "id": 143
    },
    {
      "language": "en_GB",
      "parentid": 0,
      "ordernumber": 0,
      "name": "Agricultural products",
      "id": 143
    },
    {
      "language": "de_DE",
      "parentid": 0,
      "ordernumber": 0,
      "name": "Nutzholz",
      "id": 144
    },
    {
      "language": "en_GB",
      "parentid": 0,
      "ordernumber": 0,
      "name": "Timber",
      "id": 144
    }
  ]
}
```

### HTTP request

`GET {baseurl}/product-groups`

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairtypeid | numeric | true |
parentid | numeric | false
language | string | false
exhibitorid | numeric | false
showlocked | boolean | false | false 

## Get product group by Id
```shell
curl --location --request GET '{baseurl}/product-groups/{product_group_id}' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "product_groups": [
    {
      "language": "de_DE",
      "name": "Lösung 1",
      "parentid": 0,
      "ordernumber": 0,
      "id": 143
    },
    {
      "language": "en_GB",
      "name": "Lösung 1 EN",
      "parentid": 0,
      "ordernumber": 0,
      "id": 143
    }
  ]
}
```
### HTTP request

`GET {baseurl}/product-groups/{product_group_id}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
product_group_id | numeric | true |
fairtypeid | numeric | false |
language | string | false |

## Create product group

```shell
curl --location --request POST '{baseurl}/product-groups/' \
--header 'X-API-KEY: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "parentid": 0,
    "ordernumber": 0,
    "fairtypeid": 1,
    "languages": [
        {
            "product_group": "Lorem Ipsum",
            "language": "de_DE"
        },
        {
            "product_group": "Lorem Ipsum EN",
            "language": "en_GB"
        }
    ]
}'
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "id": 144,
  "error_message": {}
}
```

### HTTP request

`POST {baseurl}/product-groups/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
parentid | numeric | true | 0 | |
ordernumber | numeric | true | 0 | |
fairtypeid | numeric | true | | |
languages | array of objects | true | |

### Languages details

| Parameter            | Type    | required | Default | Description |
| -------------------- | ------- | -------- | ------- | ----------- |
| language            | string | true    |       |
| product_group           | string | true    |         |

## Update product group

```shell
curl --location --request PUT '{baseurl}/product-groups/{product_group_id}' \
--header 'X-API-KEY: {API-Key}' \
--header 'Content-Type: text/json' \
--data-raw '{
    "parentid": 0,
    "ordernumber": 0,
    "fairtypeid": 1,
    "languages": [
        {
            "product_group": "Lösung 3",
            "language": "de_DE"
        },
        {
            "product_group": "Lösung 3 EN",
            "language": "en_GB"
        }
    ]
}'
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "id": 143,
  "error_message": {}
}
```

### HTTP request

`PUT {baseurl}/product-groups/{product_group_id}`

### URL Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
product_group_id | numeric | true |

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
parentid | numeric | true | 0 | |
ordernumber | numeric | true | 0 | |
fairtypeid | numeric | true | | |
languages | array of objects | true | |

### Languages details

| Parameter            | Type    | required | Default | Description |
| -------------------- | ------- | -------- | ------- | ----------- |
| language            | string | true    |       |
| product_group           | string | true    |         |

## Delete product group

```shell
curl --location --request DELETE '{baseurl}/product-groups/{product_group_id}' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "id": 143,
  "error_message": {}
}
```

### HTTP request

`DELETE {baseurl}/product-groups/{product_group_id}`

### URL Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
product_group_id | numeric | true |
