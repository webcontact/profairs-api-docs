# Hall planning


## Missing values

If a value in the database is optional and missing for a record requested via the API, then the key of the value is simply not returned instead of being `null`. 


## Get standrequest

```curl
curl --location '{baseurl}/hall_planning/standrequest?exhibitor_id=1&fair_id=5' \
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
            "status": "umplanen",
            "booth_type": 3,
            "platzierungswunsch": "",
            "id": 3,
            "exhibitor": {
                "exhibitor_id": 1,
                "fair_id": 5,
                "main_industrie_id": 3,
                "name": "web://contact GmbH"
            }
        }
    ],
    "error": false,
    "warning": {},
    "error_message": {}
}
```

This endpoint returns the data of the stand requests.

### HTTP Request

`GET {baseurl}/hall_planning/standrequest`  

### Query Parameters

The `exhibitor_id` and `fair_id` are optional parameters. If they are set, the endpoint returns all stand requests that are assigned to the respective exhibitor and fair. If they are not set, all stand requests will be returned.

Parameter |	Type | required | Default | Description
---|---|---|---|---
exhibitor_id | numeric | false | | If this is set, fair_id has to be set as well.
fair_id | numeric | false | | If this is set, exhibitor_id has to be set as well


### Description

This data must be sent back to profairs with the planned stand:

1. `standwunsch_id`, to which the planned stand refers to
2. `exhibitor_id`
2. `fair_id`

The status is an enum, which can have the following values:

status | meaning
---|---
`initial_planning` | The stand request is assigned to at least one stand proposal that is not locked.
`replanning` | The stand request is not assigned to a stand proposal that is not locked.

### Response Codes

code | meaning
---|---
`200` | The request was successful.
`406` | The request was not successful because probably the data was sent to the API incorrectly.


## Get industrie

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

With this endpoint you can get the parent and child industries of an industry. It is meant that the `main_industry_id` from the [stand requests](#get-standrequest) is used here. Here the `branchen_id` is mandatory.

### Response Codes

code | meaning
---|---
`200` | The request was successful.
`406` | The request was not successful because probably the data was sent to the API incorrectly.


## Get standstatus

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

The `booth_number` is optional as for the [stand requests](#get-standrequest). If none is given, the booth status of each booth is returned.

Usually there is only one booth for each booth number. But it can also happen that there are several.

The status is an enum, which can have the following values:

status | meaning
---|---
`offen` | A stand object is not assigned to an exhibitor and there is no associated stand proposal for the stand object that is set to open.
`zugestimmt` | A stand object is assigned to an exhibitor.
`abgelehnt` | A stand object is not assigned to an exhibitor. There is no associated stand proposal for the stand object that is set to open or agreed, but there is at least one stand proposal that is set to rejected.

### Response Codes

code | meaning
---|---
`200` | The request was successful.
`406` | The request was not successful because probably the data was sent to the API incorrectly.


## Make stand proposal

```curl
curl --location '{baseurl}/hall_planning/standproposal?debug' \
--header 'x-API-Key: {API-Key}' \
--data '{
    "booth_width": 10,
    "booth_depth": 2,
    "booth_number": "A4",
    "booth_type": 1,
    "stand_request_id": 1,
    "exhibitor_id": 1,
    "fair_id": 2,
    "hall_id": 1,
    "status": "open",
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
            "status": "open",
            "standzuordnung": 1,
            "standlaenge": 2,
            "standbreite": 10,
            "user": 1337,
            "messeid": 2
        }
    },
    "error": false,
    "warning": {}
}
``` 

`{baseurl}/hall_planning/standproposal?debug`

This endpoint creates a new stand proposal. One must specify:

- the stand dimensions,
- the stand number,
- the stand type,
- other metadata
- the exhibitor to whom the stand should be proposed.
- and the fair to which the stand belongs to.

In order for the associated stand request to disappear from the list of stand requests with the transfer of the scheduled stand, a getStandRequests would have to be executed again after the successful transfer of the stand to profairs.

### The proposal was not made

It is possible that no stand proposal is made. In this case the response code `200` will be returned. This happens under the following conditions:

- There is already a stand with the identical stand number.

### Request Body 

key | required | type | default
---|---|---|---
`booth_width` | [x] | numeric
`booth_depth` | [x] | numeric
`booth_number` | [x] | string
`booth_type` | [x] | integer
`stand_request_id` | [x] | integer
`exhibitor_id` | [x] | integer
`fair_id` | [x] | integer
`hall_id` | [ ] | integer
`description` | [ ] | string
`status` | [ ] | enum('accepted', 'declined', 'open', 'archived') | `open`

Whether the values have the correct data type should be validated, with a meaningful error message.

### Query Params

#### debug

If `debug` was set as a parameter, this endpoint additionally returns the arguments as they were used internally.

The endpoint runs checks before making the proposal, if both `exhibitor_id` and `fair_id` exist in the system. If not no proposal will be made. However, if debug is set to `true`, the proposal will be made regardless, and the error messages from the checks will be warnings instead. 

### Response Codes

code | meaning
---|---
`201` | The request was successful and a stand proposal was made.
`200` | The request was successful, but for [some reason](#the-proposal-was-not-made) no stand proposal was made.
`406` | The request was not successful because probably the data was sent to the API incorrectly.
