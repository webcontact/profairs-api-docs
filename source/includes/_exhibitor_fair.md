# Exhibitors fair assignment
## Get exhibitor fair assignments

```shell
curl --location --request GET '{baseurl}/exhibitor-fair-assignments/' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "exhibitor_fair_assignments": [
        {
            "create_date": "April, 11 2016 10:57:00",
            "terms_and_conditions_confirmed": "",
            "change_user": 999,
            "mail_order_confirmation": "",
            "create_user": 35,
            "fairid": 3,
            "exhibitorfairid": 7,
            "is_highlighted": 1,
            "userid": "",
            "change_date": "February, 06 2021 19:46:47",
            "exhibitorid": 5
        },
        {
            "create_date": "June, 11 2016 13:33:57",
            "terms_and_conditions_confirmed": "",
            "change_user": 999,
            "mail_order_confirmation": "",
            "create_user": 999,
            "fairid": 3,
            "exhibitorfairid": 15,
            "is_highlighted": 0,
            "userid": "",
            "change_date": "June, 11 2016 13:33:57",
            "exhibitorid": 10
        }
    ]
}
```

### HTTP Request

`GET {baseurl}/exhibitor-fair-assignments/`

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairtypeid | numeric | false | |
fairid | numeric | false | |
exhibitorid | numeric | false | |
exhibitorfairid | numeric | false | |

## Create exhibitor fair assignment

```shell
curl --location --request POST '{baseurl}/exhibitor-fair-assignments/' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "exhibitorid": 1337,
    "fairid": 10,
    "is_highlighted": 1
}'
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "exhibitorfairid": "2610"
}
```

### HTTP Request

`POST {baseurl}/exhibitor-fair-assignments/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorid | numeric | true | |
fairid | numeric | true | |
is_highlighted | numeric | false | 0 | 1 = "yes", 0 = "no"

## Update exhibitor fair assignment

```shell
curl --location --request PUT '{baseurl}/exhibitor-fair-assignments/{exhibitorfairid}/' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "is_highlighted": 1
}'
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "debug": {
    "exhibitorfairid": "256",
    "x-api-key": null,
    "is_highlighted": 1
  },
  "exhibitorfairid": "256"
}
```

### HTTP Request

`PUT {baseurl}/exhibitor-fair-assignments/{exhibitorfairid}`


### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorfairid | numeric | true | |


### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
is_highlighted | numeric | false | 0 | 1 = "yes", 0 = "no"

## Delete exhibitor fair assignment

```shell
curl --location --request DELETE '{baseurl}/exhibitor-fair-assignments/{exhibitorid}/' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "exhibitorid": "1337"
}
```

### HTTP Request

`DELETE {baseurl}/exhibitor-fair-assignments/{exhibitorid}/`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorid | numeric | true | |

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairid | numeric | false | |


## Get exhibitor-fair logins

```shell
curl --location --request GET '{baseurl}/exhibitor-fair-assignments/{exhibitorfairid}/track-login/' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "exhibitorlogins": [
        {
            "date": "October, 27 2022 14:36:44 +0200",
            "id": 77,
            "exhibitorfairid": 1479
        }
    ]
}
```

### HTTP Request

`GET {baseurl}/exhibitor-fair-assignments/{exhibitorfairid}/track-login/`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorfairid | numeric | true | |
