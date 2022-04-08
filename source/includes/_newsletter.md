# Newsletter

## Get newsletter

```shell
curl --location --request GET '{baseurl}/newsletter/  ' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "newsletter": [
        {
            "text_html": "<p>*ANREDE*<br />\r\n*VORNAME*<br />\r\n*NAME*<br />\r\n*ID*<br />\r\n*BENUTZERNAME*<br />\r\n*PASSWORT*<br />\r\n*INTERESSE_CODE*<br />\r\n*CATCHALL*</p>\r\n",
            "reciver_pool_type": "1",
            "change_user": 60,
            "regard": "sdds",
            "send_at": "",
            "create_user": 61,
            "sender": "yannick@webcontact.de",
            "text": "fff",
            "change_date": "January, 19 2021 14:59:20",
            "create_date": "February, 15 2018 13:40:47",
            "reciver_pool_contactperson": "",
            "fairid": 4,
            "istest": 0,
            "reciver_pool": "1",
            "id": 1,
            "email_type": "html",
            "reciver_pool_acquisition": ""
        },
        {
            "text_html": "",
            "reciver_pool_type": "1",
            "change_user": 50,
            "regard": "С 30 апреля будет поднята стоимость на доп услуги",
            "send_at": "",
            "create_user": 50,
            "sender": "messeleitung@myevent.de",
            "text": "Уважаемы участники выставки Kubex, с 30 апреля будет поднята цена на допуслуги. Успейте приобрести необходимые услуги в разделе Вашего личного кабинета \"Магазин\" по самой низкой цене.",
            "change_date": "April, 02 2018 09:03:09",
            "create_date": "April, 02 2018 08:35:32",
            "reciver_pool_contactperson": "",
            "fairid": 9,
            "istest": 0,
            "reciver_pool": "1",
            "id": 2,
            "email_type": "html",
            "reciver_pool_acquisition": ""
        }
    ],
    "error": false
}
```
### HTTP request

`GET {baseurl}/newsletter/`

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairid | numeric | false |
newsletterid | numeric | false |
sended | Boolean | false |
pooltype | String | false |
poolcontact | String | false |
order | String | false |
poolTyp | String | false |

## Set newsletter

```shell
curl --location --request POST '{baseurl}/newsletter/' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "fairid": 7,
    "sender": "yannick@webcontact.de",
    "regard": "Newsletter über API",
    "text_html": "<h1>Text über API</h1><p>Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.</p>",
    "email_type": "html",
    "pool": "t_1, t_2, a_23, a_32, akquise_32, akquise_2"
}'
```

> The above command returns JSON structured like this:

```json
{
    "newsletter": "25",
    "error": false
}
```

### HTTP request

`POST {baseurl}/newsletter/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairid | numeric | true |
sender | String | true |
regard | String | true |
text_html | String | false |
text | String | false |
email_type | String | true |
istest | Boolean | true | false |

## Delete newsletter

```shell
curl --location --request DELETE '{baseurl}/newsletter/{newsletterid}' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false
}
```

### HTTP request

`DELETE {baseurl}/newsletter/`

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
newsletterid | numeric | true |
