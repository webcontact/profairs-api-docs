# Press Releases

## Get press releases

```shell
curl --location --request GET '{baseurl}/press-releases' \
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
      "highlightid": 9,
      "image_subtitle": "This is an image",
      "image_mimetype": "image/png",
      "id": 74,
      "image_name": "image01.png",
      "link": "https://webcontact.de",
      "title": "Lorem Ipsum...",
      "image_preview": ""
    },
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
      "image_preview": ""
    }
  ]
}
```

### HTTP request

`GET {baseurl}/press-releases`


## Get press release by Id

```shell
curl --location --request GET '{baseurl}/press-releases/{press_release_id}' \
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
      "image_preview": ""
    }
  ]
}
```

### HTTP request

`GET {baseurl}/press-releases/{press_release_id}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
press_release_id | numeric | true |

## Create press release

```shell
curl --location --request POST '{baseurl}/press-releases' \
--header 'X-API-KEY: {API-Key}' \
--header 'Content-Type: application/json' \
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

`POST {baseurl}/press-releases`

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


## Update press release

```shell
curl --location --request PUT '{baseurl}/press-releases/{press_release_id}' \
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

`PUT {baseurl}/press-releases/{press_release_id}`

### URL Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
press_release_id | numeric | true |

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

## Delete press release

```shell
curl --location --request DELETE '{baseurl}/press-releases/{press_release_id}' \
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

`DELETE {baseurl}/press-releases/{press_release_id}`

### URL Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
press_release_id | numeric | true |
