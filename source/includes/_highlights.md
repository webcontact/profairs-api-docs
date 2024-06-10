# Highlights

## Get highlights

```shell
curl --location --request GET '{baseurl}/highlights' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
  "highlights": [
    {
      "language": "de_DE",
      "text": "",
      "introduction": "",
      "groupid": 14,
      "image_subtitle": "Das ist ein Highlightbild",
      "image_mimetype": "image/png",
      "downloadlink": "",
      "id": 80,
      "image_name": "image01.png",
      "link": "https://webcontact.de",
      "title": "TestHighlight",
      "videolink": "",
      "image_preview": "preview_image01.png",
      "videolink": "",
      "downloadlink": "",
      "keywords": [
        {
          "language": "de_DE",
          "groupId": 26,
          "name": "Stichwort 1",
          "id": 26
        },
        {
          "language": "en_GB",
          "groupId": 26,
          "name": "Keyword 1",
          "id": 27
        },
        {
          "language": "de_DE",
          "groupId": 26,
          "name": "Stichwort 2",
          "id": 26
        },
        {
          "language": "en_GB",
          "groupId": 26,
          "name": "Keyword 2",
          "id": 27
        }
      ],
      "solution_list_entries": [
        [
          {
            "language": "de_DE",
            "parentid": 169,
            "name": "klimaneutral",
            "id": 170,
            "ordernumber": 0
          },
          {
            "language": "en_GB",
            "parentid": 169,
            "name": "climate neutral",
            "id": 170,
            "ordernumber": 0
          }
        ]
      ],
      "brands": [
        {
          "language": "de_DE",
          "groupId": 11,
          "name": "Marke 1",
          "id": 12
        },
        {
          "language": "de_DE",
          "groupId": 13,
          "name": "Marke 2",
          "id": 14
        },
      ],
      "branches": [
        [
          {
            "language": "de_DE",
            "parentid": 0,
            "name": "Architektur",
            "id": 34,
            "ordernumber": 0
          },
          {
            "language": "en_GB",
            "parentid": 0,
            "name": "Architecture",
            "id": 34,
            "ordernumber": 0
          }
        ]
      ],
      "product_group": [
        [
          {
            "language": "de_DE",
            "parentid": 172,
            "name": "Gemüse",
            "id": 195,
            "ordernumber": 0
          },
          {
            "language": "en_GB",
            "parentid": 172,
            "name": "Vegetables",
            "id": 195,
            "ordernumber": 0
          }
        ],
        [
          {
            "language": "de_DE",
            "parentid": 172,
            "name": "Getreide",
            "id": 196,
            "ordernumber": 0
          },
          {
            "language": "en_GB",
            "parentid": 172,
            "name": "Cereals",
            "id": 196,
            "ordernumber": 0
          }
        ]
      ]
    }
  ],
  "error": false,
  "error_message": {}
}
```

### HTTP request

`GET {baseurl}/highlights`

## Get highlight by Id

```shell
curl --location --request GET '{baseurl}/highlights/{id}' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "highlights": [
    {
      "language": "de_DE",
      "text": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut l",
      "introduction": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut l",
      "groupid": 10,
      "image_subtitle": "This is another image", 
      "image_mimetype": "image/jpeg",
      "id": 75,
      "image_name": "02.jpeg",
      "link": "https://webcontact.de",
      "title": "Lorem ipsum...",
      "image_preview": "",
      "videolink": "",
      "downloadlink": "",
      "keywords": [
        {
          "language": "de_DE",
          "groupId": 26,
          "name": "Stichwort 1",
          "id": 26
        },
        {
          "language": "en_GB",
          "groupId": 26,
          "name": "Keyword 1",
          "id": 27
        },
        {
          "language": "de_DE",
          "groupId": 26,
          "name": "Stichwort 2",
          "id": 26
        },
        {
          "language": "en_GB",
          "groupId": 26,
          "name": "Keyword 2",
          "id": 27
        }
      ],
      "solution_list_entries": [
        [
          {
            "language": "de_DE",
            "parentid": 169,
            "name": "klimaneutral",
            "id": 170,
            "ordernumber": 0
          },
          {
            "language": "en_GB",
            "parentid": 169,
            "name": "climate neutral",
            "id": 170,
            "ordernumber": 0
          }
        ]
      ],
      "brands": [
        {
          "language": "de_DE",
          "groupId": 11,
          "name": "Marke 1",
          "id": 12
        },
        {
          "language": "de_DE",
          "groupId": 13,
          "name": "Marke 2",
          "id": 14
        },
      ],
      "branches": [
        [
          {
            "language": "de_DE",
            "parentid": 0,
            "name": "Architektur",
            "id": 34,
            "ordernumber": 0
          },
          {
            "language": "en_GB",
            "parentid": 0,
            "name": "Architecture",
            "id": 34,
            "ordernumber": 0
          }
        ]
      ],
      "product_group": [
        [
          {
            "language": "de_DE",
            "parentid": 172,
            "name": "Gemüse",
            "id": 195,
            "ordernumber": 0
          },
          {
            "language": "en_GB",
            "parentid": 172,
            "name": "Vegetables",
            "id": 195,
            "ordernumber": 0
          }
        ],
        [
          {
            "language": "de_DE",
            "parentid": 172,
            "name": "Getreide",
            "id": 196,
            "ordernumber": 0
          },
          {
            "language": "en_GB",
            "parentid": 172,
            "name": "Cereals",
            "id": 196,
            "ordernumber": 0
          }
        ]
      ]
    }
  ]
}
```
### HTTP request

