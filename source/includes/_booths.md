# Booths

## Get booths

```shell
curl --location --request GET '{baseurl}/booths/' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "booths": [
        {
          "articleid": 3,
          "change_user": 999,
          "create_user": 999,
          "change_date": "February, 03 2022 10:48:33",
          "boothwidth": "3.0",
          "exhibitors": [
            {
              "company": "Muster GmbH",
              "plz": "12345",
              "street": "Musterweg 45",
              "tel": "+49 1234 12 345 67",
              "main_exhibitor": "Muster GmbH",
              "website": "https://www.muster.local",
              "city": "Musterstadt",
              "exhibitorid": 123,
              "main_exhibitor_fair_id": 132,
              "exhibitorfairid": 1,
              "exhibitorbootid": 111,
              "short_company": "Muster GmbH",
              "mail": "mail@muster.local",
              "brands": [
                {
                  "language": "de_DE",
                  "groupId": 11,
                  "name": "Marke 1",
                  "id": 12
                },
                {
                  "language": "en_GB",
                  "groupId": 11,
                  "name": "Brand 1",
                  "id": 37
                }
              ],
              "branches": [
                {
                  "language": "de_DE",
                  "parentid": 2,
                  "groupid": 197,
                  "name": "Webentwicklung",
                  "id": 197,
                  "ordernumber": 0
                },
                {
                  "language": "en_GB",
                  "parentid": 2,
                  "groupid": 197,
                  "name": "Web Development",
                  "id": 198,
                  "ordernumber": 0
                }
              ],
              "keywords": [
                {
                  "language": "de_DE",
                  "groupId": 26,
                  "name": "Stichwort 3",
                  "id": 26
                },
                {
                  "language": "en_GB",
                  "groupId": 26,
                  "name": "Keyword 3",
                  "id": 27
                }
              ],
              "solution_lists": [
                {
                  "language": "de_DE",
                  "parentid": 169,
                  "groupid": 170,
                  "name": "Logistik",
                  "id": 170,
                  "ordernumber": 0
                },
                {
                  "language": "en_GB",
                  "parentid": 169,
                  "groupid": 170,
                  "name": "Logistics",
                  "id": 170,
                  "ordernumber": 0
                }
              ],
              "product_groups": [
                {
                  "language": "de_DE",
                  "parentid": 172,
                  "groupid": 195,
                  "name": "Malz",
                  "id": 195,
                  "ordernumber": 0
                },
                {
                  "language": "en_GB",
                  "parentid": 172,
                  "groupid": 195,
                  "name": "Malt",
                  "id": 195,
                  "ordernumber": 0
                }
              ],
              "contacts": [
                {
                  "postalcode": "12345",
                  "company": "Muster GmbH",
                  "telephone": "01234/567890",
                  "country": "Deutschland",
                  "job_title": "Senior Developer",
                  "salutation": "Herr",
                  "lastname": "Max",
                  "contactid": 2876,
                  "mobile": "",
                  "street": "Musterweg 1",
                  "additional_address": "",
                  "firstname": "Mustermann",
                  "comment": "",
                  "city": "Musterstadt",
                  "exhibitorid": 3415,
                  "title": "",
                  "newsletter": false,
                  "email": "max@mustermann.local"
                }
              ],
              "press_releases": [
                {
                  "keywords": [],
                  "language": "de_DE",
                  "text": "Lorem ipsum",
                  "introduction": "Lorem ipsum ...",
                  "solution_list_entries": [],
                  "image_subtitle": "",
                  "brands": [],
                  "groupid": 41,
                  "image_mimetype": "image/png",
                  "image_name": "https://url/to/image.png",
                  "branches": [],
                  "id": 317,
                  "product_group": [],
                  "link": "",
                  "exhibitor_fair_id": 1442,
                  "title": "Das ist ein Presseartikel"
                }
              ],
              "highlights": [
                {
                  "keywords": [],
                  "language": "de_DE",
                  "text": "Lorem ipsum ...",
                  "introduction": "Lorem ipsum",
                  "solution_list_entries": [],
                  "image_subtitle": "",
                  "brands": [],
                  "groupid": 40,
                  "image_mimetype": "image/png",
                  "image_name": "https://url/to/image.png",
                  "downloadlink": "https://url/to/download",
                  "branches": [],
                  "id": 316,
                  "product_group": [],
                  "link": "",
                  "exhibitor_fair_id": 1442,
                  "title": "Das ist ein Messehighlight",
                  "videolink": ""
                }
              ],
            }
          ],
          "boothnumber": "2-634",
          "boothtype": 0,
          "create_date": "February, 02 2022 10:44:02",
          "syncstatus": 0,
          "boothsize": "15.0",
          "fairid": 7,
          "boothid": 30,
          "boothdepth": "5.0",
          "address": "Testweg 1, 12345 Testen",
          "description": "Lorem ipsum ..."
        }
    ]
}
```

