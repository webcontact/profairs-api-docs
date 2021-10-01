# Publications

## Get online medias

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`GET {baseurl}/publications/online/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fair_id | numeric | true | |

## Get online media

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`GET {baseurl}/publications/online/{exhibitor_fair_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitor_fair_id | numeric | true | |

## Create online media

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`POST {baseurl}/publications/online/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitor_fair_id | numeric | true | |
language | string | true | |
description | string | false | |
company_description | string | false | |
logo | binary | false | |
logo_name | string | false | |
logo_mimetype | string | false | |
logo_preview | binary | false | |
logo_mimetype | string | false | |
video_url | string | false | |
contact_person_id | numeric | false | |
