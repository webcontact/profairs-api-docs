---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='mailto:kevin@webcontact'>Contact us for a developer key</a>
  - <a href='https://www.profairs.de'>Powered by profairs</a>

includes:
  - acquisition
  - booths
  - contacts
  - exhibitors
  - exhibitor_fair
  - exhibitor_industry
  - fairs
  - fairtypes
  - industries
  - label
  - newsletter
  - publications
  - shop
  - texts
  - users
  - hall_planning

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the profairs API
---

<!-- # Introduction

Welcome to the profairs API! You can use our API to access profairs API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/slatedocs/slate). Feel free to edit it and use it as a base for your own API's documentation. -->

# General

## Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "x-api-key: {API-Key}"
```

> Make sure to replace `{API-Key}` with your API key.

<!-- profairs uses API keys to allow access to the API. You can register a new profairs API key at our [developer portal](http://example.com/developers). -->

profairs expects for the API key to be included in all API requests to the server in a header that looks like the following:

`x-api-key: {API-Key}`

<aside class="notice">
You must replace <code>{API-Key}</code> with your personal API key.
</aside>

## Formatting

### Dates

The date format we use at all endpoints is:

`yyyy-mm-dd HH:nn:ss.000`

### Salutation

The salutation is an enum. The possible values are:

- `SALUTATION-MX`
- `SALUTATION-MS`
- `SALUTATION-MR`

<!-- # Kittens

## Get All Kittens

```ruby
require 'profairs'

api = profairs::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import profairs

api = profairs.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const profairs = require('profairs');

let api = profairs.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'profairs'

api = profairs::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import profairs

api = profairs.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const profairs = require('profairs');

let api = profairs.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'profairs'

api = profairs::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import profairs

api = profairs.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -X DELETE \
  -H "Authorization: meowmeowmeow"
```

```javascript
const profairs = require('profairs');

let api = profairs.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete -->
