#  Shop items

## Get items

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

`GET {baseurl}/shop/items/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
datasource | string | true | |
category_id | numeric | false | |
itemnr | string | false | |
language | string | false | de_DE |
item_id | numeric | false | |
fair_id | numeric | false | |
end_date | string | false | |
show_locked | boolean | false | true |
show_coupon | boolean | false | |
show_catchall | boolean | false | |
show_special_coupon | boolean | false | |
user_role_admin | boolean | false | |
user_roles | string | false | |
exhibitor_types | string | false | |

## Get item

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

`GET {baseurl}/shop/items/{item_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
item_id | string | true | |
datasource | string | false | |
category_id | numeric | true | |
itemnr | string | false | |
language | string | false | |
fair_id | numeric | false | |
end_date | string | false | |
show_locked | boolean | false | true |
show_coupon | boolean | false | |
show_catchall | boolean | false | |
show_special_coupon | boolean | false | |
user_role_admin | boolean | false | |
user_roles | string | false | |
exhibitor_types | string | false | |

## Create item

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

`POST {baseurl}/shop/items/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
datasource | string | true | |
type_id | numeric | false | |
category_id | numeric | false | |
itemnr | string | false | |
booth_specific | boolean | true | false |
comment | string | false | |
sort | string | false | |
lock | boolean | true | false |
end_date | string | false | |
item_units | string | false | |
unit_of_measurement | string | false | |
item_title | string | false | |
upload | boolean | true | false |
recommended | boolean | true | false |
languages | any | true | false |
crossselling | string | false | |
dependence | string | false | |
exhibitor_types | string | false | |

## Update item

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

`PUT {baseurl}/shop/items/{item_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
item_id | numeric | true | |
datasource | string | true | |
type_id | numeric | false | |
category_id | numeric | false | |
itemnr | string | false | |
booth_specific | boolean | true | false |
comment | string | false | |
sort | string | false | |
lock | boolean | true | false |
end_date | string | false | |
item_units | string | false | |
unit_of_measurement | string | false | |
item_title | string | false | |
upload | boolean | true | false |
recommended | boolean | true | false |
languages | any | true | false |
crossselling | string | false | |
dependence | string | false | |
exhibitor_types | string | false | |

## Upload item file

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

`POST {baseurl}/shop/items/upload/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
file | binary | true | |
file_name | string | true | |
file_title | string | true | |
item_id | numeric | true | |
language | string | true | |
type | string | true | |

## Delete item

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

`DELETE {baseurl}/shop/items/{item_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
item_id | numeric | true | |

# Shop categories

## Get categories

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

`GET {baseurl}/shop/categories/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
datasource | string | true | |
language | string | false | de_DE |
fair_id | numeric | false | |
show_disabled | boolean | false | false |
hide_coupon | boolean | false | true |

## Get categorie

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

`GET {baseurl}/shop/categories/{categorie_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
category_id | string | true | |
datasource | string | true | |
language | string | false | |
fair_id | numeric | false | |

## Create categroie

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

`POST {baseurl}/shop/categories/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
datasource | string | true | |
parent_id | numeric | false | 0  |
contact_id | numeric | false | |
permissions_group_id | numeric | false | |
fair_id | numeric | false | |
show_coupons_link | boolean | false | false  |
order | numeric | false | |
lock | boolean | false | false  |
languages | string | false | |
auth_user | numeric | true | 666  |

## Update categorie

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

`PUT {baseurl}/shop/categories/{categorie_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
category_id | numeric | false | |
datasource | string | false | |
parent_id | numeric | false | 0 |
contact_id | numeric | false | |
permissions_group_id | numeric | false | |
fair_id | numeric | false | |
show_coupons_link | boolean | false | false |
order | numeric | false | |
lock | boolean | false | false |
languages | string | false | |
auth_user | numeric | false | 666 |

## Delete categorie

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

`DELETE {baseurl}/shop/categories/{categorie_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
category_id | numeric | true | |

# Shop variants

## Get variants

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

`GET {baseurl}/shop/variants/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
datasource | string | false | |
item_id | numeric | false | |
locked | boolean | false | false |
ordered_variants | boolean | false | false |

## Get variant

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

`GET {baseurl}/shop/variants/{variant_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
variants_id | numeric | true | |
datasource | string | true | |
locked | boolean | false | false |
ordered_variants | boolean | false | false |

## Create variant

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

`POST {baseurl}/shop/variants/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
datasource | string | true | |
item_id | numeric | true | |
number_of_pieces | numeric | true | |
price | numeric | true | |
lock | boolean | true | false |
languages | any | true | |

## Upload files

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

`POST {baseurl}/shop/variants/upload/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
file | binary | true | |
file_name | string | true | |
file_title | string | true | |
variants_id | numeric | true | |
language | string | true | |

## Update variant

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

`PUT {baseurl}/shop/variants/{variant_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
variant_id | numeric | true | |
datasource | string | true | |
item_id | numeric | true | |
number_of_pieces | numeric | true | |
price | numeric | true | |
lock | boolean | true | false |
languages | any | true | |

## Delete variant

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

`DELETE {baseurl}/shop/variants/{variant_id}`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
variant_id | numeric | true | |
