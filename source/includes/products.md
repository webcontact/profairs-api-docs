# Products

## Get products

```shell
curl --location --request GET '{baseurl}/products' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
  "products": [
    {
      "language": "de_DE",
      "text": "",
      "introduction": "",
      "highlightid": 14,
      "image_subtitle": "Das ist Produktbild",
      "image_mimetype": "image/png",
      "downloadlink": "",
      "id": 80,
      "image_name": "image01.png",
      "link": "https://webcontact.de",
      "title": "Testprodukt",
      "videolink": "",
      "image_preview": "",
      "videolink": "",
      "downloadlink": ""
    }
  ],
  "error": false,
  "error_message": {}
}
```

### HTTP request

`GET {baseurl}/products`

## Get product by Id

```shell
curl --location --request GET '{baseurl}/products/{product_id}' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "pressReleases": [
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
      "title": "dfgsdfhsdfh",
      "image_preview": "",
      "videolink": "",
      "downloadlink": ""
    }
  ]
}
```
### HTTP request

`GET {baseurl}/products/{product_id}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
product_id | numeric | true |

## Create product

```shell
curl --location --request POST '{baseurl}/products' \
--header 'X-API-KEY: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
  "exhibitor_fair_id": "1",
  "title": "Eine neues Produkt",
  "language": "de_DE",
  "image_name": "image03.png",
  "image_preview": "",
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
  "id": "144",
  "error_message": {}
}
```

### HTTP request

`POST {baseurl}/products`

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


## Update product

```shell
curl --location --request PUT '{baseurl}/products/{product_id}' \
--header 'X-API-KEY: {API-Key}' \
--header 'Content-Type: text/json' \
--data-raw '{
  "exhibitor_fair_id": "1",
  "title": "Eine neue Pressemitteilung",
  "language": "de_DE",
  "image_name": "image03.png",
  "image_preview": "",
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
  "id": "14"
}
```

### HTTP request

`PUT {baseurl}/products/{product_id}`

### URL Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
product_id | numeric | true |

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

## Delete product

```shell
curl --location --request DELETE '{baseurl}/products/{product_id}' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "id": "16",
  "error_message": {}
}
```

### HTTP request

`DELETE {baseurl}/products/{product_id}`

### URL Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
product_id | numeric | true |
