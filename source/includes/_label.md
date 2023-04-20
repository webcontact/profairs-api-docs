# Labels

## Get labels

```shell
curl --location --request GET '{baseurl}/label/  ' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "labels": [
        {
            "de_DE": "Storniert",
            "module": "shop",
            "color": "#d62e2e",
            "en_GB": "Storniert",
            "id": 40
        },
        {
            "de_DE": "Erledigt",
            "module": "shop",
            "color": "#4fdf01",
            "en_GB": "Done",
            "id": 42
        }
    ]
}
```
### HTTP request

`GET {baseurl}/label/`

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
module | String | true | |  Either "akquise" or "shop"

## Set label

```shell
curl --location --request POST '{baseur}/label/' \
--header 'X-API-KEY: {baseurl}' \
--header 'Content-Type: text/plain' \
--data-raw '{
    "module": "shop",
    "de_DE": "Test DE",
    "en_GB": "Test EN",
    "color": "#000"
}'
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "boothid": "70"
}
```

### HTTP request

`POST {baseurl}/label/`

### Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| module         | String | true    |         | Either "akquise" or "shop"
| de_DE         | String | true    |         |
| en_DE         | String | true    |         |
| color         | String | true    |         | Color as Hex-Code


## Delete label

```shell
curl --location --request DELETE '{baseurl}/label/{labelid}' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false
}
```

### HTTP request

`DELETE {baseurl}/label/{labelid}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| labelid         | numeric | true    |         |
