# Acquisition

## Get acquisition

```shell
curl --location --request GET '{baseurl}/acquisition' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "acquisition": [
        {
            "date": "September, 09 2021 00:00:00",
            "contact_type": 2,
            "note": "",
            "contact_person": "2823",
            "id": 1,
            "interestedexhibitorid": 5,
            "is_followup": true
        },
        {
            "date": "August, 30 2021 00:00:00",
            "contact_type": 1,
            "note": "Wir versuchen es auf jeden Fall, das Unternehmen zur Teilnahme zu bewegen.",
            "contact_person": "2823",
            "id": 2,
            "interestedexhibitorid": 5,
            "is_followup": false
        }
    ]
}
```

### HTTP request

`GET {baseurl}/acquisition/`

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairid | numeric | false |


## Get acquisition by ID
```shell
curl --location --request GET '{baseurl}/acquisition/{acquisitionid}' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "acquisition": [
        {
            "date": "September, 09 2021 00:00:00",
            "contact_type": 2,
            "note": "",
            "contact_person": "2823",
            "id": 1,
            "interestedexhibitorid": 5,
            "is_followup": true
        }
    ]
}
```

### HTTP request

`GET {baseurl}/acquisition/{acquisitionid}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
acquisitionid | numeric | true |

## Set acquisition

```shell
curl --location --request POST '{baseurl}/acquisition/' \
--header 'X-API-KEY: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "interestedexhibitorid": 1337,
    "contact_type": 2,
    "contact_person_id": 1337,
    "date": "2022-03-21",
    "note": "Lorem Impsum",
    "is_followup": true
}'
```

> The above command returns JSON structured like this:

```json
{
    "acquisitionid": "25",
    "error": false
}
```

### HTTP request

`PUT {baseurl}/acquisition/{acquisitionid}`

### Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
acquisitionid | numeric | true |
date | date | true |
contact_type | String | true |
contact_person_id | numeric | true |
interestedexhibitorid | numeric | true |
note | String | false |
is_followup | Boolean | true | false |

## Update acquisition

```shell
curl --location --request PUT '{baseurl}/acquisition/{acquisitionid}' \
--header 'X-API-KEY: {API-Key}' \
--header 'Content-Type: text/json' \
--data-raw '{
    "contact_type": 3,
    "contact_person_id": 123,
    "date": "2022-03-22",
    "note": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.",
    "is_followup": false
}'
```

> The above command returns JSON structured like this:

```json
{
    "acquisitionid": "25",
    "error": false
}
```

### HTTP request

`PUT {baseurl}/acquisition/{acquisitionid}`

### URL Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
acquisitionid | numeric | true |


### Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
date | date | false |
contact_type | String | false |
contact_person_id | numeric | false |
interestedexhibitorid | numeric | false |
note | String | false |
is_followup | Boolean | true | false |

## Delete acquisition

```shell
curl --location --request DELETE '{baseurl}/acquisition/{acquisitionid}' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "acquisitionid": "25",
    "error": false
}
```

### HTTP request

`DELETE {baseurl}/acquisition/{acquisitionid}`

### URL Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
acquisitionid | numeric | true |


## Get interessted exhibitors

```shell
curl --location --request GET '{baseurl}/acquisition/interested-exhibitors' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "interested-exhibitors": [
        {
            "longitude": "",
            "customer_number": "",
            "company": "Best Western Riverview Inn",
            "lexwareid": "",
            "telephone": "01413-348876",
            "interesse_code": "yC79M9",
            "latitude": "",
            "additional_address": "Hertfordshire",
            "password": "Kc3aaE7v",
            "labelid": "",
            "adress_verified": false,
            "comment": "",
            "fairid": 1,
            "bexioid": "",
            "city": "Woodhall Farm Ward",
            "exhibitorid": 2948,
            "vat_identification_number": "",
            "homepage": "http://www.bestwesternriverviewinn.co.uk",
            "newsletter": false,
            "username": "bestweste",
            "email": "shawana@yahoo.com",
            "postalcode": "HP2 7JP",
            "country": "United Kingdom",
            "interestedexhibitorid": 23,
            "sorttitle": "Best Western Riverview Inn",
            "sevdeskid": "",
            "street": "33 Vipond St",
            "locked": false,
            "fairtypeid": 1
        },
        "error": false
    ]
}
```
### HTTP request

`GET {baseurl}/acquisition/interested-exhibitors`

### URL Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairtypeid | numeric | true |
interestedexhibitorid | numeric | false |

## Set interessted exhibitor

```shell
curl --location '{baseurl}/acquisition/interested-exhibitors?fairtypeid={fairtypeid}&interestedexhibitorid={interestedexhibitorid}' \
--header 'X-API-KEY: {API-Key}' \
--header 'Content-Type: application/json' \
--data '{
    "fairtypeid": 1,
    "fairid": 16,
    "exhibitorid": 1
}'
```

> The above command returns JSON structured like this:

```json
{
    "interestedexhibitorid": "77",
    "error": false
}
```
### HTTP request

`POST {baseurl}/acquisition/interested-exhibitors`

### Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairtypeid | numeric | true |
exhibitorid | numeric | true |
fairid | numeric | false |

## Delete interessted exhibitor

```shell
curl --location --request DELETE '{baseurl}/acquisition/interessted exhibitor/{interestedexhibitorid}' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "interestedexhibitorid": "25",
    "error": false
}
```

### HTTP request

`DELETE {baseurl}/acquisition/interested-exhibitors/{interestedexhibitorid}`

### URL Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
interestedexhibitorid | numeric | true |


## Assign label to interessted exhibitor

```shell
curl --location '{baseurl}/acquisition/interested-exhibitors/{interestedexhibitorid}/assign-label' \
--header 'X-API-KEY: {API-Key}' \
--header 'Content-Type: application/json' \
--data '{
    "labelid": {labelid}
}'
```

> The above command returns JSON structured like this:

```json
{
    "interestedexhibitorid": "77",
    "error": false
}
```
### HTTP request

`POST {baseurl}/acquisition/interested-exhibitors/{interestedexhibitorid}/assign-label`

### URL Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
interestedexhibitorid | numeric | true |

### Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
labelid | numeric | true |