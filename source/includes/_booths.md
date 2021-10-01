# Booths

## Get booths

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

`GET {baseurl}/booths/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fair_id | numeric | false |

## Get booth

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

`GET {baseurl}/booths/{booth_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
booth_id | numeric | true |

## Create booth

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

`POST {baseurl}/booths/`

### Parameters

<!-- TODO: SET PARAMS -->
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------

## Update booth

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

`PUT {baseurl}/booths/{booth_id}`
### Parameters

<!-- TODO: SET PARAMS -->
Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------

## Delete booth

```shell
curl "{baseurl}/ENDPOINT/" \
  -H "x-api-key: {API-Key}" \
  -X POST \
```

> The above command returns JSON structured like this:

```json
{}
```

`DELETE {baseurl}/booths/{booth_id}`

### HTTP request

`PUT {baseurl}/booths/{booth_id}`
### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
booth_id | numeric | true | |
forum_sync | boolean | false | false |
