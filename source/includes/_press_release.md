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
      "image_preview": "",
      "keywords": [
        {
          "language": "de_DE",
          "groupId": 8,
          "name": "Stichwort 1",
          "id": 7
        },
        {
          "language": "en_GB",
          "groupId": 8,
          "name": "Keyword 1",
          "id": 8
        },
        {
          "language": "de_DE",
          "groupId": 9,
          "name": "stichwort 2",
          "id": 9
        },
        {
          "language": "en_GB",
          "groupId": 9,
          "name": "Keyword 2",
          "id": 10
        }
      ],
      "solution_list_entries": [
        [
          {
            "language": "de_DE",
            "parentid": 169,
            "name": "Lösungsverzeichniseintrag 1",
            "id": 170,
            "ordernumber": 0
          },
          {
            "language": "en_GB",
            "parentid": 169,
            "name": "Solution List Entry 1",
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
        }
      ],
      "branches": [
        [
          {
            "language": "de_DE",
            "parentid": 0,
            "name": "Branche 1",
            "id": 34,
            "ordernumber": 0
          },
          {
            "language": "en_GB",
            "parentid": 0,
            "name": "Branch 1",
            "id": 34,
            "ordernumber": 0
          }
        ],
        [
          {
            "language": "de_DE",
            "parentid": 0,
            "name": "Branche 2",
            "id": 36,
            "ordernumber": 0
          }
        ],
        [
          {
            "language": "de_DE",
            "parentid": 0,
            "name": "Branch 2",
            "id": 36,
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
        ],
        [
          {
            "language": "de_DE",
            "parentid": 172,
            "name": "Obst",
            "id": 194,
            "ordernumber": 0
          },
          {
            "language": "en_GB",
            "parentid": 172,
            "name": "Fruits",
            "id": 194,
            "ordernumber": 0
          }
        ]
      ]
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
      "image_preview": "",
      "keywords": [
        {
          "language": "de_DE",
          "groupId": 8,
          "name": "Stichwort 1",
          "id": 7
        },
        {
          "language": "en_GB",
          "groupId": 8,
          "name": "Keyword 1",
          "id": 8
        },
        {
          "language": "de_DE",
          "groupId": 9,
          "name": "stichwort 2",
          "id": 9
        },
        {
          "language": "en_GB",
          "groupId": 9,
          "name": "Keyword 2",
          "id": 10
        }
      ],
      "solution_list_entries": [
        [
          {
            "language": "de_DE",
            "parentid": 169,
            "name": "Lösungsverzeichniseintrag 1",
            "id": 170,
            "ordernumber": 0
          },
          {
            "language": "en_GB",
            "parentid": 169,
            "name": "Solution List Entry 1",
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
        }
      ],
      "branches": [
        [
          {
            "language": "de_DE",
            "parentid": 0,
            "name": "Branche 1",
            "id": 34,
            "ordernumber": 0
          },
          {
            "language": "en_GB",
            "parentid": 0,
            "name": "Branch 1",
            "id": 34,
            "ordernumber": 0
          }
        ],
        [
          {
            "language": "de_DE",
            "parentid": 0,
            "name": "Branche 2",
            "id": 36,
            "ordernumber": 0
          }
        ],
        [
          {
            "language": "de_DE",
            "parentid": 0,
            "name": "Branch 2",
            "id": 36,
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
        ],
        [
          {
            "language": "de_DE",
            "parentid": 172,
            "name": "Obst",
            "id": 194,
            "ordernumber": 0
          },
          {
            "language": "en_GB",
            "parentid": 172,
            "name": "Fruits",
            "id": 194,
            "ordernumber": 0
          }
        ]
      ]
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
      "image_preview": "",
      "keywords": [
        {
          "language": "de_DE",
          "groupId": 8,
          "name": "Stichwort 1",
          "id": 7
        },
        {
          "language": "en_GB",
          "groupId": 8,
          "name": "Keyword 1",
          "id": 8
        },
        {
          "language": "de_DE",
          "groupId": 9,
          "name": "stichwort 2",
          "id": 9
        },
        {
          "language": "en_GB",
          "groupId": 9,
          "name": "Keyword 2",
          "id": 10
        }
      ],
      "solution_list_entries": [
        [
          {
            "language": "de_DE",
            "parentid": 169,
            "name": "Lösungsverzeichniseintrag 1",
            "id": 170,
            "ordernumber": 0
          },
          {
            "language": "en_GB",
            "parentid": 169,
            "name": "Solution List Entry 1",
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
        }
      ],
      "branches": [
        [
          {
            "language": "de_DE",
            "parentid": 0,
            "name": "Branche 1",
            "id": 34,
            "ordernumber": 0
          },
          {
            "language": "en_GB",
            "parentid": 0,
            "name": "Branch 1",
            "id": 34,
            "ordernumber": 0
          }
        ],
        [
          {
            "language": "de_DE",
            "parentid": 0,
            "name": "Branche 2",
            "id": 36,
            "ordernumber": 0
          }
        ],
        [
          {
            "language": "de_DE",
            "parentid": 0,
            "name": "Branch 2",
            "id": 36,
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
        ],
        [
          {
            "language": "de_DE",
            "parentid": 172,
            "name": "Obst",
            "id": 194,
            "ordernumber": 0
          },
          {
            "language": "en_GB",
            "parentid": 172,
            "name": "Fruits",
            "id": 194,
            "ordernumber": 0
          }
        ]
      ]
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
  "image_name": "https://URL_TO_IMAGE",
  "image_preview": "https://URL_TO_PREVIEW_IMAGE",
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
  "id": 144,
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
  "image_name": "https://URL_TO_IMAGE",
  "image_preview": "https://URL_TO_PREVIEW_IMAGE",
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
  "id": 14
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
  "id": 16,
  "error_message": {}
}
```

### HTTP request

`DELETE {baseurl}/press-releases/{press_release_id}`

### URL Parameters
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
press_release_id | numeric | true |
