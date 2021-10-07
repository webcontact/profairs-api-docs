# Shop items

## Get items

```shell
curl --location --request GET '{baseurl}/shop/items' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "items": [
       {
            "language": "de_DE",
            "locked": false,
            "unit": "",
            "booth-specific": true,
            "categoryid": 39,
            "comment": "",
            "article_typ_id": 1,
            "description": "",
            "upload": false,
            "sort": 1,
            "introduction": "Buchbar pro Stromabschluss. Wird der Artikel nicht bestellt, wird der Strombverbrauch pauschal berechnet.",
            "title": "Stromverbrauch f&uuml;r einen bestellten Stromanschluss",
            "closedate": "",
            "itemid": 140
        },
        {
            "language": "de_DE",
            "locked": false,
            "unit": "",
            "booth-specific": false,
            "categoryid": 80,
            "comment": "",
            "article_typ_id": 1,
            "description": "",
            "upload": false,
            "sort": 1,
            "introduction": "Buchbar pro Stromabschluss. Wird der Artikel nicht bestellt, wird der Strombverbrauch pauschal berechnet.",
            "title": "Stromverbrauch f&uuml;r einen bestellten Stromanschluss",
            "closedate": "",
            "itemid": 186
        }
    ]
}
```

### HTTP request

`GET {baseurl}/shop/items/`

### Query Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| categoryid         | numeric | false    |         |
| itemnr              | string  | false    |         |
| language            | string  | false    | de_DE   |
| itemid             | numeric | false    |         |
| fairid             | numeric | false    |         |
| enddate            | string  | false    |         |
| showlocked         | boolean | false    | true    |
| showcoupon         | boolean | false    |         |
| showcatchall       | boolean | false    |         |
| showspecial_coupon | boolean | false    |         |
| userroleadmin     | boolean | false    |         |
| userroles          | string  | false    |         |
| exhibitortypes     | string  | false    |         |

## Get item

```shell
curl --location --request GET '{baseurl}/shop/items/{itemid}' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "items": [
        {
            "language": "de_DE",
            "locked": false,
            "unit": "",
            "booth-specific": false,
            "categoryid": 14,
            "comment": "",
            "article_typ_id": 4,
            "description": "",
            "upload": false,
            "sort": 0,
            "introduction": "",
            "title": "E-Gutschein",
            "closedate": "",
            "itemid": 23
        }
    ]
}
```

### HTTP request

