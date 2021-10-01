# Contact persons

## Retreive contact persons

```shell
curl "{baseurl}/contact_persons/" \
  -H "x-api-key: {API-Key}" \
  -X GET \
```

### HTTP request

`GET {baseurl}/contact_persons/`

## Retreive contact person

```shell
curl "{baseurl}/contact_persons/{contact_person_id}" \
  -H "x-api-key: {API-Key}" \
  -X GET \
```

## Create contact person

```shell
curl "{baseurl}/contact_persons/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
salutation | string | true |  |
title | string | false |  |
job_title | string | false |  |
firstname | string | true |  |
lastname | string | true |  |
exhibitor_id | numeric | true |  |
telephone | string | false |  |
mobile | string | false |  |
email | string | true |  |
has_newsletter_approval | boolean | true |  false |
comment | string | false |  |
company | string | false |  |
street | string | false |  |
additional_address | string | false |  |
postalcode | string | false |  |
city | string | false |  |
country | string | false |  |
fair_type_id | numeric | false |  |

## Upload contact person image

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

`POST {baseurl}/contactpersons/upload/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
datasource | string | true |  |
file | binary | true |  |
image_name | string | true |  |
type | string | true |  |
contact_person_id | numeric | true |  |

## Update contact person

### HTTP request

`PUT {baseurl}/contactpersons/{contact_person_id}/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
datasource | string | true |  |
salutation | string | true |  |
title | string | false |  |
job_title | string | false |  |
firstname | string | true |  |
lastname | string | true |  |
exhibitor_id |numeric | true |  |
telephone | string | false |  |
mobile | string | false |  |
email | string | true |  |
has_newsletter_approval | boolean | true | false |
comment | string | false |  |
company | string | false |  |
street | string | false |  |
additional_address | string | false |  |
postalcode |string | false |  |
city | string | false |  |
country | string | false |  |
fair_type_id | numeric | false |  |

## Delete contact person

### HTTP request

`DELETE {baseurl}/contactperson/{contact_person_id}/`


### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
contact_person_id | numeric | true |  |
datasource | string | true |  |
forum_sync | boolean |  false | false |  |
