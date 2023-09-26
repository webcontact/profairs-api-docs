# Hall planning


## Missing values

If a value in the database is optional and missing for a record requested via the API, then the key of the value is simply not returned instead of being 'null'. 


## Standrequest

```curl
curl --location '{baseurl}/hall_planning/standrequest/1535' \
--header 'x-API-Key: {API-Key}'
```

> The above command returns JSON structured like this:

```json
{
    "data": [
        {
            "standwunsch": "",
            "booth_width": 10,
            "booth_depth": 2,
            "status": "neu aufplanen",
            "booth_type": 3,
            "platzierungswunsch": "",
            "id": 1,
            "exhibitor": {
                "main_industrie_id": 81,
                "name": "web://contact GmbH",
                "exhibitor_fair_id": 1535
            }
        }
    ],
    "error": false
}
```


`{baseurl}/hall_planning/standrequest`  
`{baseurl}/hall_planning/standrequest/{exhibitor_fair_id}`

This endpoint returns the data of the stand requests.

The `exhibitor_fair_id` is an optional parameter. If this is set, the endpoint returns all booth requests that are assigned to the respective exhibitor. If this is not set, all booth requests will be returned.

This data must be sent back to profairs with the planned stand:

1. `standwunsch_id`, to which the planned stand refers to
2. `exhibitor_fair_id`

The status is an enum, which can have the following values:

status | meaning
---|---
`neu aufplanen` | The stand request is assigned to at least one stand proposal that is not locked.
`umplanen` | The stand request is not assigned to a stand proposal that is not locked.

### Response Codes

code | meaning
---|---
`200` | The request was successful.
`406` | The request was not successful because probably the data was sent to the API incorrectly.


## [GET] Branche

```curl
curl --location '{baseurl}/hall_planning/standrequest/industrie/4' \
--header 'x-API-Key: {API-Key}'
```

> The above command returns JSON structured like this:

```json
{
    "data": {
        "parent_industrie": {
            "name": "Onlinemarketing",
            "id": 5
        },
        "child_industrie_list": [
            {
                "name": "Hagelsalz",
                "id": 61
            }
        ]
    },
    "error": false
}
```

`{baseurl}/hall_planning/standrequest/industrie/{branchen_id}`

With this endpoint you can get the parent and child industries of an industry. It is meant that the `main_industry_id` of the [booth wishes](#get-standwünsche) is used here. Here the `branchen_id` is mandatory.

### Response Codes

code | meaning
---|---
`200` | The request was successful.
`406` | The request was not successful because probably the data was sent to the API incorrectly.


## [GET] Standstatus

```curl
curl --location '{baseurl}/hall_planning/standstatus/63' \
--header 'x-API-Key: {API-Key}'
```

> The above command returns JSON structured like this:

```json
{
    "data": [
        {
            "booth_number": "63",
            "status": "offen"
        }
    ],
    "error": false
}
```

`{baseurl}/hall_planning/standstatus`
`{baseurl}/hall_planning/standstatus/{booth_number}`

The `booth_number` is optional as for the [booth_wishes](#get_booth_wishes). If none is given, the booth status of each booth is returned.

Usually there is only one booth for each booth number. But it can also happen that there are several.

Ein Status kann folgendes bedeuten:

Status | Bedeutung
---|---
`offen` | A stand object is not assigned to an exhibitor and there is no associated stand proposal for the stand object that is set to open.
`zugestimmt` | A stand object is assigned to an exhibitor.
`abgelehnt` | A stand object is not assigned to an exhibitor. There is no associated stand proposal for the stand object that is set to open or agreed, but there is at least one stand proposal that is set to rejected.

### Response Codes

code | meaning
---|---
`200` | The request was successful.
`406` | The request was not successful because probably the data was sent to the API incorrectly.


## [POST] Neuer Standvorschlag

```curl
curl --location '{baseurl}/hall_planning/standproposal?debug=null' \
--header 'x-API-Key: {API-Key}' \
--data '{
    "booth_width": 10,
    "booth_depth": 2,
    "booth_number": "A4",
    "booth_type": 1,
    "stand_request_id": 1,
    "exhibitor_fair_id": 3,
    "hall_id": 1,
    "description": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum."
}'
```

> The above command returns JSON structured like this:

```json
{
    "data": {
        "stand_proposal_id": 13,
        "internal_args": {
            "standwunsch": 1,
            "ausstellerid": 1,
            "beschreibung": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum.",
            "standtyp": 1,
            "standnummer": "A4",
            "standgroesse": 20,
            "standzuordnung": 1,
            "standlaenge": 2,
            "standbreite": 10,
            "user": 1337,
            "messeid": 2
        }
    },
    "error": false
}
``` 

`{baseurl}/hall_planning/standproposal?debug`

This endpoint creates a new stand proposal. One must specify:

- the stand dimensions,
- the stand number,
- the stand type,
- other metadata
- and the exhibitor to whom the stand should be proposed.

In order for the associated stand request to disappear from the list of stand requests with the transfer of the scheduled stand, a getStandRequests would have to be executed again after the successful transfer of the stand to profairs.

### The proposal was not made

It is possible that no stand proposal is made. In this case the response code `200` will be returned. This happens under the following conditions:

- There is already a stand with the identical stand number.

### Request Body 

key | required | type
---|---|---
`booth_width` | [x] | numeric
`booth_depth` | [x] | numeric
`booth_number` | [x] | string
`booth_type` | [x] | integer
`stand_request_id` | [x] | integer
`exhibitor_fair_id` | [x] | integer
`hall_id` | [ ] | integer
`description` | [ ] | string

Whether the values have the correct data type should be validated, with a meaningful error message.

### Query Params

If `debug` was set as a parameter, this endpoint additionally returns the arguments as they were used internally.

### Response Codes

code | meaning
---|---
`201` | The request was successful and a stand proposal was made.
`200` | The request was successful, but for [some reason](#the-proposal-was-not-made) no stand proposal was made.
`406` | The request was not successful because probably the data was sent to the API incorrectly.
