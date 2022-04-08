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
            "interested_exhibitor_id": 5,
            "is_followup": true
        },
        {
            "date": "August, 30 2021 00:00:00",
            "contact_type": 1,
            "note": "Wir versuchen es auf jeden Fall, das Unternehmen zur Teilnahme zu bewegen.",
            "contact_person": "2823",
            "id": 2,
            "interested_exhibitor_id": 5,
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
            "interested_exhibitor_id": 5,
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
    "interested_exhibitor_id": 1337,
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
interested_exhibitor_id | numeric | true |
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
interested_exhibitor_id | numeric | false |
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
