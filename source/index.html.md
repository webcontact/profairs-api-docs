---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

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

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "x-api-key: {API-Key}"
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
## Get exhibitors

```shell
curl "{baseurl}/exhibitors/" \
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

`GET {baseurl}/exhibitors/`

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fair_id | Integer | false | | If set returns exhibitors from a specific fair.


## Get Exhibitor
```shell
curl "{baseurl}/exhibitors/{exhibitor_id}" \
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

`GET {baseurl}/exhibitors/{exhibitor_id}`

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitor_id | Integer | true | | defines the exhibitor.

## Create an Exhibitor
```shell
curl "{baseurl}/exhibitors/" \
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

`POST {baseurl}/exhibitors/`

### Parameters

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
curl "{baseurl}/exhibitors/{exhibitor_id}" \
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

`DELETE {baseurl}/exhibitors/{exhibitor_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitor_id | numeric | true | | ID of the exhibitor to be deleted
forum_sync | boolean | true | false | If the Forum Sync feature is used, this must be noted in the call
external | boolean | true | false | Decide whether to use the ProFairs ID or the External ID

## Update an Exhibitor

```shell
curl "{baseurl}/exhibitors/{exhibitor_id}" \
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

`PUT {baseurl}/exhibitors/{exhibitor_id}`

### Parameters

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

## Retreive contact persons

```shell
curl "{baseurl}/contact_persons/" \
  -H "x-api-key: {API-Key}" \
  -X GET \
```

### HTTP request

`GET {baseurl}/contact_persons/`

## Retreive contact person

```shell
curl "{baseurl}/contact_persons/{contact_person_id}" \
  -H "x-api-key: {API-Key}" \
  -X GET \
```

## Create contact person

```shell
curl "{baseurl}/contact_persons/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
salutation | string | true |  |
title | string | false |  |
job_title | string | false |  |
firstname | string | true |  |
lastname | string | true |  |
exhibitor_id | numeric | true |  |
telephone | string | false |  |
mobile | string | false |  |
email | string | true |  |
has_newsletter_approval | boolean | true |  false |
comment | string | false |  |
company | string | false |  |
street | string | false |  |
additional_address | string | false |  |
postalcode | string | false |  |
city | string | false |  |
country | string | false |  |
fair_type_id | numeric | false |  |

## Upload contact person image

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`POST {baseurl}/contactpersons/upload/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
datasource | string | true |  |
file | binary | true |  |
image_name | string | true |  |
type | string | true |  |
contact_person_id | numeric | true |  |

## Update contact person

### HTTP request

`PUT {baseurl}/contactpersons/{contact_person_id}/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
datasource | string | true |  |
salutation | string | true |  |
title | string | false |  |
job_title | string | false |  |
firstname | string | true |  |
lastname | string | true |  |
exhibitor_id |numeric | true |  |
telephone | string | false |  |
mobile | string | false |  |
email | string | true |  |
has_newsletter_approval | boolean | true | false |
comment | string | false |  |
company | string | false |  |
street | string | false |  |
additional_address | string | false |  |
postalcode |string | false |  |
city | string | false |  |
country | string | false |  |
fair_type_id | numeric | false |  |

## Delete contact person

### HTTP request

`DELETE {baseurl}/contactperson/{contact_person_id}/`


### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
contact_person_id | numeric | true |  |
datasource | string | true |  |
forum_sync | boolean |  false | false |  |

# Fairs

## Get fairs

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`GET {baseurl}/fairs/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
datasource | string | true |  |
logo | boolean | true | false  |
motion | boolean | true | false  |
order | boolean | true | false  |

## Get fair

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`GET {baseurl}/fairs/{fair_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fair_id | numeric | true |  |
datasource | string | true |  |
logo | boolean | true | false  |
motion | boolean | true | false  |

## Create fair

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`POST {baseurl}/fairs/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
datasource | string | true |  |
fair | string | false |  |
fair_type_id | numeric | false |  |
location | string | false |  |
shop_no_cancellations | string | false |  |
shop_closes | string | false |  |
css | string | true | profairs-default  |
url_logout | string | false |  |
price_per_voucher | string | false |  |
date_from | string | false |  |
date_to | string | false |  |

## Upload file

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`POST {baseurl}/fairs/upload/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
datasource | string | true |  |
type | string | true |  |
file | binary | true |  |
fair_id | numeric | true |  |

## Update fair

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`PUT {baseurl}/fairs/{fair_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fair_id | string | true | |
datasource | string | true | |
fair | string | false | |
fair_type_id | numeric | false | |
location | string | false | |
shop_no_cancellations | string | false | |
shop_closes | string | false | |
css | string | true | profairs-default |
url_logout | string | false | |
price_per_voucher | string | false | |
date_from | string | false | |
date_to | string | false | |

## Delete fair

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`DELETE {baseurl}/fairs/{fair_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fair_id | numeric | true |


# Fair types

## Get fair types

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`GET {baseurl}/fairtypes/`

## Get fair type

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`GET {baseurl}/fairtypes/{fair_type_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fair_type_id | numeric | true |

## Create new fair type

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
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

## Update fair type

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`POST {baseurl}/fairtypes/{fair_type_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fair_type_id | numeric | true | |
datasource | string | true | |
fair_type | string | false | |
email | string | false | |
telephone | string | false | |
redirect | string | false | https:// |
redirect_error | string | false | https:// |
contact_person_id | numeric | false | |

## Delete fair type

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`DELETE {baseurl}/fairtypes/{fair_type_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fair_type_id | numeric | true | |

# Booths

## Get booths

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`GET {baseurl}/booths/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fair_id | numeric | false |

## Get booth

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`GET {baseurl}/booths/{booth_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
booth_id | numeric | true |

## Create booth

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`POST {baseurl}/booths/`

### Parameters

<!-- TODO: SET PARAMS -->
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------

## Update booth

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`PUT {baseurl}/booths/{booth_id}`
### Parameters

<!-- TODO: SET PARAMS -->
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------

## Delete booth

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

`DELETE {baseurl}/booths/{booth_id}`

### HTTP request

`PUT {baseurl}/booths/{booth_id}`
### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
booth_id | numeric | true | |
forum_sync | boolean | false | false |

# Visitors

## Get visitors

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`GET {baseurl}/visitors/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairid | numeric | false | |

## Get visitor

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`GET {baseurl}/visitors/{visitor_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
visitor_id | numeric | true | |
datasource | string | true | |
fair_id | numeric | false | |
external | boolean | false | false |

## Create visitor

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`POST {baseurl}/visitors/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
datasource | string | false | |
external_id | string | false | |
code_id | numeric | false | |
company | string | false |  |
title | string | false |  |
salutation | string | false |  |
firstname | string | false |  |
lastname | string | false |  |
street | string | false |  |
postalcode | string | false |  |
city | string | false |  |
country | string | false | Deutschland |
telephone | string | false |  |
mobil | string | false |  |
latitude | string | false |  |
longitude | string | false |  |
email | string | false |  |
newsletter | boolean | false | false |

## Update visitor

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`PUT {baseurl}/visitors/{visitor_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
external | boolean | true | false |
datasource | string | true | |
code_id | numeric | true | |
company | string | false |  |
title | string | false |  |
salutation | string | false |  |
firstname | string | false |  |
lastname | string | false |  |
street | string | false |  |
postalcode | string | false |  |
city | string | false |  |
country | string | false | Deutschland |
telephone | string | false |  |
mobil | string | false |  |
latitude | string | false |  |
longitude | string | false |  |
email | string | false |  |
newsletter | boolean | false | false |

## Delete visitor

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`DELETE {baseurl}/visitors/{visitor_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
visitor_id | numeric | true | |
datasource | string | true | |
external | boolean | true | false |

# Industries

## Get industries

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`GET {baseurl}/industries/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------

## Get industrie

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`GET {baseurl}/industries/{industrie_id}`

### Parameters

<!-- TODO: SET PARAMS -->
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------

## Create industrie

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`POST {baseurl}/industries/`

### Parameters

<!-- TODO: SET PARAMS -->
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------

## Update industrie

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`PUT {baseurl}/industries/{industrie_id}`

### Parameters

<!-- TODO: SET PARAMS -->
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------

## Delete industrie

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`DELETE {baseurl}/industries/{industrie_id}`

### Parameters

<!-- TODO: SET PARAMS -->
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------

# Publications

## Get online medias

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`GET {baseurl}/publications/online/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fair_id | numeric | true | |

## Get online media

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`GET {baseurl}/publications/online/{exhibitor_fair_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitor_fair_id | numeric | true | |

## Create online media

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`POST {baseurl}/publications/online/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitor_fair_id | numeric | true | |
language | string | true | |
description | string | false | |
company_description | string | false | |
logo | binary | false | |
logo_name | string | false | |
logo_mimetype | string | false | |
logo_preview | binary | false | |
logo_mimetype | string | false | |
video_url | string | false | |
contact_person_id | numeric | false | |

#  Shop items

## Get items

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`GET {baseurl}/shop/items/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
datasource | string | true | |
category_id | numeric | false | |
itemnr | string | false | |
language | string | false | de_DE |
item_id | numeric | false | |
fair_id | numeric | false | |
end_date | string | false | |
show_locked | boolean | false | true |
show_coupon | boolean | false | |
show_catchall | boolean | false | |
show_special_coupon | boolean | false | |
user_role_admin | boolean | false | |
user_roles | string | false | |
exhibitor_types | string | false | |

## Get item

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`GET {baseurl}/shop/items/{item_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
item_id | string | true | |
datasource | string | false | |
category_id | numeric | true | |
itemnr | string | false | |
language | string | false | |
fair_id | numeric | false | |
end_date | string | false | |
show_locked | boolean | false | true |
show_coupon | boolean | false | |
show_catchall | boolean | false | |
show_special_coupon | boolean | false | |
user_role_admin | boolean | false | |
user_roles | string | false | |
exhibitor_types | string | false | |

## Create item

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`POST {baseurl}/shop/items/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
datasource | string | true | |
type_id | numeric | false | |
category_id | numeric | false | |
itemnr | string | false | |
booth_specific | boolean | true | false |
comment | string | false | |
sort | string | false | |
lock | boolean | true | false |
end_date | string | false | |
item_units | string | false | |
unit_of_measurement | string | false | |
item_title | string | false | |
upload | boolean | true | false |
recommended | boolean | true | false |
languages | any | true | false |
crossselling | string | false | |
dependence | string | false | |
exhibitor_types | string | false | |

## Update item

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`PUT {baseurl}/shop/items/{item_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
item_id | numeric | true | |
datasource | string | true | |
type_id | numeric | false | |
category_id | numeric | false | |
itemnr | string | false | |
booth_specific | boolean | true | false |
comment | string | false | |
sort | string | false | |
lock | boolean | true | false |
end_date | string | false | |
item_units | string | false | |
unit_of_measurement | string | false | |
item_title | string | false | |
upload | boolean | true | false |
recommended | boolean | true | false |
languages | any | true | false |
crossselling | string | false | |
dependence | string | false | |
exhibitor_types | string | false | |

## Upload item file

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`POST {baseurl}/shop/items/upload/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
file | binary | true | |
file_name | string | true | |
file_title | string | true | |
item_id | numeric | true | |
language | string | true | |
type | string | true | |

## Delete item

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`DELETE {baseurl}/shop/items/{item_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
item_id | numeric | true | |

# Shop categories

## Get categories

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`GET {baseurl}/shop/categories/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
datasource | string | true | |
language | string | false | de_DE |
fair_id | numeric | false | |
show_disabled | boolean | false | false |
hide_coupon | boolean | false | true |

## Get categorie

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`GET {baseurl}/shop/categories/{categorie_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
category_id | string | true | |
datasource | string | true | |
language | string | false | |
fair_id | numeric | false | |

## Create categroie

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`POST {baseurl}/shop/categories/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
datasource | string | true | |
parent_id | numeric | false | 0  |
contact_id | numeric | false | |
permissions_group_id | numeric | false | |
fair_id | numeric | false | |
show_coupons_link | boolean | false | false  |
order | numeric | false | |
lock | boolean | false | false  |
languages | string | false | |
auth_user | numeric | true | 666  |

## Update categorie

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`PUT {baseurl}/shop/categories/{categorie_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
category_id | numeric | false | |
datasource | string | false | |
parent_id | numeric | false | 0 |
contact_id | numeric | false | |
permissions_group_id | numeric | false | |
fair_id | numeric | false | |
show_coupons_link | boolean | false | false |
order | numeric | false | |
lock | boolean | false | false |
languages | string | false | |
auth_user | numeric | false | 666 |

## Delete categorie

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`DELETE {baseurl}/shop/categories/{categorie_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
category_id | numeric | true | |

# Shop variants

## Get variants

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`GET {baseurl}/shop/variants/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
datasource | string | false | |
item_id | numeric | false | |
locked | boolean | false | false |
ordered_variants | boolean | false | false |

## Get variant

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`GET {baseurl}/shop/variants/{variant_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
variants_id | numeric | true | |
datasource | string | true | |
locked | boolean | false | false |
ordered_variants | boolean | false | false |

## Create variant

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`POST {baseurl}/shop/variants/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
datasource | string | true | |
item_id | numeric | true | |
number_of_pieces | numeric | true | |
price | numeric | true | |
lock | boolean | true | false |
languages | any | true | |

## Upload files

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`POST {baseurl}/shop/variants/upload/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
file | binary | true | |
file_name | string | true | |
file_title | string | true | |
variants_id | numeric | true | |
language | string | true | |

## Update variant

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`PUT {baseurl}/shop/variants/{variant_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
variant_id | numeric | true | |
datasource | string | true | |
item_id | numeric | true | |
number_of_pieces | numeric | true | |
price | numeric | true | |
lock | boolean | true | false |
languages | any | true | |

## Delete variant

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`DELETE {baseurl}/shop/variants/{variant_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
variant_id | numeric | true | |
