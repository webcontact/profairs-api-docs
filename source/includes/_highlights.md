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
      "highlightid": 14,
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
      "downloadlink": ""
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
curl --location --request GET '{baseurl}/highlights/{highlight_id}' \
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
      "highlightid": 10,
      "image_subtitle": "This is another image", 
      "image_mimetype": "image/jpeg",
      "id": 75,
      "image_name": "02.jpeg",
      "link": "https://webcontact.de",
      "title": "Lorem ipsum...",
      "image_preview": "",
      "videolink": "",
      "downloadlink": ""
    }
  ]
}
```
### HTTP request

`GET {baseurl}/highlights/{highlight_id}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
highlight_id | numeric | true |

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
highlightid | numeric | false | | | use this parameter to add a new entry to an existing highlight in another language


## Update highlight

```shell
curl --location --request PUT '{baseurl}/highlights/{highlight_id}' \
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

`PUT {baseurl}/highlights/{highlight_id}`

### URL Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
highlight_id | numeric | true |

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

## Delete Highlight

```shell
curl --location --request DELETE '{baseurl}/highlights/{highlight_id}' \
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

`DELETE {baseurl}/highlights/{highlight_id}`

### URL Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
highlight_id | numeric | true |
