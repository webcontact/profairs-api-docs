# Booths

## Get booths

```shell
curl --location --request GET '{baseurl}/booths/' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "booths": [
		{
            "booth_type_id": 3,
            "booth_type": "Blockstand",
            "booth_width": "876",
            "boothid": 1167,
            "booth_number": "G-88",
            "booth_assignment": "",
            "booth_length": "8",
            "exhibitor_fairid": 2380,
            "comment": "",
            "booth_size": "7008",
            "main_exhibitor_id": 0
        },
        {
            "booth_type_id": 2,
            "booth_type": "Eckstand",
            "booth_width": "44",
            "boothid": 1174,
            "booth_number": "44",
            "booth_assignment": "",
            "booth_length": "44",
            "exhibitor_fairid": 2379,
            "comment": "",
            "booth_size": "1936",
            "main_exhibitor_id": 0
        },
	]
}
```

### HTTP request

`GET {baseurl}/booths/`

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairid | numeric | false |

## Get booth

```shell
curl --location --request GET '{baseurl}/booths/{boothid}' \
--header 'X-API-Key: {API-Keys}' \
```

> The above command returns JSON structured like this:

```json
{
    "booths": [
        {
            "booth_type_id": 3,
            "booth_type": "Blockstand",
            "booth_width": "3.00",
            "boothid": 323,
            "booth_number": "A-420",
            "booth_assignment": "",
            "booth_length": "4.00",
            "exhibitor_fairid": 368,
            "comment": "",
            "main_exhibitor_id": 0
        }
    ],
    "error": false
}
```

### HTTP request

`GET {baseurl}/booths/{boothid}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
boothid | numeric | true |

## Create booth

```shell
curl --location --request POST '{baseurl}/booths/' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "exhibitor_fairid": 1,
    "booth_number": "D123",
    "booth_size": 25,
    "main_exhibitor": 0,
    "booth_width": 5,
    "booth_length": 5,
    "comment": "Lorem Ipsum",
    "booth_type_id": 1,
    "booth_assignment": 13
}'
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "boothid": "1180"
}
```

### HTTP request

`POST {baseurl}/booths/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitor_fairid | numeric | true | | |
booth_number | string | true | | |
booth_size | numeric | false | | |
main_exhibitor | numeric | false | | |
booth_width | numeric | false | | |
booth_length | numeric | false | | |
comment | string | false | | |
booth_type_id | numeric | true | | |
booth_assignment | numeric | false | | |

## Update booth

```shell
curl --location --request PUT '{baseurl}/booths/{boothid}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: text/plain' \
--data-raw '{
    "exhibitor_fairid": 1,
    "booth_number": "D123",
    "booth_size": 25,
    "main_exhibitor": 0,
    "booth_width": 5,
    "booth_length": 5,
    "comment": "Lorem Ipsum 1234",
    "booth_type_id": 1,
    "booth_assignment": 13
}'
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "boothid": 1179
}
```

### HTTP request

`PUT {baseurl}/booths/{boothid}`
### URL Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
boothid | numeric | true | | |

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitor_fairid | numeric | false | | |
booth_number | string | false | | |
booth_size | numeric | false | | |
main_exhibitor | numeric | false | | |
booth_width | numeric | false | | |
booth_length | numeric | false | | |
comment | string | false | | |
booth_type_id | numeric | false | | |
booth_assignment | numeric | false | | |

## Delete booth

```shell
curl --location --request DELETE '{baseurl}/booths/{boothid}' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "boothid": 1179,
    "deleted": true
}
```

`DELETE {baseurl}/booths/{boothid}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
boothid | numeric | true | |

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
forum_sync | boolean | true | false |
