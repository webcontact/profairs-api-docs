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
  - brand
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
  - solution_list
  - texts
  - users
  - hall_planning

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the profairs API
---

# General

## Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "x-api-key: {API-Key}"
```

> Make sure to replace `{API-Key}` with your API key.

profairs expects for the API key to be included in all API requests to the server in a header that looks like the following:

`x-api-key: {API-Key}`

<aside class="notice">
You must replace <code>{API-Key}</code> with your personal API key.
</aside>

## Formatting

### Language Codes

If you need to input language codes _(commonly found in the `language` field)_, we use a variation of the BCP 47 standard. Here are some examples:

- `en_GB`
- `de_DE`

### Dates

The date format we use at all endpoints is:

`yyyy-mm-dd HH:nn:ss.000`

### Salutation

The salutation is an enum. The possible values are:

- `SALUTATION-MX`
- `SALUTATION-MS`
- `SALUTATION-MR`
