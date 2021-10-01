# Visitors

## Get visitors

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

`GET {baseurl}/visitors/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairid | numeric | false | |

## Get visitor

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

`GET {baseurl}/visitors/{visitor_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
visitor_id | numeric | true | |
datasource | string | true | |
fair_id | numeric | false | |
external | boolean | false | false |

## Create visitor

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

`POST {baseurl}/visitors/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
datasource | string | false | |
external_id | string | false | |
code_id | numeric | false | |
company | string | false |  |
title | string | false |  |
salutation | string | false |  |
firstname | string | false |  |
lastname | string | false |  |
street | string | false |  |
postalcode | string | false |  |
city | string | false |  |
country | string | false | Deutschland |
telephone | string | false |  |
mobil | string | false |  |
latitude | string | false |  |
longitude | string | false |  |
email | string | false |  |
newsletter | boolean | false | false |

## Update visitor

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

`PUT {baseurl}/visitors/{visitor_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
external | boolean | true | false |
datasource | string | true | |
code_id | numeric | true | |
company | string | false |  |
title | string | false |  |
salutation | string | false |  |
firstname | string | false |  |
lastname | string | false |  |
street | string | false |  |
postalcode | string | false |  |
city | string | false |  |
country | string | false | Deutschland |
telephone | string | false |  |
mobil | string | false |  |
latitude | string | false |  |
longitude | string | false |  |
email | string | false |  |
newsletter | boolean | false | false |

## Delete visitor

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

`DELETE {baseurl}/visitors/{visitor_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
visitor_id | numeric | true | |
datasource | string | true | |
external | boolean | true | false |