### HTTP request

`GET {baseurl}/booths/`

### Query Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| fairid         | numeric | false    |         |
| boothid         | numeric | false    |         |
| exhibitorboothid         | numeric | false    |         |


## Set booth

```shell
curl --location --request POST '{baseurl}/booths/' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "fairid": 7,
    "boothnumber": "A-1337",
    "boothwidth": 5,
    "boothdepth": 3,
    "boothsize": 15,
    "articleid": 1337,
    "boothtype": 1
}'
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "boothid": "1553"
}
```

### HTTP request

`POST {baseurl}/booths/`

### Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- |----------| ------- | ----------- |
| boothnumber         | String | true     |         |
| boothwidth         | numeric | true     |         |
| boothdepth         | numeric | true     |         |
| fairid         | numeric | true     |         |
| boothsize         | numeric | false    |         |
| articleid         | numeric | false    |         |
| boothtype         | numeric | false    |         |
| hall_id        | numeric | false    |         | 

### No Booth is created

If a booth matching the given parameters already exists, the endpoint will throw an error, but it will still return the booth id of the already existing booth.

A booth matching the given parameters is considered a duplicate in the following cases:

- There is already a booth with the identical booth number.
- If the hall id was given, the booth has to exist in the same hall.

## Delete booth

```shell
curl --location --request DELETE '{baseurl}/booths/{boothid}' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "boothid": "1551"
}
```

### HTTP request

`DELETE {baseurl}/booths/{boothid}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| boothid         | numeric | true    |         |


## Update booth

```shell
curl --location --request PUT '{baseurl}/booths/{boothid}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "fairid": 7,
    "boothnumber": "A-1338",
    "boothwidth": 5,
    "boothdepth": 3,
    "boothsize": 15,
    "articleid": 1337,
    "boothtype": 1,
    "hall_id": 15
}'
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "boothid": 1551
}
```

### HTTP request

`PUT {baseurl}/booths/{boothid}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| boothid         | numeric | true    |         |

### Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| boothnumber         | String | false    |         |
| boothwidth         | numeric | false    |         |
| boothdepth         | numeric | false    |         |
| fairid         | numeric | false    |         |
| boothsize         | numeric | false    |         |
| articleid         | numeric | false    |         |
| boothtype         | numeric | false    |         |
| hall_id         | numeric | false    |         | please user either hall_id or hall_namne
| hall_name         | name | false    |         | please user either hall_id or hall_namne


## Get booth types

```shell
curl --location --request GET '{baseurl}/booths/types/' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "type": [
        {
            "id": 1,
            "type": "Reihenstand 21"
        },
        {
            "id": 2,
            "type": "Eckstand"
        }
    ]
}
```

### HTTP request

`GET {baseurl}/booths/types/`

### Query Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| id         | numeric | false    |         |
| language         | String | true    | de_DE        |



## Get exhibitor booth assignments

```shell
curl --location --request GET '{baseurl}/booths/exhibitor/' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "assingments": [
        {
            "boothassignment": "",
            "create_date": "April, 05 2019 15:05:04",
            "change_user": 999,
            "exhibitorboothid": 1108,
            "syncstatus": 0,
            "create_user": 999,
            "note": "",
            "mainexhibitorid": 2279,
            "boothid": 26,
            "change_date": "April, 05 2019 15:05:04",
            "exhibitorfairid": 2280,
            "address": "Testweg 1, 12345 Testen",
            "description": "Lorem ipsum ..."
        },
        {
            "boothassignment": "",
            "create_date": "June, 25 2019 17:03:19",
            "change_user": 667,
            "exhibitorboothid": 1121,
            "syncstatus": 0,
            "create_user": 667,
            "note": "",
            "mainexhibitorid": 0,
            "boothid": 562,
            "change_date": "June, 25 2019 17:03:19",
            "exhibitorfairid": 2305,
            "address": "Musterstraße 12, 12345 Testen",
            "description": "Lorem ipsum ..."
        }
    ]
}
```