`GET {baseurl}/highlights/{id}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
id | numeric | true |

## Create highlight

```shell
curl --location --request POST '{baseurl}/highlights' \
--header 'X-API-KEY: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
  "exhibitor_fair_id": "1",
  "title": "Eine neues Highlight",
  "language": "de_DE",
  "image_name": "https://URL_TO_IMAGE",
  "image_preview": "https://URL_TO_PREVIEW_IMAGE",
  "image_mimetype": "image/png",
  "introduction": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut",
  "text": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut",
  "link": "https://webcontact.de",
  "videolink": "",
  "downloadlink": "",
  "groupid": 19
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

`POST {baseurl}/highlights`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitor_fair_id | numeric | true | | |
language | string | true | |
title | string | true | | |
image_name | string | false | | |
image_preview | string | false | | |
image_mimetype | string | false | | |
introduction | string | false | | |
text | string | false | | |
link | string | false | | |
videolink | string | false | | |
downloadlink | string | false | | |
groupid | numeric | false | | | use this parameter to add a new entry to an existing highlight in another language


## Update highlight

```shell
curl --location --request PUT '{baseurl}/highlights/{id}' \
--header 'X-API-KEY: {API-Key}' \
--header 'Content-Type: text/json' \
--data-raw '{
  "exhibitor_fair_id": "1",
  "title": "Eine aktualisiertes Highlight",
  "language": "de_DE",
  "image_name": "https://URL_TO_IMAGE",
  "image_preview": "https://URL_TO_PREVIEW_IMAGE",
  "image_mimetype": "image/png",
  "introduction": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut",
  "text": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut",
  "link": "https://webcontact.de",
  "videolink": "",
  "downloadlink": "",
  "groupid": 19
}'
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "id": 14
}
```

### HTTP request

`PUT {baseurl}/highlights/{id}`

### URL Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
id | numeric | true |

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitor_fair_id | numeric | true | | |
language | string | true | |
title | string | true | | |
image_name | string | false | | |
image_preview | string | false | | |
image_mimetype | string | false | | |
introduction | string | false | | |
text | string | false | | |
link | string | false | | |
videolink | string | false | | |
downloadlink | string | false | | |
groupid | numeric | false | | | use this parameter to add a new entry to an existing press release in another language

## Delete Highlight

```shell
curl --location --request DELETE '{baseurl}/highlights/{id}' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "id": 16,
  "error_message": {}
}
```

### HTTP request

`DELETE {baseurl}/highlights/{id}`

### URL Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
id | numeric | true |


## Assign Brand to Highlight

```shell
curl --location --request POST '{baseurl}/highlights/{highlight_group_id}/brand' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
--data-raw '{
  "brand_group_id": 4
}'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "id": 40
}
```

### HTTP request

`POST {baseurl}/highlights/{highlight_group_id}/brand`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| highlight_group_id         | numeric | true    |         |

### Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| brand_group_id         | numeric | true    |         |


## Unassign Brand from Highlight

```shell
curl --location --request DELETE '{baseurl}/highlights/{highlight_group_id}/brand/{brand_group_id}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "id": 40
}
```

### HTTP request

`DELETE {baseurl}/highlights/{highlight_group_id}/brand/{brand_group_id}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| highlight_group_id         | numeric | true    |         |
| brand_group_id         | numeric | true    |         |


## Assign Branch to Highlight

```shell
curl --location --request POST '{baseurl}/highlights/{highlight_group_id}/branch' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
--data-raw '{
  "branch_group_id": 6
}'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "id": 42
}
```

### HTTP request

`POST {baseurl}/highlights/{highlight_group_id}/branch`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| highlight_group_id         | numeric | true    |         |

### Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| branch_group_id         | numeric | true    |         |


## Unassign Branch from Highlight

```shell
curl --location --request DELETE '{baseurl}/highlights/{highlight_group_id}/branch/{branch_group_id}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "id": 40
}
```

### HTTP request

`DELETE {baseurl}/highlights/{highlight_group_id}/branch/{branch_group_id}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| highlight_group_id         | numeric | true    |         |
| brand_group_id         | numeric | true    |         |


## Assign Product Group to Highlight

```shell
curl --location --request POST '{baseurl}/highlights/{highlight_group_id}/product-group' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
--data-raw '{
  "branch_group_id": 6
}'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "id": 42
}
```

### HTTP request

`POST {baseurl}/highlights/{highlight_group_id}/product-group`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| highlight_group_id         | numeric | true    |         |

### Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| product-group_group-id         | numeric | true    |         |


## Unassign Product Group from Highlight

```shell
curl --location --request DELETE '{baseurl}/highlights/{highlight_group_id}/product-group/{product-group_group-id}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "id": 40
}
```

### HTTP request

`DELETE {baseurl}/highlights/{highlight_group_id}/product-group/{product-group_group-id}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| highlight_group_id         | numeric | true    |         |
| product-group_group-id         | numeric | true    |         |


## Assign Solution List to Highlight

```shell
curl --location --request POST '{baseurl}/highlights/{highlight_group_id}/solution-list' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
--data-raw '{
  "solution-list_group-id": 6
}'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "id": 42
}
```

### HTTP request

`POST {baseurl}/highlights/{highlight_group_id}/product-group`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| highlight_group_id         | numeric | true    |         |

### Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| solution-list_group-id         | numeric | true    |         |


## Unassign Solution List from Highlight

```shell
curl --location --request DELETE '{baseurl}/highlights/{highlight_group_id}/solution-list/{solution-list_group-id}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "id": 40
}
```

### HTTP request

`DELETE {baseurl}/highlights/{highlight_group_id}/solution-list/{solution-list_group-id}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| highlight_group_id         | numeric | true    |         |
| solution-list_group-id         | numeric | true    |         |