`GET {baseurl}/shop/items/{item_id}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| item_id             | string  | true     |         |

### Query Parameters
| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| itemid             | string  | true     |         |
| categoryid         | numeric | true     |         |
| itemnr              | string  | false    |         |
| language            | string  | false    |         |
| fairid             | numeric | false    |         |
| end_date            | string  | false    |         |
| showlocked         | boolean | false    | true    |
| showcoupon         | boolean | false    |         |
| showcatchall       | boolean | false    |         |
| showspecialcoupon | boolean | false    |         |
| userroleadmin     | boolean | false    |         |
| userroles          | string  | false    |         |
| exhibitortypes     | string  | false    |         |

## Create item

```shell
curl --location --request POST '{baseurl}/shop/items' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
	"type_id": 1,
	"categoryid": 2,
	"itemnr": "AR1234",
	"booth_specific": false,
	"comment": "optional",
	"sort": 10,
	"lock": false,
	"item_units": "10, 20, 30, 50",
	"unit_of_measurement": "cm",
	"upload": false,
	"recommended": true,
    "enddate": "2021-12-31",
	"languages": [
		{
			"language": "de_DE",
			"title": "Lorem Ipsum",
			"introduction": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore",
			"description": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore",
			"comment": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore"
		},
		{
			"language": "en_GB",
			"title": "Lorem Ipsum",
			"introduction": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore",
			"description": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore",
			"comment": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore"
		}
	]
}'
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "itemid": "371"
}
```

### HTTP request

`POST {baseurl}/shop/items/`

### Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| type_id             | numeric | false    |         |
| categoryid         | numeric | false    |         |
| itemnr              | string  | false    |         |
| booth_specific      | boolean | true     | false   |
| comment             | string  | false    |         |
| sort                | string  | false    |         |
| lock                | boolean | true     | false   |
| end_date            | string  | false    |         |
| item_units          | string  | false    |         |
| unit_of_measurement | string  | false    |         |
| item_title          | string  | false    |         |
| upload              | boolean | true     | false   |
| recommended         | boolean | true     | false   |
| languages           | any     | true     | false   |
| crossselling        | string  | false    |         |
| dependence          | string  | false    |         |
| exhibitor_types     | string  | false    |         |

## Update item

```shell
curl --location --request PUT '{baseurl}/shop/items/{itemid)' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
	"type_id": 1,
	"categoryid": 2,
	"itemnr": "AR1234",
	"booth_specific": false,
	"comment": "optional",
	"sort": 10,
	"lock": false,
	"item_units": "10, 20, 30, 50",
	"unit_of_measurement": "cm",
	"upload": false,
	"recommended": true,
    "enddate": "2021-12-31",
	"languages": [
		{
			"language": "de_DE",
			"title": "Lorem Ipsum 123",
			"introduction": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore",
			"description": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore",
			"comment": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore"
		},
		{
			"language": "en_GB",
			"title": "Lorem Ipsum 123",
			"introduction": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore",
			"description": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore",
			"comment": "Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore"
		}
	]
}'
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`PUT {baseurl}/shop/items/{item_id}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| itemid             | numeric | true     |         |

### Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| type_id             | numeric | false    |         |
| categoryid         | numeric | false    |         |
| itemnr              | string  | false    |         |
| booth_specific      | boolean | true     | false   |
| comment             | string  | false    |         |
| sort                | string  | false    |         |
| lock                | boolean | true     | false   |
| end_date            | string  | false    |         |
| item_units          | string  | false    |         |
| unit_of_measurement | string  | false    |         |
| item_title          | string  | false    |         |
| upload              | boolean | true     | false   |
| recommended         | boolean | true     | false   |
| languages           | any     | true     | false   |
| crossselling        | string  | false    |         |
| dependence          | string  | false    |         |
| exhibitor_types     | string  | false    |         |

## Upload item file

```shell
curl --location --request POST '{baseurl}/shop/items/upload/' \
--header 'X-API-Key: {API-Key}' \
--form 'file=@"{file_path}"' \
--form 'file_name="{file_name}"' \
--form 'file_title="Lorum Ipsum"' \
--form 'language="de_DE"' \
--form 'itemid="{itemid}"' \
--form 'type="pdf"'
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "itemid": "370"
}
```

### HTTP request

`POST {baseurl}/shop/items/upload/`

### Parameters

| Parameter  | Type    | required | Default | Description |
| ---------- | ------- | -------- | ------- | ----------- |
| file       | binary  | true     |         |
| file_name  | string  | true     |         |
| file_title | string  | true     |         |
| itemid    | numeric | true     |         |
| language   | string  | true     |         |
| type       | string  | true     |         |

## Delete item

```shell
curl --location --request DELETE '{baseurl}/shop/items/{itemid}' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "itemid": 363,
    "deleted": true
}
```

### HTTP request

`DELETE {baseurl}/shop/items/{item_id}`

### URL Parameters

| Parameter | Type    | required | Default | Description |
| --------- | ------- | -------- | ------- | ----------- |
| itemid   | numeric | true     |         |

# Shop categories

## Get categories

```shell
curl --location --request GET '{baseurl}/shop/categories?fairid={fairid}' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "categories": [
      {
            "language": "de_DE",
            "infobox_title": "",
            "locked": false,
            "description": "&lt;p&gt;Im Folgenden haben Sie die M&ouml;glichkeit &lt;strong&gt;Sonderwerbeformen &lt;&#x2f;strong&gt;zu bestellen.&amp;nbsp&#x3b;Alle Preise in Euro zuz&uuml;glich der gesetzlichen MwSt.&lt;&#x2f;p&gt;&#xd;&#xa;",
            "category": "Sonderwerbeformen",
            "contact_id": "",
            "id": 42,
            "infobox_description": "",
            "parent_id": 47
        },
        {
            "language": "de_DE",
            "infobox_title": "",
            "locked": false,
            "description": "&lt;p&gt;Die Standausstattung muss separat gebucht werden.&lt;&#x2f;p&gt;&#xd;&#xa;",
            "category": "Standausstattung",
            "contact_id": "",
            "id": 27,
            "infobox_description": "",
            "parent_id": 32
        }
    ]
}
```

### HTTP request

`GET {baseurl}/shop/categories/`

### Query Parameters

| Parameter     | Type    | required | Default | Description |
| ------------- | ------- | -------- | ------- | ----------- |
| fairid       | numeric | false    |         |
| language      | string  | false    | de_DE   |
| show_disabled | boolean | false    | false   |
| hide_coupon   | boolean | false    | true    |

## Get categorie

```shell
curl --location --request GET '{baseurl}/shop/categories/{categoryid}' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "categories": [
        {
            "language": "de_DE",
            "infobox_title": "",
            "locked": false,
            "description": "&lt;p&gt;Die Standausstattung muss separat gebucht werden.&lt;/p&gt;\n",
            "category": "Standausstattung",
            "contact_id": "",
            "id": 27,
            "infobox_description": "",
            "parent_id": 32
        }
    ]
}
```

### HTTP request

`GET {baseurl}/shop/categories/{categorie_id}`

### URL Parameters

| Parameter   | Type    | required | Default | Description |
| ----------- | ------- | -------- | ------- | ----------- |
| categoryid | string  | true     |         |

### Query Parameters

| Parameter   | Type    | required | Default | Description |
| ----------- | ------- | -------- | ------- | ----------- |
| language    | string  | false    |         |
| fairid     | numeric | false    |         |

## Create categroie

```shell
curl --location --request POST '{baseurl}/shop/categories/' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "parent_id": 0,
    "contact_id": 12,
    "permissions_group_id": 1,
    "fairid": 7,
    "show_coupons_link": true,
    "order": 10,
    "lock": false,
    "languages": [
        {
            "language": "de_DE",
            "title": "Lorem Ipsum",
            "description": "Lorem Ipsum",
            "infobox_headline": "Lorem Ipsum",
            "infobox_description": "Lorem Ipsum"
        },
        {
            "language": "en_GB",
            "title": "Lorem Ipsum",
            "description": "Lorem Ipsum",
            "infobox_headline": "Lorem Ipsum",
            "infobox_description": "Lorem Ipsum"
        }
    ]
}
'
```

> The above command returns JSON structured like this:

```json
{
    "categoryid": "171",
    "error": false
}
```

### HTTP request

`POST {baseurl}/shop/categories/`

### Parameters

| Parameter            | Type    | required | Default | Description |
| -------------------- | ------- | -------- | ------- | ----------- |
| parent_id            | numeric | false    | 0       |
| contact_id           | numeric | false    |         |
| permissions_group_id | numeric | false    |         |
| fairid              | numeric | false    |         |
| show_coupons_link    | boolean | false    | false   |
| order                | numeric | false    |         |
| lock                 | boolean | false    | false   |
| languages            | array of objects  | false    |         |

### Languages details

| Parameter            | Type    | required | Default | Description |
| -------------------- | ------- | -------- | ------- | ----------- |
| language            | string | true    |       |
| title           | string | true    |         |
| description | string | true    |         |
| infobox_headline    | string | true    |   |
| infobox_description | string | true    |         |

## Update categorie

```shell
curl --location --request PUT '{baseurl}/shop/categories/{categoryid}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "parent_id": 0,
    "contact_id": 12,
    "permissions_group_id": 1,
    "fairid": 7,
    "show_coupons_link": true,
    "order": 10,
    "lock": false,
    "languages": [
        {
            "language": "de_DE",
            "title": "Lorem Ipsum",
            "description": "Lorem Ipsum",
            "infobox_headline": "Lorem Ipsum",
            "infobox_description": "Lorem Ipsum"
        },
        {
            "language": "en_GB",
            "title": "Lorem Ipsum",
            "description": "Lorem Ipsum",
            "infobox_headline": "Lorem Ipsum",
            "infobox_description": "Lorem Ipsum"
        }
    ]
}
'
```

> The above command returns JSON structured like this:

```json
{
    "categoryid": 166,
    "error": false
}
```

### HTTP request

`PUT {baseurl}/shop/categories/{categoryid}`

### URL Parameters

| Parameter            | Type    | required | Default | Description |
| -------------------- | ------- | -------- | ------- | ----------- |
| categoryid           | numeric | true     |       |

### Parameters

| Parameter            | Type    | required | Default | Description |
| -------------------- | ------- | -------- | ------- | ----------- |
| parent_id            | numeric | false    | 0       |
| contact_id           | numeric | false    |         |
| permissions_group_id | numeric | false    |         |
| fairid              | numeric | false    |         |
| show_coupons_link    | boolean | false    | false   |
| order                | numeric | false    |         |
| lock                 | boolean | false    | false   |
| languages            | array of objects  | false    |         |

### Languages details

| Parameter            | Type    | required | Default | Description |
| -------------------- | ------- | -------- | ------- | ----------- |
| language            | string | true    |       |
| title           | string | true    |         |
| description | string | true    |         |
| infobox_headline    | string | true    |   |
| infobox_description | string | true    |         |

## Delete categorie

```shell
curl --location --request DELETE '{baseurl}/shop/categories/{categoryid}' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "categoryid": 170,
    "error": false,
    "deleted": true
}
```

### HTTP request

`DELETE {baseurl}/shop/categories/{categoryid}`

### URL Parameters

| Parameter   | Type    | required | Default | Description |
| ----------- | ------- | -------- | ------- | ----------- |
| categoryid | numeric | true     |         |

# Shop variants

## Get variants

```shell
curl --location --request GET '{baseurl}/shop/variants?itemid={itemid}' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "variants": [
        {
            "language": "de_DE",
            "variantid": 593,
            "price": 39.0,
            "amount": "",
            "orders": "",
            "title": "weiß - T06w",
            "text": "",
            "itemid": 337
        },
        {
            "language": "de_DE",
            "variantid": 594,
            "price": 39.0,
            "amount": "",
            "orders": "",
            "title": "schwarz - T06s",
            "text": "",
            "itemid": 337
        }
    ],
    "error": false
}
```

### HTTP request

`GET {baseurl}/shop/variants/`

### Query Parameters

| Parameter        | Type    | required | Default | Description |
| ---------------- | ------- | -------- | ------- | ----------- |
| item_id          | numeric | true    |         |
| locked           | boolean | false    | false   |
| ordered_variants | boolean | false    | false   |

## Get variant

```shell
curl --location --request GET '{baseurl}/shop/variants/{variantid}' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "variants": [
        {
            "language": "de_DE",
            "price": 39.0,
            "amount": "",
            "orders": "",
            "title": "weiß - T06w",
            "text": "",
            "id": 593,
            "itemid": 337
        }
    ],
    "error": false
}
```

### HTTP request

`GET {baseurl}/shop/variants/{variantid}`

### URL Parameters

| Parameter        | Type    | required | Default | Description |
| ---------------- | ------- | -------- | ------- | ----------- |
| variants_id      | numeric | true     |         |

### Query Parameters

| Parameter        | Type    | required | Default | Description |
| ---------------- | ------- | -------- | ------- | ----------- |
| locked           | boolean | false    | false   |
| ordered_variants | boolean | false    | false   |

## Create variant

```shell
curl --location --request POST '{baseurl}/shop/variants/' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "itemid": 1337,
    "price": 100,
    "number_of_pieces": 999,
    "lock": false,
    "languages": [
        {
            "language": "de_DE",
            "title": "Lorem Ipsum",
            "description": "Lorem Ipsum"
        },
        {
            "language": "en_GB",
            "title": "Lorem Ipsum",
            "description": "Lorem Ipsum"
        }
    ]
}
'
```

> The above command returns JSON structured like this:

```json
{
    "variantid": "617",
    "error": false
}
```

### HTTP request

`POST {baseurl}/shop/variants/`

### Parameters

| Parameter        | Type    | required | Default | Description |
| ---------------- | ------- | -------- | ------- | ----------- |
| itemid          | numeric | true     |         |
| number_of_pieces | numeric | true     |         |
| price            | numeric | true     |         |
| lock             | boolean | true     | false   |
| languages        | any     | true     |         |

## Upload files

```shell
curl --location --request POST '{baseurl}/shop/variants/upload/' \
--header 'X-API-Key: {API-Key}' \
--form 'file=@"{file_path}"' \
--form 'file_name="{file_name"' \
--form 'file_title="{file_title}"' \
--form 'variantid="{variantid}"' \
--form 'language="de_DE"'
```

> The above command returns JSON structured like this:

```json
{
    "variantid": "616",
    "updated": true,
    "error": false
}
```

### HTTP request

`POST {baseurl}/shop/variants/upload/`

### Parameters

| Parameter   | Type    | required | Default | Description |
| ----------- | ------- | -------- | ------- | ----------- |
| file        | binary  | true     |         |
| file_name   | string  | true     |         |
| file_title  | string  | true     |         |
| variantsid | numeric | true     |         |
| language    | string  | true     |         |

## Update variant

```shell
curl --location --request PUT '{baseurl}/shop/variants/{variantid}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
    "itemid": 1337,
    "price": 100,
    "number_of_pieces": 999,
    "lock": false,
    "languages": [
        {
            "language": "de_DE",
            "title": "Lorem Ipsum",
            "description": "Lorem Ipsum"
        },
        {
            "language": "en_GB",
            "title": "Lorem Ipsum",
            "description": "Lorem Ipsum"
        }
    ]
}
'
```

> The above command returns JSON structured like this:

```json
{
    "variantid": 1337,
    "error": false
}
```

### HTTP request

`PUT {baseurl}/shop/variants/{variantid}`

### Parameters

| Parameter        | Type    | required | Default | Description |
| ---------------- | ------- | -------- | ------- | ----------- |
| variantid       | numeric | true     |         |
| itemid          | numeric | true     |         |
| number_of_pieces | numeric | true     |         |
| price            | numeric | true     |         |
| lock             | boolean | true     | false   |
| languages        | any     | true     |         |

## Delete variant

```shell
curl --location --request DELETE '{baseurl}/shop/variants/{variantid}' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{}
```

### HTTP request

`DELETE {baseurl}/shop/variants/{variantid}`

### Parameters

| Parameter  | Type    | required | Default | Description |
| ---------- | ------- | -------- | ------- | ----------- |
| variantid | numeric | true     |         |