### HTTP request

`GET {baseurl}/booths/exhibitor/`

### Query Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| fairid         | numeric | false    |         |
| exhibitorid         | numeric | false    |         |
| exhibitorfairid         | numeric | false    |         |
| exhibitorboothid         | numeric | false    |         |
| mainexhibitorid         | numeric | false    |         |
| language         | String | false    | de_DE        |


## Set exhibitor booth assignment

```shell
curl --location --request POST '{baseurl}/booths/exhibitor/{boothid}/' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "fairid": 7,
    "exhibitorfairid": 96,
    "address": "Testweg 1, 12345 Testen",
    "description": "Lorem ipsum ..."
}'
```

> The above command returns JSON structured like this:

```json
{
    "exhibitorboothid": "1405",
    "error": false
}
```

### HTTP request

`POST {baseurl}/booths/exhibitor/{boothid}/`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| boothid         | numeric | true    |         |

### Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| fairid         | numeric | true    |         |
| exhibitorfairid| numeric | true    |         |
| mainexhibitor  | numeric | true    | 0       |
| note  | String | false    |        |
| postingdate  | date | false    |        |
| boothassignment  | String | false    |        |
| variantid  | numeric | false    |        | Specified variant is ordered when creating |
| address  | string | false    |  |
| description  | string | false    |  |


## Delete exhibitor booth assignment

```shell
curl --location --request DELETE '{baseurl}/booths/exhibitor/{exhibitorboothid}/' \
--header 'X-API-Key: API-Key' \
```

> The above command returns JSON structured like this:

```json
{
    "exhibitorboothid": "1401",
    "error": false
}
```

### HTTP request

`DELETE {baseurl}/booths/exhibitor/{exhibitorboothid}/`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| exhibitorboothid         | numeric | true    |         |


## Get booth reservation

```shell
curl --location --request GET '{baseurl}/booths/reservation/{reservationhash}/' \
--header 'X-API-Key: API-Key' \
```

> The above command returns JSON structured like this:

```json
{
    "fairid": "3",
    "boothids": "S-23,S-24,S-25",
    "hash": "XXXXXXXXXXXXXXXXXXXXXX",
    "expire_date": "2023-06-02 08:13:11",
    "error": false
}
```

### HTTP request

`GET {baseurl}/booths/reservation/{reservationhash}/`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| reservationhash     | string  | true     |         |


## Assign Brand to Booth

```shell
curl --location --request POST '{baseurl}/booths/{exhibitorboothid}/brand/{brand_group_id}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "id": 5
}
```

### HTTP request

`POST {baseurl}/booths/{exhibitorboothid}/brand/{brand_group_id}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| exhibitorboothid         | numeric | true    |         |
| brand_group_id         | numeric | true    |         |


## Unassign Brand from Booth

```shell
curl --location --request DELETE '{baseurl}/booths/{exhibitorboothid}/brand/{brand_group_id}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "id": 117
}
```

### HTTP request

`DELETE {baseurl}/booths/{exhibitorboothid}/brand/{brand_group_id}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| exhibitorboothid         | numeric | true    |         |
| brand_group_id         | numeric | true    |         |

## Assign Branch to Booth

```shell
curl --location --request POST '{baseurl}/booths/{exhibitorboothid}/branch/{branch_group_id}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "id": 7
}
```

### HTTP request

`POST {baseurl}/booths/{exhibitorboothid}/branch/{branch_group_id}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| exhibitorboothid         | numeric | true    |         |
| branch_group_id         | numeric | true    |         |


## Unassign Branch from Booth

```shell
curl --location --request DELETE '{baseurl}/booths/{exhibitorboothid}/branch/{branch_group_id}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "id": 117
}
```

### HTTP request

`DELETE {baseurl}/booths/{exhibitorboothid}/branch/{branch_group_id}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| exhibitorboothid         | numeric | true    |         |
| branch_group_id         | numeric | true    |         |


## Assign Keyword to Booth

```shell
curl --location --request POST '{baseurl}/booths/{exhibitorboothid}/keyword/{keyword_group_id}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "id": 8
}
```

### HTTP request

