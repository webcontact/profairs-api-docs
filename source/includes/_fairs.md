# Fairs

## Get fairs

```shell
curl --location --request GET '{baseurl}/fairs/' \
--header '{API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "fairs": [
        {
            "location": "",
            "fair": "Karrieremesse 2022",
            "date_from": "2023-11-30 12:00:00",
            "fairid": 2,
            "fair_type_id": 2,
            "shop_closes": "2023-04-30 12:00:00",
            "shop_no_cancellations": "2023-04-26 12:00:00",
            "date_to": "2023-11-30 12:00:00"
        },
        {
            "location": "Mittelerde",
            "fair": "Demofair 2022",
            "date_from": "2022-11-08 12:00:00",
            "fairid": 1,
            "fair_type_id": 1,
            "shop_closes": "2022-03-31 12:00:00",
            "shop_no_cancellations": "2022-03-16 12:00:00",
            "date_to": "2022-11-10 12:00:00"
        }
    ],
    "error": false
}
```

### HTTP request

`GET {baseurl}/fairs/`

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairtypeid | numeric | false |   |
showLocked | boolean | true | true  |


## Get fair

```shell
curl --location --request GET '{baseurl}/fairs/{fairid}' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "fairs": [
        {
            "location": "",
            "fair": "Karrieremesse 2022",
            "date_from": "2023-11-30 12:00:00",
            "fairid": 2,
            "fair_type_id": 2,
            "shop_closes": "2023-04-30 12:00:00",
            "shop_no_cancellations": "2023-04-26 12:00:00",
            "date_to": "2023-11-30 12:00:00"
        }
    ],
    "error": false
}
```

### HTTP request

`GET {baseurl}/fairs/{fairid}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairid | numeric | true |  |

### Query Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
logo | boolean | true | false  |
motion | boolean | true | false  |

## Create fair

```shell
curl --location --request POST '{baseurl}/fairs/' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "fair": "Musterfair",
    "fairtypeid": "1",
    "location": "Pforzheim",
    "shop_no_cancellations": "2021-12-31 15:00:00",
    "shop_closes": "2022-01-31 15:00:00",
    "url_logout": "https://...",
    "css": "profairs-default",
    "price_per_voucher": "10.00",
    "date_from": "2022-02-13 00:00:00",
    "date_to": "2022-02-15 00:00:00"
}'
```

> The above command returns JSON structured like this:

```json
{
    "fairid": "27",
    "error": false
}
```

### HTTP request

`POST {baseurl}/fairs/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fair | string | false |  |
fairtypeid | numeric | false |  |
location | string | false |  |
shop_no_cancellations | string | false |  |
shop_closes | string | false |  |
css | string | true | profairs-default  |
url_logout | string | false |  |
price_per_voucher | string | false |  |
date_from | string | false |  |
date_to | string | false |  |

## Upload file

```shell
curl --location --request POST '{baseurl}/fairs/upload/' \
--header 'X-API-Key: {API-Key}' \
--form 'file=@"{img_path}"' \
--form 'fairid="26"' \
--form 'type="motion"'
```

> The above command returns JSON structured like this:

```json
{
    "fairid": "26",
    "error": false
}
```

### HTTP request

`POST {baseurl}/fairs/upload/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
type | string | true |  |
file | binary | true |  |
fairid | numeric | true |  |

## Update fair

```shell
curl --location --request PUT '{baseurl}/fairs/{fairid}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: text/plain' \
--data-raw '{
    "fair": "Musterfair2",
    "fairtypeid": "1",
    "location": "Pforzheim",
    "shop_no_cancellations": "2021-12-31 15:00:00",
    "shop_closes": "2022-01-31 15:00:00",
    "url_logout": "https://...",
    "css": "profairs-default",
    "price_per_voucher": "10.00",
    "date_from": "2022-02-13 00:00:00",
    "date_to": "2022-02-15 00:00:00"
}'
```

> The above command returns JSON structured like this:

```json
{
    "fairid": "25",
    "error": false
}
```

### HTTP request

`PUT {baseurl}/fairs/{fairid}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairid | string | true | |
### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fair | string | false | |
fairtypeid | numeric | false | |
location | string | false | |
shop_no_cancellations | string | false | |
shop_closes | string | false | |
css | string | true | profairs-default |
url_logout | string | false | |
price_per_voucher | string | false | |
date_from | string | false | |
date_to | string | false | |

## Delete fair

```shell
curl --location --request DELETE '{baseurl}/fairs/{fairid}' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "fairid": 26,
    "error": false,
    "deleted": true
}
```

### HTTP request

`DELETE {baseurl}/fairs/{fairid}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairid | numeric | true |
