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
exhibitorid | numeric | false | |
exhibitorfairid | numeric | false | |
mainexhibitorid | numeric | false | |
industryid | numeric | false | |
industryids | list | false | |
shop_categorie | numeric | false | |
interestcode | String | false | |
locked | Boolean | true | false |
external_id | String | false | |
exhibitortypeid | numeric | false | |
getBooths | Boolean | true | false | Adds booths to the exhibitors. If set to true, fairid is required.
getContacts | Boolean | true | false | Adds contacts to the exhibitors.

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
    "newsletter": false,
    "external_id": "EID_123"
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
external_id | String | false | |

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
    "external_id": "EID_123",
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
external_id | String | false | |

## Generate access data

```shell
curl --location --request GET '{baseurl}/exhibitors/generate-access-data/' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false
}
```

This endpoint generates username and password for all exhibitors from a specific fair.

### HTTP Request

`GET {baseurl}/exhibitors/generate-access-data/`

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairid | numeric | true | |

## Generate catchall code

```shell
curl --location --request GET '{baseurl}/exhibitors/generate-catchall-code/' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false
}
```

### HTTP Request

`GET {baseurl}/exhibitors/generate-catchall-code/`

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairid | numeric | true | |
code | String | false | |
exhibitorid | String | false | | required when code is set

## Generate interest code

```shell
curl --location --request GET '{baseurl}/exhibitors/generate-access-data/' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false
}
```

### HTTP Request

`POST {baseurl}/exhibitors/generate-access-data/`

## Assign label to exhibitor

```shell
curl --location '{baseurl}/exhibitors/assign-label' \
--header 'X-API-KEY: {API-Key}' \
--header 'Content-Type: application/json' \
--data '{
    "exhibitorid": {exhibitorid},
    "labelid": {labelid}
}'
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "labelid": 13,
    "exhibitorid": 1
}
```

### HTTP Request

`POST {baseurl}/exhibitors/assign-label/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
labelid | numeric | true |
exhibitorid | numeric | true |

## Set exhibitor-type assignment

```shell
curl --location '{baseurl}/exhibitors/exhibitor-type-assignment/' \
--header 'X-API-KEY: {API-Key}' \
--header 'Content-Type: application/json' \
--data '{
    "exhibitorfairid": {exhibitorfairid},
    "exhibitortypeid": {exhibitortypeid}
}'
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "exhibitor_type_assignment": {
        "exhibitortypeid": 5,
        "exhibitorfairid": 1541
    }
}
```

### HTTP Request

`POST {baseurl}/exhibitors/exhibitor-type-assignment/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitortypeid | numeric | true |
exhibitorfairid | numeric | true |

## Get exhibitor-type assignment

```shell
curl --location '{baseurl}/exhibitors/exhibitor-type-assignment/' \
--header 'X-API-KEY: {API-Key}' \
--header 'Content-Type: application/json' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "exhibitortypes": {
        "exhibitortypeids": "1,2,3",
        "exhibitorfairid": "1234"
    }
}
```

### HTTP Request

`GET {baseurl}/exhibitors/exhibitor-type-assignment/`

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorfairid | numeric | true |

## Get exhibitor-types

```shell
curl --location '{baseurl}/exhibitors/exhibitor-type' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "exhibitortypes": {
        "exhibitortypeids": "1,2,3",
        "exhibitorfairid": "1234"
    }
}
```

### HTTP Request

`GET {baseurl}/exhibitors/exhibitor-type/`

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairtypeid | numeric | false |
exhibitortypeid | numeric | false |



## Get exhibitor-address-verification

```shell
curl --location '{baseurl}/exhibitors/{exhibitorid}/adress-verification/' \
--header 'X-API-KEY: {API-Key}' \
```
> The above command returns JSON structured like this:

```json
{
    "error": false,
    "addressverifications": [
        {
            "date": "April, 20 2023 11:58:00 +0200",
            "fairid": 1,
            "exhibitorid": 1
        }
    ]
}
```