`POST {baseurl}/booths/{exhibitorboothid}/keyword/{keyword_group_id}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| exhibitorboothid         | numeric | true    |         |
| keyword_group_id         | numeric | true    |         |


## Unassign Keyword from Booth

```shell
curl --location --request DELETE '{baseurl}/booths/{exhibitorboothid}/keyword/{keyword_group_id}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "id": 110
}
```

### HTTP request

`DELETE {baseurl}/booths/{exhibitorboothid}/keyword/{keyword_group_id}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| exhibitorboothid         | numeric | true    |         |
| keyword_group_id         | numeric | true    |         |


## Assign Solution List to Booth

```shell
curl --location --request POST '{baseurl}/booths/{exhibitorboothid}/solution-list/{solution_list_group_id}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "id": 45
}
```

### HTTP request

`POST {baseurl}/booths/{exhibitorboothid}/solution-list/{solution_list_group_id}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| exhibitorboothid         | numeric | true    |         |
| solution_list_group_id         | numeric | true    |         |


## Unassign Solution List from Booth

```shell
curl --location --request DELETE '{baseurl}/booths/{exhibitorboothid}/solution-list/{solution_list_group_id}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "id": 110
}
```

### HTTP request

`DELETE {baseurl}/booths/{exhibitorboothid}/solution-list/{solution_list_group_id}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| exhibitorboothid         | numeric | true    |         |
| solution_list_group_id         | numeric | true    |         |


## Assign Product Group to Booth

```shell
curl --location --request POST '{baseurl}/booths/{exhibitorboothid}/product-group/{product_group_group_id}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "id": 19
}
```

### HTTP request

`POST {baseurl}/booths/{exhibitorboothid}/product-group/{product_group_group_id}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| exhibitorboothid         | numeric | true    |         |
| product_group_group_id         | numeric | true    |         |


## Unassign Product Group from Booth

```shell
curl --location --request DELETE '{baseurl}/booths/{exhibitorboothid}/product-group/{product_group_group_id}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "id": 110
}
```

### HTTP request

`DELETE {baseurl}/booths/{exhibitorboothid}/product-group/{product_group_group_id}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| exhibitorboothid         | numeric | true    |         |
| solution_list_group_id         | numeric | true    |         |


## Assign Contact to Booth

```shell
curl --location --request POST '{baseurl}/booths/{exhibitorboothid}/contact/{contact_id}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "id": 19
}
```

### HTTP request

`POST {baseurl}/booths/{exhibitorboothid}/contact/{contact_id}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| exhibitorboothid         | numeric | true    |         |
| contact_id         | numeric | true    |         |


## Unassign Contact from Booth

```shell
curl --location --request DELETE '{baseurl}/booths/{exhibitorboothid}/contact/{contact_id}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "id": 110
}
```

### HTTP request

`DELETE {baseurl}/booths/{exhibitorboothid}/contact/{contact_id}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| exhibitorboothid         | numeric | true    |         |
| contact_id         | numeric | true    |         |


## Assign Highlight to Booth

```shell
curl --location --request POST '{baseurl}/booths/{exhibitorboothid}/highlight/{highlight_group_id}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "id": 19
}
```

### HTTP request

`POST {baseurl}/booths/{exhibitorboothid}/highlight/{highlight_group_id}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| exhibitorboothid         | numeric | true    |         |
| highlight_group_id         | numeric | true    |         |


## Unassign Highlight from Booth

```shell
curl --location --request DELETE '{baseurl}/booths/{exhibitorboothid}/highlight/{highlight_group_id}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {}
}
```

### HTTP request

`DELETE {baseurl}/booths/{exhibitorboothid}/highlight/{highlight_group_id}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| exhibitorboothid         | numeric | true    |         |
| highlight_group_id         | numeric | true    |         |


## Assign Press Release to Booth

```shell
curl --location --request POST '{baseurl}/booths/{exhibitorboothid}/press-release/{pressrelease_group_id}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "id": 19
}
```

### HTTP request

`POST {baseurl}/booths/{exhibitorboothid}/press-release/{pressrelease_group_id}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| exhibitorboothid         | numeric | true    |         |
| pressrelease_group_id         | numeric | true    |         |


## Unassign Press Release from Booth

```shell
curl --location --request DELETE '{baseurl}/booths/{exhibitorboothid}/press-release/{pressrelease_group_id}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {}
}
```

### HTTP request

`DELETE {baseurl}/booths/{exhibitorboothid}/press-release/{pressrelease_group_id}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| exhibitorboothid         | numeric | true    |         |
| pressrelease_group_id         | numeric | true    |         |
