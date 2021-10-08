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
            "fairtypeid": 1,
            "redirect_error": "http://",
            "contactid": "",
            "fair_type": "MyEvent",
            "redirect": "http://"
        },
        {
            "telephone": "",
            "fairtypeid": 4,
            "redirect_error": "http://",
            "contactid": "",
            "fair_type": "DemoFair",
            "redirect": "http://"
        }
    ],
    "error": false
}
```

### HTTP request

`GET {baseurl}/fair_types/`

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
            "fairtypeid": 1,
            "redirect_error": "http://",
            "contactid": "",
            "fair_type": "MyEvent",
            "redirect": "http://"
        }
    ],
    "error": false
}
```

### HTTP request

`GET {baseurl}/fair_types/{fairtypeid}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairtypeid | numeric | true |

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
    "contactid": "1"
}'
```

> The above command returns JSON structured like this:

```json
{
    "fairtypeid": 3,
    "error": false
}
```

### HTTP request

`POST {baseurl}/fair_types/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fair_type | string | true |  |
email | string | true |  |
telephone | string | true |  |
redirect | string | true | https:// |
redirect_error | string | true | https:// |
contactid | numeric | false |  |

## Update fair type

```shell
curl --location --request PUT '{baseurl}/fair_types/{fairtypeid}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "fair_type": "Fairtype 123",
    "email": "mustermann@musterfirma.de",
    "telephone": "+49 12345 6789",
    "redirect": "https://...",
    "redirect_error": "https://error...",
    "contactid": "1"
}'
```

> The above command returns JSON structured like this:

```json
{
    "fairtypeid": 14,
    "error": false
}
```

### HTTP request

`PUT {baseurl}/fair_types/{fairtypeid}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairtypeid | numeric | true | |

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fair_type | string | false | |
email | string | false | |
telephone | string | false | |
redirect | string | false | https:// |
redirect_error | string | false | https:// |
contactid | numeric | false | |

## Delete fair type

```shell
curl --location --request DELETE '{baseurl}/fair_types/{fairtypeid}' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "fairtypeid": 3,
    "error": false,
    "deleted": true
}
```

### HTTP request

`DELETE {baseurl}/fair_types/{fairtypeid}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairtypeid | numeric | true | |
