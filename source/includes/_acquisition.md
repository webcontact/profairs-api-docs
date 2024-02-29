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
fairid | numeric | true |


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

`POST {baseurl}/acquisition/`

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

## Register Interested

```shell
curl --location '{baseurl}/acquisition/register-interested-exhibitors/?dry_run=false&debug=false' \
--header 'x-api-key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "company_name": "{company-name}",
    "salutation": "{salutation}",
    "first_name": "{first-name}",
    "last_name": "{last-name}",
    "email": "{email}",
    "send_email": {send-email},
    "language_code": "{language-code}",
    "fair_id": {fair-id}
}'
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "data": {
        "temp_passwort": "krv7Mb8vNW4Z",
        "exhibitor_id": 4080
    },
    "error_message": {},
    "warning_message": {}
}
```

This endpoint registers an interested exhibitor. It creates an exhibitor and a connected contact person. If `send_email` is set to `true`, it sends an email to the contact person. The email and the api response contains a temporary password, which can be used to login to profairs and set a permanent password.

### Flow

1. Create exhibitors. If an exhibitor with the same company name and short title exists, update the exhibitor. Otherwise, create a new exhibitor.
2. Create a contact person and add it to the created/updated exhibitor.
3. Create a temporary password for Keycloak if one doesn't already exist.
4. If `send_email` is set to true, send an email to the contact person containing the temporary password.

### HTTP request

`POST {baseurl}/acquisition/register-interested-exhibitors/?dry_run=false&debug=false`

### URL Parameters

| Parameter | Type | required | default | Description |
|-----------|------|----------|---------|-------------|
| dry_run | boolean | false | false| If set to true, the endpoint doesn't modify anything in the database. |
| debug | boolean | false | false | If set to true, it returns some additional data, which could be helpful to debug. |

### Parameters


| Parameter | Type | required | Default | Description |
|-----------|------|----------|---------|-------------|
| fair_id | integer | true | | The ID of the fair |
| language_code | string [`de_DE`, `en_GB`, etc...] | true | | The language profairs uses for e.g. the email |
| company_name | string | true | | The name of the company |
| salutation | string | true | | The salutation of the contact person |
| first_name | string | true | | The first name of the contact person |
| last_name | string | true | | The last name of the contact person |
| email | string | true | | The email address of the contact person |
| send_email | boolean | false | See description | Whether to send an email to the contact person. If omitted, the default will be the value, set in control. | 



### Response

The API returns a JSON object with the following fields:

| Field | Type | Description |
|-------|------|-------------|
| error | boolean | Whether an error occurred. |
| data | object | The data returned by the API |
| error_message | object | The error message, if an error occurred |
| warning_message | object | The warning message, if any |

If `error` is `false`, `data` will contain the following fields:

| Field | Type | Description |
|-------|------|-------------|
| temp_passwort | string | The temporary password, which can be used to login to profairs. |
| exhibitor_id | integer | The id of the created exhibitor |

If `error` is `true`, `error_message` will contain the error message.
