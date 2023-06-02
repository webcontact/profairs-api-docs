# Booths

## Get booths

```shell
curl --location --request GET '{baseurl}/booths/' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    {
    "booths": [
        {
            "articleid": "",
            "change_user": 999,
            "create_user": 999,
            "change_date": "February, 03 2022 10:48:33",
            "boothwidth": "3.0",
            "boothnumber": "2-634",
            "boothtype": 0,
            "create_date": "February, 02 2022 10:44:02",
            "syncstatus": 0,
            "boothsize": "15.0",
            "fairid": 7,
            "boothid": 30,
            "boothdepth": "5.0"
        },
        {
            "articleid": "",
            "change_user": 999,
            "create_user": 999,
            "change_date": "February, 03 2022 10:48:33",
            "boothwidth": "4.00",
            "boothnumber": "2-614",
            "boothtype": "",
            "create_date": "February, 02 2022 10:44:02",
            "syncstatus": 0,
            "boothsize": "",
            "fairid": 7,
            "boothid": 29,
            "boothdepth": "3.00"
        }
    ]
}
```

### HTTP request

`GET {baseurl}/booths/`

### Query Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| fairid         | numeric | false    |         |
| boothid         | numeric | false    |         |
| exhibitorboothid         | numeric | false    |         |


## Set booth

```shell
curl --location --request POST '{baseurl}/booths/' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "fairid": 7,
    "boothnumber": "A-1337",
    "boothwidth": 5,
    "boothdepth": 3,
    "boothsize": 15,
    "articleid": 1337,
    "boothtype": 1
}'
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "boothid": "1553"
}
```

### HTTP request

`POST {baseurl}/booths/`

### Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| boothnumber         | String | true    |         |
| boothwidth         | numeric | true    |         |
| boothdepth         | numeric | true    |         |
| fairid         | numeric | false    |         |
| boothsize         | numeric | false    |         |
| articleid         | numeric | false    |         |
| boothtype         | numeric | false    |         |


## Delete booth

```shell
curl --location --request DELETE '{baseurl}/booths/{boothid}' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "boothid": "1551"
}
```

### HTTP request

`DELETE {baseurl}/booths/{boothid}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| boothid         | numeric | true    |         |


## Update booth

```shell
curl --location --request PUT '{baseurl}/booths/{boothid}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "fairid": 7,
    "boothnumber": "A-1338",
    "boothwidth": 5,
    "boothdepth": 3,
    "boothsize": 15,
    "articleid": 1337,
    "boothtype": 1
}'
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "boothid": 1551
}
```

### HTTP request

`PUT {baseurl}/booths/{boothid}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| boothid         | numeric | true    |         |

### Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| boothnumber         | String | false    |         |
| boothwidth         | numeric | false    |         |
| boothdepth         | numeric | false    |         |
| fairid         | numeric | false    |         |
| boothsize         | numeric | false    |         |
| articleid         | numeric | false    |         |
| boothtype         | numeric | false    |         |


## Get booth types

```shell
curl --location --request GET '{baseurl}/booths/types/' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "type": [
        {
            "id": 1,
            "type": "Reihenstand 21"
        },
        {
            "id": 2,
            "type": "Eckstand"
        }
    ]
}
```

### HTTP request

`GET {baseurl}/booths/types/`

### Query Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| id         | numeric | false    |         |
| language         | String | true    | de_DE        |



## Get exhibitor booth assignments

```shell
curl --location --request GET '{baseurl}/booths/exhibitor/' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "assingments": [
        {
            "boothassignment": "",
            "create_date": "April, 05 2019 15:05:04",
            "change_user": 999,
            "exhibitorboothid": 1108,
            "syncstatus": 0,
            "create_user": 999,
            "note": "",
            "mainexhibitorid": 2279,
            "boothid": 26,
            "change_date": "April, 05 2019 15:05:04",
            "exhibitorfairid": 2280
        },
        {
            "boothassignment": "",
            "create_date": "June, 25 2019 17:03:19",
            "change_user": 667,
            "exhibitorboothid": 1121,
            "syncstatus": 0,
            "create_user": 667,
            "note": "",
            "mainexhibitorid": 0,
            "boothid": 562,
            "change_date": "June, 25 2019 17:03:19",
            "exhibitorfairid": 2305
        }
    ]
}
```

### HTTP request

`GET {baseurl}/booths/exhibitor/`

### Query Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| fairid         | numeric | false    |         |
| exhibitorid         | numeric | false    |         |
| exhibitorfairid         | numeric | false    |         |
| exhibitorboothid         | numeric | false    |         |
| mainexhibitorid         | numeric | false    |         |
| language         | String | false    | de_DE        |


## Set exhibitor booth assignment

```shell
curl --location --request POST '{baseurl}/booths/exhibitor/{boothid}/' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "fairid": 7,
    "exhibitorfairid": 96
}'
```

> The above command returns JSON structured like this:

```json
{
    "exhibitorboothid": "1405",
    "error": false
}
```

### HTTP request

`POST {baseurl}/booths/exhibitor/{boothid}/`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| boothid         | numeric | true    |         |

### Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| fairid         | numeric | true    |         |
| exhibitorfairid| numeric | true    |         |
| mainexhibitor  | numeric | true    | 0       |
| note  | String | false    |        |
| postingdate  | date | false    |        |
| boothassignment  | String | false    |        |
| variantid  | numeric | false    |        | Specified variant is ordered when creating |


## Delete exhibitor booth assignment

```shell
curl --location --request DELETE '{baseurl}/booths/exhibitor/{exhibitorboothid}/' \
--header 'X-API-Key: API-Key' \
```

> The above command returns JSON structured like this:

```json
{
    "exhibitorboothid": "1401",
    "error": false
}
```

### HTTP request

`DELETE {baseurl}/booths/exhibitor/{exhibitorboothid}/`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| exhibitorboothid         | numeric | true    |         |


## Get booth reservation

```shell
curl --location --request GET '{baseurl}/booths/reservation/{reservationhash}/' \
--header 'X-API-Key: API-Key' \
```

> The above command returns JSON structured like this:

```json
{
    "fairid": "3",
    "boothids": "S-23,S-24,S-25",
    "hash": "XXXXXXXXXXXXXXXXXXXXXX",
    "expire_date": "2023-06-02 08:13:11",
    "error": false
}
```

### HTTP request

`GET {baseurl}/booths/reservation/{reservationhash}/`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| reservationhash     | string  | true     |         |