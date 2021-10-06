# Fair types

## Get fair types

```shell
curl --location --request GET '{baseurl}/fair_types/' \
--header 'X-API-Key: {API-Key}'
```

> The above command returns JSON structured like this:

```json
{
    "fair_types": [
       {
            "telephone": "+49 12345 6789",
            "fair_type_id": 1,
            "redirect_error": "http://",
            "contact_id": "",
            "fair_type": "MyEvent",
            "redirect": "http://"
        },
        {
            "telephone": "",
            "fair_type_id": 4,
            "redirect_error": "http://",
            "contact_id": "",
            "fair_type": "DemoFair",
            "redirect": "http://"
        }
    ],
    "error": false
}
```

### HTTP request

`GET {baseurl}/fairtypes/`

## Get fair type

```shell
curl --location --request GET '{baseurl}/fair_types/1/' \
--header 'X-API-Key: {API-Key}'
```

> The above command returns JSON structured like this:

```json
{
    "fair_types": [
        {
            "telephone": "+49 12345 6789",
            "fair_type_id": 1,
            "redirect_error": "http://",
            "contact_id": "",
            "fair_type": "MyEvent",
            "redirect": "http://"
        }
    ],
    "error": false
}
```

### HTTP request

`GET {baseurl}/fairtypes/{fair_type_id}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fair_type_id | integer | true |

## Create new fair type

```shell
curl --location --request POST '{baseurl}/fair_types/' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "fair_type": "Messetyp",
    "email": "mustermann@musterfirma.com",
    "telephone": "+49 12345 6789",
    "redirect": "https://...",
    "redirect_error": "https://error...",
    "contact_id": "1"
}'
```

> The above command returns JSON structured like this:

```json
{
    "fair_type_id": 3,
    "error": false
}
```

### HTTP request

`POST {baseurl}/fairtypes/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fair_type | string | false |  |
email | string | false |  |
telephone | string | false |  |
redirect | string | false | https:// |
redirect_error | string | false | https:// |
contact_id | integer | false |  |

## Update fair type

```shell
curl --location --request PUT '{baseurl}/fair_types/{fair_type_id}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "fair_type": "Fairtype 123",
    "email": "mustermann@musterfirma.de",
    "telephone": "+49 12345 6789",
    "redirect": "https://...",
    "redirect_error": "https://error...",
    "contact_id": "1"
}'
```

> The above command returns JSON structured like this:

```json
{
    "fair_type_id": 14,
    "error": false
}
```

### HTTP request

`POST {baseurl}/fairtypes/{fair_type_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fair_type_id | integer | true | |
datasource | string | true | |
fair_type | string | false | |
email | string | false | |
telephone | string | false | |
redirect | string | false | https:// |
redirect_error | string | false | https:// |
contact_person_id | integer | false | |

## Delete fair type

```shell
curl --location --request DELETE '{baseurl}/fair_types/{fair_type_id}' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "fair_type_id": 3,
    "error": false,
    "deleted": true
}
```

### HTTP request

`DELETE {baseurl}/fairtypes/{fair_type_id}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fair_type_id | integer | true | |
