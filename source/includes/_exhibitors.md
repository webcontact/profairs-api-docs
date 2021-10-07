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

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorid | numeric | true | | defines the exhibitor.

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

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorid | numeric | true | | ID of the exhibitor to be deleted
forum_sync | boolean | true | false | If the Forum Sync feature is used, this must be noted in the call
external | boolean | true | false | Decide whether to use the ProFairs ID or the External ID

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

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorid | numeric | true | | ID from the Exhibitor
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
