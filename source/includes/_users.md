# Users

## Get users

```shell
curl --location --request GET '{baseurl}/user/' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "users": [
        {
            "group": "admin",
            "locked": false,
            "username": "alf",
            "firstname": "Thomas",
            "id": 59,
            "name": "Alf"
        },
        {
            "group": "scanner",
            "locked": false,
            "username": "scanner",
            "firstname": "scanner",
            "id": 42,
            "name": "barcode"
        }
    ]
}
```
### HTTP request

`GET {baseurl}/user/`

## Get user

```shell
curl --location --request GET '{baseurl}/user/{userid}' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "users": [
        {
            "group": "admin",
            "locked": false,
            "username": "alf",
            "firstname": "Thomas",
            "id": 59,
            "name": "Alf"
        }
    ]
}
```
### HTTP request

`GET {baseurl}/user/{userid}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| userid         | numeric | true    |         |

## Set user

```shell
curl --location --request POST '{baseurl}/user/' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "salutation": "Herr",
    "title": "Dr.",
    "firstname": "Max",
    "name": "Mustermann",
    "username": "username",
    "password": "password",
    "email": "max-mustermann@gmail.com",
    "telephone": "+49 12345 123",
    "address": "",
    "printnode_printer_id": "123456789",
    "printnode_api_key": "987654321",
    "group": 1
}'
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "userid": 1337
}
```
### HTTP request

`POST {baseurl}/user/`

### Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| salutation         | String | true    |         |
| firstname         | String | true    |         |
| name         | String | true    |         |
| username         | String | true    |         |
| password         | String | true    |         |
| email         | String | true    |         |
| group         | numeric | true    |         |
| locked         | boolean | true    |  false       |
| title         | String | false    |         |
| telephone         | String | false    |         |
| address         | String | false    |         |
| printnode_printer_id         | String | false    |         |
| printnode_api_key         | String | false    |         |

## Delete user

```shell
curl --location --request DELETE '{baseurl}/user/{userid}/' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "usersid": 1337
}
```
### HTTP request

`DELETE {baseurl}/user/{userid}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| userid         | numeric | true    |         |


## Get user-groups

```shell
curl --location --request GET '{baseurl}/groups' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "users": [
        {
            "group": "admin",
            "create_date": "March, 17 2016 11:02:15",
            "change_user": 999,
            "create_user": 999,
            "fairid": 0,
            "id": 1,
            "change_date": "March, 17 2016 11:02:15"
        },
        {
            "group": "Admin",
            "create_date": "March, 18 2016 14:49:36",
            "change_user": "",
            "create_user": 999,
            "fairid": 1,
            "id": 3,
            "change_date": ""
        }
    ]
}
```
### HTTP request

`GET {baseurl}/groups`

### Query Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| fairid         | numeric | false    |         |


## Set user-groups

```shell
curl --location --request POST '{baseurl}/groups' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "group": "API Group",
    "fairid": 7,
    "shipping": true
}'
```

> The above command returns JSON structured like this:

```json
{
    "users_group_id": "31",
    "error": false
}
```
### HTTP request

`POST {baseurl}/groups`

### Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| group         | String | true    |         |
| shipping         | Boolean | true    | false        |
| fairid         | numeric | false    |         |

## Get shop categories by user

```shell
curl --location --request GET '{baseurl}/user/{userid}/shop_categories/ \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "shop_categories": [
        {
            "create_date": "February, 25 2022 15:29:30",
            "locked": false,
            "change_user": 666,
            "parentid": 0,
            "fair": "Testmesse 2022",
            "usergroupid": 28,
            "create_user": 666,
            "id": 194,
            "categorie": "Standmöbel",
            "change_date": "February, 25 2022 16:21:32",
            "contactid": ""
        }
    ],
    "error": false
}
```
### HTTP request

`GET {baseurl}/user/{userid}/shop_categories/`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| userid         | numeric | true    |         |

### Query Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| language         | String | true    |         |

