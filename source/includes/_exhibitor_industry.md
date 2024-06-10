# Exhibitors industry assignment
## Get exhibitor industry assignments

```shell
curl --location --request GET '{baseurl}/exhibitor-industry/' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "exhibitor_industry_assignments": [
        {
            "language": "de_DE",
            "create_date": "February, 25 2022 14:58:53",
            "change_user": 667,
            "industry": "Digital",
            "create_user": 667,
            "exhibitor": "12345",
            "industryid": 73,
            "groupid": 197,
            "change_date": "February, 25 2022 14:58:53",
            "exhibitorid": 2299,
            "is_top_of_the_list": 0
        },
        {
            "language": "de_DE",
            "create_date": "February, 25 2022 14:58:38",
            "change_user": 667,
            "industry": "Print",
            "create_user": 667,
            "exhibitor": "12345",
            "industryid": 72,
            "groupid": 198,
            "change_date": "February, 25 2022 14:58:38",
            "exhibitorid": 2299,
            "is_top_of_the_list": 0
        }
    ],
    "error": false
}
```

### HTTP Request

`GET {baseurl}/exhibitor-industry/`

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorid | numeric | true | |
fairtypeid | numeric | false | |
industryid | numeric | false | |
language | String | true | "de_DE" |
showLockedIndustries | Boolean | true | false |

## Create exhibitor industry assignment

```shell
curl --location --request POST '{baseurl}/exhibitor-industry/' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "exhibitorid": 1337,
    "industryid": 20,
    "is_top_of_the_list": 0
}'
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "industryid": 20,
    "exhibitorid": 1337
}
```

### HTTP Request

`POST {baseurl}/exhibitor-industry/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorid | numeric | true | |
industryid | numeric | true | |
is_top_of_the_list | numeric | true | 1 = yes, 0 = no

## Delete exhibitor industry assignment

```shell
curl --location --request DELETE '{baseurl}/exhibitor-industry/{exhibitorid}' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "industryid": "20",
    "exhibitorid": "1337"
}
```

### HTTP Request

`DELETE {baseurl}/exhibitor-industry/{exhibitorid}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorid | numeric | true | |

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
industryid | numeric | true | |
