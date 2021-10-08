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
fairid | numeric | false | | If set returns exhibitors from a specific fair.


## Get Exhibitor
```shell
curl "{baseurl}/exhibitors/{exhibitorid}" \
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
    "exhibitorid": 3216,
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

`GET {baseurl}/exhibitors/{exhibitorid}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorid | numeric | true | |

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
	"exhibitorid": 1337
}
```

This endpoint creates an exhibitor.

### HTTP Request

`POST {baseurl}/exhibitors/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
external_id | string | false | |
company | string | true | |
sorttitle | string | true | |
street | string | true | |
postalcode | string | true | |
city | string | true | |
additional_address | string | false | |
country | string | false | |
latitude | string | false | |
longitude | string | false | |
telephone | string | true | |
email | string | true | |
homepage | string | false | |
customer_number | string | false | |
vat_identification_number | string | false | |
remarks | string | false | |
username | string | false | |
password | string | false | |
address_verified | boolean | false | |
lock | boolean | false | |
newsletter | boolean | false | |

## Delete an Exhibitor
```shell
curl "{baseurl}/exhibitors/{exhibitorid}" \
  -H "x-api-key: {API-Key}" \
  -X DELETE
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
	"exhibitorid": 1337
}
```

This endpoint deletes an exhibitor.

### HTTP Request

`DELETE {baseurl}/exhibitors/{exhibitorid}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorid | numeric | true | |
### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
forum_sync | boolean | true | false |
external | boolean | true | false |

## Update an Exhibitor

```shell
curl "{baseurl}/exhibitors/{exhibitorid}" \
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
	"exhibitorid": 1337
}
```

This endpoint updates an exhibitor.

### HTTP Request

`PUT {baseurl}/exhibitors/{exhibitorid}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorid | numeric | true | |
### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
external_id | string | false | |
company | string | false | |
sorttitle | string | false | |
street | string | false | |
postalcode | string | false | |
city | string | false | |
additional_address | string | | false |
country | string | false | |
latitude | string | false | |
longitude | string | false | |
telephone | string | false | |
email | string | false | |
homepage | string | false | |
customer_number | string | false | |
vat_identification_number | string | false | |
remarks | string | false | |
username | string | false | |
password | string | false | |
address_verified | boolean | false | |
lock | boolean | false | |
newsletter | boolean | false | |
