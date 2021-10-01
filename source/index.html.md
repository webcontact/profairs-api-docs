---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='mailto:kevin@webcontact'>Contact us for a developer key</a>
  - <a href='https://www.profairs.de'>Powered by profairs</a>

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the profairs API
---

# Introduction

Welcome to the profairs API! You can use our API to access profairs API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/slatedocs/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentication

> To authorize, use this code:

```ruby
require 'profairs'

api = profairs::APIClient.authorize!('meowmeowmeow')
```

```python
import profairs

api = profairs.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "x-api-key: {API-Key}"
```

```javascript
const profairs = require('profairs');

let api = profairs.authorize('meowmeowmeow');
```

> Make sure to replace `{API-Key}` with your API key.

profairs uses API keys to allow access to the API. You can register a new profairs API key at our [developer portal](http://example.com/developers).

profairs expects for the API key to be included in all API requests to the server in a header that looks like the following:

`x-api-key: {API-Key}`

<aside class="notice">
You must replace <code>{API-Key}</code> with your personal API key.
</aside>

<!-- # Kittens

## Get All Kittens

```ruby
require 'profairs'

api = profairs::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import profairs

api = profairs.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const profairs = require('profairs');

let api = profairs.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'profairs'

api = profairs::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import profairs

api = profairs.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const profairs = require('profairs');

let api = profairs.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'profairs'

api = profairs::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import profairs

api = profairs.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -X DELETE \
  -H "Authorization: meowmeowmeow"
```

```javascript
const profairs = require('profairs');

let api = profairs.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete -->

# Exhibitors
## Get All Exhibitors
```shell
curl "http://profairs-api.tom.webcontact.de/rest/profairs-api/exhibitors/" \
  -H "x-api-key: {API-Key}" \
  -X GET \
```

> The above command returns JSON structured like this:

```json
{
    "exhibitors": [
        {
            "postalcode": "L24 6SH",
            "telephone": "01708-724957",
            "customer_number": "",
            "address_verified": false,
            "lock": false,
            "remarks": "",
            "street": "4 Sherwood St",
            "email": "rebbeca_rubinstein@hotmail.com",
            "vat_identification_number": "",
            "company": "Cullen, Jack J Esq",
            "order_title": "Cullen, Jack J Esq",
            "city": "Speke-Garston Ward",
            "country": "",
            "external_id": "",
            "newsletter": false,
            "homepage": "http://www.cullenjackjesq.co.uk",
            "additional_address": "Merseyside",
            "id": 3202
        },
        {
            "postalcode": "OL15 0JP",
            "telephone": "01919-731224",
            "customer_number": "",
            "address_verified": false,
            "lock": false,
            "remarks": "",
            "street": "2 Seacombe St",
            "email": "keneth_stpierrie@hotmail.com",
            "vat_identification_number": "",
            "company": "Mueller Repro Blue Printg",
            "order_title": "Mueller Repro Blue Printg",
            "city": "Littleborough Lakeside Ward",
            "country": "",
            "external_id": "",
            "newsletter": false,
            "homepage": "http://www.muellerreproblueprintg.co.uk",
            "additional_address": "Greater Manchester",
            "id": 3216
        }
	]
}
```

This endpoint retrieves all exhibitors.

### HTTP Request

`GET http://profairs-api.tom.webcontact.de/rest/profairs-api/exhibitors/`

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fair_id | Integer | false | | If set returns exhibitors from a specific fair.


## Get a Specific Exhibitor
```shell
curl "http://profairs-api.tom.webcontact.de/rest/profairs-api/exhibitors/{exhibitor_id}" \
  -H "x-api-key: {API-Key}" \
  -X GET \
```

> The above command returns JSON structured like this:

```json
{
    "postalcode": "OL15 0JP",
    "telephone": "01919-731224",
    "customer_number": "",
    "address_verified": false,
    "lock": false,
    "remarks": "",
    "exhibitor_id": 3216,
    "street": "2 Seacombe St",
    "email": "keneth_stpierrie@hotmail.com",
    "vat_identification_number": "",
    "company": "Mueller Repro Blue Printg",
    "order_title": "Mueller Repro Blue Printg",
    "city": "Littleborough Lakeside Ward",
    "country": "",
    "external_id": "",
    "newsletter": false,
    "homepage": "http://www.muellerreproblueprintg.co.uk",
    "error": "false",
    "additional_address": "Greater Manchester"
}
```
This endpoint retrieves a specific exhibitor.

### HTTP Request

`GET http://profairs-api.tom.webcontact.de/rest/profairs-api/exhibitors/{exhibitor_id}`

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitor_id | Integer | true | | defines the exhibitor.

## Create an Exhibitor
```shell
curl "http://profairs-api.tom.webcontact.de/rest/profairs-api/exhibitors/" \
  -H "x-api-key: {API-Key}" \
  -H "Content-Type: application/json" \
  -X POST \
  -d '{
	"company": "company",
	"sorttitle": "sorttitle",
	"street": "street",
	"postalcode": "postalcode",
	"city": "city",
	"country": "country",
	"additional_address": "additional_address",
	"latitude": "latitude",
	"longitude": "longitude",
	"telephone": "telephone",
	"email": "email",
	"homepage": "homepage",
	"customer_number": "customer_number",
	"vat_identification_number": "vat_identification_number",
	"remarks": "remarks",
	"username": "username",
	"password": "password",
	"address_verified": false,
    "lock": true,
    "newsletter": false
}'
```


> The above command returns JSON structured like this:

```json
{
    "error": false,
	"exhibitor_id": 1337
}
```

This endpoint creates an exhibitor.

### HTTP Request

`POST http://profairs-api.tom.webcontact.de/rest/profairs-api/exhibitors/`

### Form Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
external_id | string | false | | ID from a external source (for Mapping)
company | string | false | | Name of the Company
sorttitle | string | false | | Sorttitle for ProFairs
street | string | false | | Street of the Company
postalcode | string | false | | Postalcode
city | string | false | | City
additional_address | string | | false | Additional Adress
country | string | false | | Country
latitude | string | false | | Latitude
longitude | string | false | | Longitude
telephone | string | false | | Telephone
email | string | false | | Email
homepage | string | false | | Homepage
customer_number | string | false | | Customer number
vat_identification_number | string | false | | VAT Identification Number
remarks | string | false | | Comments
username | string | false | | Username for the Exhibitor-Area
password | string | false | | Password for the Exhibitor-Area
address_verified | boolean | false | | Address verified
lock | boolean | false | | Locks the created Exhibitor
newsletter | boolean | false | | Can the Exhibitor recive Newsletter

## Delete an Exhibitor
```shell
curl "http://profairs-api.tom.webcontact.de/rest/profairs-api/exhibitors/{exhibitor_id}" \
  -H "x-api-key: {API-Key}" \
  -X DELETE
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
	"exhibitor_id": 1337
}
```

This endpoint deletes an exhibitor.

### HTTP Request

`DELETE http://profairs-api.tom.webcontact.de/rest/profairs-api/exhibitors/{exhibitor_id}`

### Form Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitor_id | numeric | true | | ID of the exhibitor to be deleted
forum_sync | boolean | true | false | If the Forum Sync feature is used, this must be noted in the call
external | boolean | true | false | Decide whether to use the ProFairs ID or the External ID

## Update an Exhibitor
```shell
curl "http://profairs-api.tom.webcontact.de/rest/profairs-api/exhibitors/{exhibitor_id}" \
  -H "x-api-key: {API-Key}" \
  -H "Content-Type: application/json" \
  -X PUT \
  -d '{
	"company": "company123",
	"sorttitle": "sorttitle",
	"street": "street",
	"postalcode": "postalcode",
	"city": "city",
	"country": "country",
	"additional_address": "additional_address",
	"latitude": "latitude",
	"longitude": "longitude",
	"telephone": "telephone",
	"email": "email",
	"homepage": "homepage",
	"customer_number": "customer_number",
	"vat_identification_number": "vat_identification_number",
	"remarks": "remarks",
	"username": "username",
	"password": "password",
	"address_verified": false,
    "lock": true,
	"external": false,
    "newsletter": false
}'
```
> The above command returns JSON structured like this:

```json
{
    "error": false,
	"exhibitor_id": 1337
}
```

This endpoint updates an exhibitor.

### HTTP Request

`PUT http://profairs-api.tom.webcontact.de/rest/profairs-api/exhibitors/{exhibitor_id}`

### Form Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitor_id | integer | true | | ID from the Exhibitor
external_id | string | false | | ID from a external source (for Mapping)
company | string | false | | Name of the Company
sorttitle | string | false | | Sorttitle for ProFairs
street | string | false | | Street of the Company
postalcode | string | false | | Postalcode
city | string | false | | City
additional_address | string | | false | Additional Adress
country | string | false | | Country
latitude | string | false | | Latitude
longitude | string | false | | Longitude
telephone | string | false | | Telephone
email | string | false | | Email
homepage | string | false | | Homepage
customer_number | string | false | | Customer number
vat_identification_number | string | false | | VAT Identification Number
remarks | string | false | | Comments
username | string | false | | Username for the Exhibitor-Area
password | string | false | | Password for the Exhibitor-Area
address_verified | boolean | false | | Address verified
lock | boolean | false | | Locks the created Exhibitor
newsletter | boolean | false | | Can the Exhibitor recive Newsletter

# Contact persons

# Fairs

# Booths

# Visitors

# Industries

# Fair types

# Publications
# Shop

## Items

## Categories
## Variants
