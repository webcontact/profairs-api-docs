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
            "booth_width": 10,
            "placement_request": {
                "test": "Some key value pair in the database regarding the placement."
            },
            "employee": {
                "id": 44,
                "first_name": "Hazel",
                "last_name": "Burger"
            },
            "booth_depth": 2,
            "status": "replanning",
            "stand_request": {
                "test": "Some key value pair in the database.",
                "A4444 (declined)": "This looks nice, but it is not mine.",
                "A2 (declined)": "I don't want any other proposals."
            },
            "booth_type": 3,
            "id": 3,
            "main_industry": {
                "name": "Andere Komponenten für Antriebstechnik",
                "id": 206
            },
            "exhibitor": {
                "exhibitor_id": 1,
                "fair_id": 5,
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

This data must be [sent back to profairs](#make-stand-proposal) in addition to the planned stand:

1. `stand_request_id`, to which the planned stand refers to
2. `exhibitor_id`
2. `fair_id`

#### status

The `status` is an enum, which can have the following values:

status | meaning
---|---
`initial_planning` | The stand request is assigned to at least one stand proposal that is not locked.
`replanning` | The stand request is not assigned to a stand proposal that is not locked.

In summary, if the status is set to `initial_planning`, the person planning has most likely never touched this standrequest. If the status is set to `replanning`, the person planning probably already touched this request, but still has to do something.  

#### stand_request / placement_request

When planning the fair, you might encounter things, that cant be processed automatically. One example could be the reason, the exhibitor rejected your stand proposal. This kind of information is returned as key value pair in the keys `placement_request` and `stand_request`.

It is recommended to show these key value pairs in your interface as e.g. additional information. This enables the person planning everything to have all the information they need.

#### employee

If an employee in your company is assigned to the returned exhibitor, their `first_name`, `last_name` and `id` will be returned additionally to the exhibitor data.
If no employee is assigned to the exhibitor, the field `employee` will not be returned.

```json
"employee": {
    "id": 44,
    "first_name": "Hazel",
    "last_name": "Burger"
},
```

### Response Codes

| code  | meaning                                                                                   |
|-------|-------------------------------------------------------------------------------------------|
| `200` | The request was successful.                                                               |
| `406` | The request was not successful because probably the data was sent to the API incorrectly. |

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

Some of the values can be fetched from [this endpoint](#get-standrequest).

In order for the associated stand request to disappear from the list of stand requests with the transfer of the scheduled stand, a getStandRequests would have to be executed again after the successful transfer of the stand to profairs.

### The proposal was not made

It is possible that no stand proposal is made. In this case the response code `200` will be returned. This happens under the following conditions:

- There is already a stand with the identical stand number.
- If the hall id was given, the stand has to exist in the same hall.

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

## Upload Floorplan

```curl
curl --location '{baseurl}/hall_planning/floorplan' -X POST \
--header 'x-API-Key: {API-Key}' \
--data '{
    "fairid": 1,
    "b64svg": fkhdfh73hf92fajkdfhaslkhfKLHHUIhjhh9h9,
}'
```


> The above command returns JSON structured like this:

```json
{
  "data": {
    "url": "https://sandbox.profairs.de/shared/sandbox/floorplans/svg/1.svg"
  },
  "error": false,
  "error_message": {}
}
```

### HTTP request

`POST {baseurl}/hall_planning/floorplan/`

### Request Body

key | required | type | default
---|---|---|---
`fairid` | [x] | integer
`b64svg` | [x] | string
`dryRun` | [ ] | boolean | `false`
`minimize` | [ ] | boolean | `true`

### Description

The `b64svg` is the base64 encoded svg file. The svg file should be a floorplan of the fair. The individual booths can be either a [group](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/g) or a [path](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/path). If the booth is a group, it will be automatically converted to a path, to ensure the hover and fill functionality works. This will result in a potential loss of detail (e.g. multi colored fields inside the group of the booth). A workaround would be to overlay the structure that should be converted, with another group that is more detailed.

The booth should be marked with the booth number as an id. For this either use the custom attribute `cvjs:roomId` or `data-stand-id`. The booth number should be the same as the booth number in the database.

```svg
<?xml version="1.0" encoding="utf-8"?>
<svg width="920" height="750" viewBox="0 0 920 750">
      <g cvjs:roomId="A2498">
        <title>0000131</title>
        <line x1="290" y1="230" x2="340" y2="230" stroke="#ff0000" stroke-width="10.00mm" style="position:absolute; z-index:0.000000" />
        <line x1="340" y1="230" x2="340" y2="270" stroke="#ff0000" stroke-width="10.00mm" style="position:absolute; z-index:0.000000" />
        <line x1="340" y1="270" x2="290" y2="270" stroke="#ff0000" stroke-width="10.00mm" style="position:absolute; z-index:0.000000" />
        <line x1="290" y1="270" x2="290" y2="230" stroke="#ff0000" stroke-width="10.00mm" style="position:absolute; z-index:0.000000" />
      </g>
</svg>
```

> This would be converted to:
  
```svg
<?xml version="1.0" encoding="utf-8"?>
<svg width="920" height="750" viewBox="0 0 920 750">
  <path cvjs:area="20" cvjs:node="1" cvjs:roomId="A2498" stroke="red" stroke-width=".616" d="M472.826 375h81.522v65.217h-81.522V375" class="ZW cvjs_nodes cvjs_A2498" />
  <text x="474.457" y="376.63" stroke="none" dominant-baseline="baseline" font-family="Arial" font-size="13.043" style="position:absolute;z-index:0" transform="matrix(1 0 0 -1 0 753.26)">A2498</text>
</svg>
```

The things this endpoint does are as follows:

1. It sanitizes the svg file (for example removing all script tags).
2. It scales the svg to an appropriate size (the default is `1500px`).
3. It fixes the closes the paths if possible, and converts groups to paths (only the booth groups and paths like described above).
4. It uses [svgo](https://github.com/svg/svgo) to minimize and optimize the svg.

Additional small things that are done are:

- setting the `preserveAspectRatio` attribute to `xMidYMid meet`
- setting the title of the path of the stand to its id.

Important to keep in mind is, that the processing can break the svg. To check just go to the returned url and take a look if it is broken.
