# Texts

## Get text categories

```shell
curl --location --request GET '{baseurl}/text/categories/' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "categories": [
        {
            "de_DE": "Automatischer Mailversand Bestellbestätigung",
            "en_GB": "Automatischer Mailversand Bestellbestätigung",
            "id": 64
        },
        {
            "de_DE": "Einstellungen Einleitung",
            "en_GB": "Einstellungen Einleitung",
            "id": 63
        }
    ]
}
```
### HTTP request

`GET {baseurl}/text/`

## Get texts

```shell
curl --location --request GET '{baseurl}/text/' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "texts": [
        {
            "language": "de_DE",
            "locked": false,
            "change_user": 667,
            "date_from": "February, 24 2022 00:00:00",
            "create_user": 667,
            "categorieid": 65,
            "change_date": "February, 24 2022 16:10:36",
            "create_date": "February, 24 2022 16:10:36",
            "fairtypeid": 1,
            "introduction": "<p>Danke für Ihre Anmeldung!</p>",
            "title": "Test web://contact",
            "id": 137,
            "date_to": "September, 21 2022 00:00:00"
        },
        {
            "language": "de_DE",
            "locked": false,
            "change_user": 666,
            "date_from": "July, 15 2020 00:00:00",
            "create_user": 666,
            "categorieid": 35,
            "change_date": "August, 27 2021 16:02:32",
            "create_date": "August, 27 2021 16:02:32",
            "fairtypeid": 1,
            "introduction": "<p>Hier könnte ein Einleitungstext für die Job-Wall stehen, u.a. auch was für Dateitypen hochgeladen werden und in welcher Auflösung (DPI, Farbraum, ...)</p>\r\n",
            "title": "Stellenausschreibungen Job-Wall",
            "id": 122,
            "date_to": "December, 31 2030 00:00:00"
        },
    ],
    "error": false
}
```

### HTTP request

`POST {baseurl}/text/`

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairtypeid | numeric | true |
fairid | numeric | false |
categorieid | numeric | false |

## Set text

```shell
curl --location --request POST '{baseurl}/text/' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "fairtypeid": 1,
    "title": "Text über API",
    "introduction": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. ",
    "categorie": 1,
    "date_from": "2022-04-04 10:00:00",
    "date_to": "2023-04-04 10:00:00",
    "language": "de_DE",
    "locked": 0
}'
```

> The above command returns JSON structured like this:

```json
{
    "textid": "142",
    "error": false
}
```

### HTTP request

`POST {baseurl}/text/{textid}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairtypeid | numeric | true |
title | String | true |
introduction | String | true |
categorie | numeric | true |
date_from | date | true |
date_to | date | true |
language | String | true |

## Update text

```shell
curl --location --request PUT '{baseurl}/text/{textid}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "fairtypeid": 1,
    "title": "Text über API",
    "introduction": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. ",
    "categorie": 1,
    "date_from": "2022-04-04 10:00:00",
    "date_to": "2023-04-04 10:00:00",
    "language": "en_GB",
    "locked": 0
}'
```

> The above command returns JSON structured like this:

```json
{
    "textid": "142",
    "error": false
}
```

### HTTP request

`PUT {baseurl}/text/{textid}`

### URL Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
textid | numeric | true |

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairtypeid | numeric | false |
title | String | false |
introduction | String | false |
categorie | numeric | false |
date_from | date | false |
date_to | date | false |
language | String | false |


## Delete text

```shell
curl --location --request DELETE '{baseurl}/text/{textid}' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "textid": "142",
    "error": false
}
```

### HTTP request

`DELETE {baseurl}/text/{textid}`

### URL Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
textid | numeric | true |
