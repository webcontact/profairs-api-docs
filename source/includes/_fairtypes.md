# Fair types

## Get fair types

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

`GET {baseurl}/fairtypes/`

## Get fair type

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

`GET {baseurl}/fairtypes/{fair_type_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fair_type_id | numeric | true |

## Create new fair type

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

`POST {baseurl}/fairtypes/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fair_type | string | false |  |
email | string | false |  |
telephone | string | false |  |
redirect | string | false | https:// |
redirect_error | string | false | https:// |

## Update fair type

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

`POST {baseurl}/fairtypes/{fair_type_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fair_type_id | numeric | true | |
datasource | string | true | |
fair_type | string | false | |
email | string | false | |
telephone | string | false | |
redirect | string | false | https:// |
redirect_error | string | false | https:// |
contact_person_id | numeric | false | |

## Delete fair type

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

`DELETE {baseurl}/fairtypes/{fair_type_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fair_type_id | numeric | true | |
