# Interested exhibitors

## Get interested exhibitors

```shell
curl --location --request GET '{baseurl}/acquisition/interested-exhibitors' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "interested-exhibitors": [
        {
            "interesse_code": "s8WSf4",
            "lexwareid": "",
            "longitude": "11.5868931",
            "email": "mail@unpainted.net",
            "vat_identification_number": "",
            "sevdeskid": "",
            "comment": "www.unpainted.net",
            "country": "DE",
            "fairid": "",
            "newsletter": true,
            "homepage": "http://www.unpainted.net/",
            "username": "99artfairs",
            "id": 5,
            "sorttitle": "-",
            "postalcode": "80202",
            "telephone": "-",
            "bexioid": "",
            "locked": false,
            "customer_number": "",
            "labelid": "32",
            "street": "Ohmstraße 22",
            "adress_verified": false,
            "company": "99artfairs GmbH",
            "city": "München",
            "password": "G2yU",
            "fairtypeid": 1,
            "additional_address": "",
            "latitude": "48.153304",
            "exhibitorid": 54
        },
        {
            "interesse_code": "7Kf4dS",
            "lexwareid": "",
            "longitude": "",
            "email": "oskar@keineahnung.de",
            "vat_identification_number": "",
            "sevdeskid": "",
            "comment": "www.gallery-weekend-berlin.de",
            "country": "DE",
            "fairid": "",
            "newsletter": true,
            "homepage": "",
            "username": "abc",
            "id": 6,
            "sorttitle": "-",
            "postalcode": "10785",
            "telephone": "+49 (0)30 7003 8771",
            "bexioid": "",
            "locked": false,
            "customer_number": "",
            "labelid": "32",
            "street": "Potsdamer Straße 93",
            "adress_verified": false,
            "company": "abc-gwb Veranstaltungs UG",
            "city": "Berlin",
            "password": "3x3H",
            "fairtypeid": 1,
            "additional_address": "",
            "latitude": "",
            "exhibitorid": 55
        }
    ],
    "error": false
}
```

### HTTP request

`GET {baseurl}/acquisition/interested-exhibitors/`

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairtypeid | numeric | true |


## Get interested exhibitor
```shell
curl --location --request GET '{baseurl}/acquisition/interested-exhibitors/{interestedexhibitorid}' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "interested-exhibitors": [
        {
            "interesse_code": "s8WSf4",
            "lexwareid": "",
            "longitude": "11.5868931",
            "email": "mail@unpainted.net",
            "vat_identification_number": "",
            "sevdeskid": "",
            "comment": "www.unpainted.net",
            "country": "DE",
            "fairid": "",
            "newsletter": true,
            "homepage": "http://www.unpainted.net/",
            "username": "99artfairs",
            "id": 5,
            "sorttitle": "-",
            "postalcode": "80202",
            "telephone": "-",
            "bexioid": "",
            "locked": false,
            "customer_number": "",
            "labelid": "32",
            "street": "Ohmstraße 22",
            "adress_verified": false,
            "company": "99artfairs GmbH",
            "city": "München",
            "password": "G2yU",
            "fairtypeid": 1,
            "additional_address": "",
            "latitude": "48.153304",
            "exhibitorid": 54
        }
    ],
    "error": false
}
```

### HTTP request

`GET {baseurl}/acquisition/interested-exhibitors/{interestedexhibitorid}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
interestedexhibitorid | numeric | true |

## Set interested exhibitor

```shell
curl --location --request POST '{baseurl}/acquisition/interested-exhibitors/' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "exhibitorid": 1337,
    "fairtypeid": 1
}'
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "interested_exhibitor_id": "37"
}
```

### HTTP request

`POST {baseurl}/acquisition/interested-exhibitors/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorid | numeric | true |
fairtypeid | numeric | true |

## Delete interested exhibitor

```shell
curl --location --request DELETE '{baseurl}/acquisition/interested-exhibitors/{exhibitorid}' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "interested_exhibitor_id": "37"
}
```

### HTTP request

`DELETE {baseurl}/acquisition/interested-exhibitors/{exhibitorid}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorid | numeric | true |

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairtypeid | numeric | true |