### HTTP Request

`GET {baseurl}/exhibitors/{exhibitorid}/adress-verification/`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorid | numeric | true | |

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairid | numeric | true | |


## Get assigned brands

```shell
curl --location --request GET '{baseurl}/exhibitors/{exhibitorid}/brands' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "brands": [
    {
      "language": "de-DE",
      "name": "John Deer",
      "id": 13
    },
    {
      "language": "de-DE",
      "name": "Test Marke",
      "id": 19
    }
  ]
}
```

### HTTP request

`GET {baseurl}/exhibitors/{exhibitorid}/brands`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorid | numeric | true |


## Assign brand

```shell
curl --location --request POST '{baseurl}/exhibitors/{exhibitorid}/brands' \
--header 'X-API-KEY: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
  "brand_id": 19
}'
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "id": 144,
  "error_message": {}
}
```

### HTTP request

`POST {baseurl}/exhibitors/{exhibitorid}/brands`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorid | numeric | true |

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
brand_id | numeric | true | | |


## Get assigned product groups

```shell
curl --location --request GET '{baseurl}/exhibitors/{exhibitorid}/product-groups' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "product-groups": [
    [
      {
        "language": "de_DE",
        "name": "Nutzholz",
        "id": 160
      },
      {
        "language": "en_GB",
        "name": "Timber",
        "id": 160
      }
    ],
    [
      {
        "language": "de_DE",
        "name": "Agrarprodukte",
        "id": 156
      },
      {
        "language": "en_GB",
        "name": "Agricultural products",
        "id": 156
      }
    ]
  ]
}
```
### HTTP request

`GET {baseurl}/exhibitors/{exhibitorid}/product-groups`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorid | numeric | true |

## Assign product group

```shell
curl --location --request POST '{baseurl}/exhibitors/{exhibitorid}/product-groups' \
--header 'X-API-KEY: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
  "product_group_id": 156
}'
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "id": 14,
  "error_message": {}
}
```

### HTTP request

`POST {baseurl}/exhibitors/{exhibitorid}/product-groups`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorid | numeric | true |

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
product_group_id | numeric | true | | |


## Get assigned solution list entries

```shell
curl --location --request GET '{baseurl}/exhibitors/{exhibitorid}/solution-list-entries' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
  "solution-list": [
    [
      {
        "language": "de_DE",
        "name": "Klimaneutral",
        "id": 158
      },
      {
        "language": "en_GB",
        "name": "climate neutral",
        "id": 158
      }
    ]
  ],
  "error": false,
  "error_message": {}
}
```

### HTTP request

`GET {baseurl}/exhibitors/{exhibitorid}/solution-list-entries`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorid | numeric | true |

## Assign solution list entry

```shell
curl --location --request POST '{baseurl}/exhibitors/{exhibitorid}/solution-list-entries' \
--header 'X-API-KEY: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
  "solution_list_id": 19
}'
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "id": 14,
  "error_message": {}
}
```

### HTTP request

`POST {baseurl}/exhibitors/{exhibitorid}/product-groups`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorid | numeric | true |

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
solution_list_id | numeric | true | | |

## Get base data

```shell
curl --location --request GET '{baseurl}/exhibitors/{exhibitorid}/{fairid}/base-data' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "base-data": {
    "strasse": "Waldblumenstraße 48",
    "longitute": "8.5172466",
    "telefax": "",
    "plz": "75334",
    "latitute": "48.8523418",
    "adresszusatz": "",
    "ustidnr": "",
    "standbezeichnung": "",
    "firma": "web://contact GmbH",
    "telefon": "+49 7082 948344",
    "ort": "Straubenhardt",
    "kurztitel": "web://contact GmbH",
    "land": "DE",
    "homepage": "",
    "debitorennummer": "",
    "email": "email@test.local"
  }
}
```

### HTTP request

`GET {baseurl}/exhibitors/{exhibitorid}/{fairid}/base-data`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorid | numeric | true |
fairid | numeric | true |

## Get profile

```shell
curl --location --request GET '{baseurl}/exhibitors/{exhibitorfairid}/profile' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "profile": {
    "ueber_uns": "Lorem ipsim ...",
    "anzahl_mitarbeiter": "100",
    "praxis": "Lorem ipsim ...",
    "anzeige_typ": "",
    "text": "test",
    "social_media_4": "",
    "bewerbungsverfahren": "Lorem ipsim ...",
    "einstiegsmoeglichkeit": "Lorem ipsim ...",
    "social_media_2": "",
    "social_media_5": "",
    "hauptsitz": "Stuttgart",
    "qualifikationen": "Lorem ipsim ...",
    "unternehmensbeschreibung": "Lorem ipsum...",
    "sprache": "de_DE",
    "logo_mimetype": "image/png",
    "videourl": "https://url_to_the_video",
    "logo": "aHR0cHM6Ly91cmxfdG9fdGhlX2xvZ28ucG5n",
    "social_media_1": "",
    "postanschrift": "Musterstraße 1",
    "logo_name": "logo.png",
    "consultation": 0,
    "logo_vorschau": "bG9nb19wcmV2aWV3LnBuZw==",
    "standorte": "München, Köln, Berlin",
    "profil": "Lorem ipsim ...",
    "social_media_3": ""
  }
}
```

### HTTP request

`GET {baseurl}/exhibitors/{exhibitorfairid}/profile`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorfairid | numeric | true |

## Set profile

```shell
curl --location --request POST '{baseurl}/exhibitors/{exhibitorfairid}/profile' \
--header 'X-API-KEY: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
  "sprache": "de_DE",
  "text": "test",
  "logo": "https://url_to_the_logo.png",
  "unternehmensbeschreibung": "Lorem ipsum...",
  "logo_name": "logo.png",
  "logo_vorschau": "logo_preview.png",
  "logo_mimetype": "image/png",
  "videourl": "https://url_to_the_video",
  "ueber_uns": "Lorem ipsim ...",
  "bewerbungsverfahren": "Lorem ipsim ...",
  "einstiegsmoeglichkeit": "Lorem ipsim ...",
  "praxis": "Lorem ipsim ...",
  "profil": "Lorem ipsim ...",
  "qualifikationen": "Lorem ipsim ...",
  "anzeige_typ": "",
  "postanschrift": "Musterstraße 1",
  "consultation": "0",
  "hauptsitz": "Stuttgart",
  "standorte": "München, Köln, Berlin",
  "anzahl_mitarbeiter": "100",
  "social_media_1": "",
  "social_media_2": "",
  "social_media_3": "",
  "social_media_4": "",
  "social_media_5": ""
}'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "id": 14,
  "error_message": {}
}
```

### HTTP request

`POST {baseurl}/exhibitors/{exhibitorfairid}/profile`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorfairid | numeric | true |

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
sprache | string | true | | |
text | string | false | | |
logo | string | false | | |
unternehmensbeschreibung | string | false | | |
logo_name | string | false | | |
logo_vorschau | string | false | | |
logo_mimetype | string | false | | |
videourl | string | false | | |
ueber_uns | string | false | | |
bewerbungsverfahren | string | false | | |
einstiegsmoeglichkeit | string | false | | |
praxis | string | false | | |
profil | string | false | | |
qualifikationen | string | false | | |
anzeige_typ | string | false | | |
postanschrift | string | false | | |
consultation | string | false | | |
hauptsitz | string | false | | |
standorte | string | false | | |
anzahl_mitarbeiter | string | false | | |
social_media_1 | string | false | | |
social_media_2 | string | false | | |
social_media_3 | string | false | | |
social_media_4 | string | false | | |
social_media_5 | string | false | | |
