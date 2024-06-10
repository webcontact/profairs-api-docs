# Exhibitor profile

## Get profile

```shell
curl --location --request GET '{baseurl}/exhibitors/{exhibitorfairid}/profile' \
--header 'X-API-KEY: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "profile": [
    {
      "ueber_uns": "Lorem ipsim ...",
      "anzahl_mitarbeiter": "100",
      "praxis": "Lorem ipsim ...",
      "anzeige_typ": "",
      "text": "test",
      "social_media_4": "",
      "bewerbungsverfahren": "Lorem ipsim ...",
      "einstiegsmoeglichkeit": "Lorem ipsim ...",
      "social_media_2": "",
      "social_media_5": "",
      "hauptsitz": "Stuttgart",
      "qualifikationen": "Lorem ipsim ...",
      "unternehmensbeschreibung": "Lorem ipsum...",
      "sprache": "de_DE",
      "logo_mimetype": "image/png",
      "videourl": "https://url_to_the_video",
      "logo": "aHR0cHM6Ly91cmxfdG9fdGhlX2xvZ28ucG5n",
      "social_media_1": "",
      "postanschrift": "Musterstraße 1",
      "logo_name": "logo.png",
      "consultation": 0,
      "logo_vorschau": "bG9nb19wcmV2aWV3LnBuZw==",
      "standorte": "München, Köln, Berlin",
      "profil": "Lorem ipsim ...",
      "social_media_3": "",
      "brands": [
        {
          "language": "de_DE",
          "groupid": 11,
          "name": "Mustermarke",
          "id": 11
        }
      ],
      "branches": [
        {
          "language": "de_DE",
          "parentid": 2,
          "groupid": 197,
          "name": "Architektur",
          "id": 197,
          "ordernumber": 0
        }
      ],
      "keywords": [
        {
          "language": "de_DE",
          "groupid": 26,
          "name": "Stichwort3",
          "id": 26
        }
      ],
    },
    {
      "ueber_uns": "Lorem ipsim ...",
      "anzahl_mitarbeiter": "100",
      "praxis": "Lorem ipsim ...",
      "anzeige_typ": "",
      "text": "test",
      "social_media_4": "",
      "bewerbungsverfahren": "Lorem ipsim ...",
      "einstiegsmoeglichkeit": "Lorem ipsim ...",
      "social_media_2": "",
      "social_media_5": "",
      "hauptsitz": "Stuttgart",
      "qualifikationen": "Lorem ipsim ...",
      "unternehmensbeschreibung": "Lorem ipsum...",
      "sprache": "en_GB",
      "logo_mimetype": "image/png",
      "videourl": "https://url_to_the_video",
      "logo": "aHR0cHM6Ly91cmxfdG9fdGhlX2xvZ28ucG5n",
      "social_media_1": "",
      "postanschrift": "Main Street 1",
      "logo_name": "logo.png",
      "consultation": 0,
      "logo_vorschau": "bG9nb19wcmV2aWV3LnBuZw==",
      "standorte": "London, Leeds, Liverpool",
      "profil": "Lorem ipsim ...",
      "social_media_3": "",
      "brands": [
        {
          "language": "en_GB",
          "groupid": 11,
          "name": "Test Brand",
          "id": 11
        }
      ],
      "branches": [
        {
          "language": "en_GB",
          "parentid": 2,
          "groupid": 197,
          "name": "Architectur",
          "id": 197,
          "ordernumber": 0
        }
      ],
      "keywords": [
        {
          "language": "en_GB",
          "groupid": 26,
          "name": "Keyword 3",
          "id": 26
        }
      ],
    }
]
```

### HTTP request

`GET {baseurl}/exhibitors/{exhibitorfairid}/profile`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorfairid | numeric | true |

## Set profile

```shell
curl --location --request POST '{baseurl}/exhibitors/{exhibitorfairid}/profile' \
--header 'X-API-KEY: {API-Key}' \
--header 'Content-Type: application/json' \
--data-raw '{
  "sprache": "de_DE",
  "text": "test",
  "logo": "https://url_to_the_logo.png",
  "unternehmensbeschreibung": "Lorem ipsum...",
  "logo_name": "https://URL_TO_IMAGE",
  "logo_vorschau": "https://URL_TO_PREVIEW_IMAGE",
  "logo_mimetype": "image/png",
  "videourl": "https://URL_TO_VIDEO",
  "ueber_uns": "Lorem ipsim ...",
  "bewerbungsverfahren": "Lorem ipsim ...",
  "einstiegsmoeglichkeit": "Lorem ipsim ...",
  "praxis": "Lorem ipsim ...",
  "profil": "Lorem ipsim ...",
  "qualifikationen": "Lorem ipsim ...",
  "anzeige_typ": "",
  "postanschrift": "Musterstraße 1",
  "consultation": "0",
  "hauptsitz": "Stuttgart",
  "standorte": "München, Köln, Berlin",
  "anzahl_mitarbeiter": "100",
  "social_media_1": "",
  "social_media_2": "",
  "social_media_3": "",
  "social_media_4": "",
  "social_media_5": ""
}'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "id": 14,
  "error_message": {}
}
```

### HTTP request

`POST {baseurl}/exhibitors/{exhibitorfairid}/profile`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitorfairid | numeric | true |

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
sprache | string | true | | |
text | string | false | | |
logo | string | false | | |
unternehmensbeschreibung | string | false | | |
logo_name | string | false | | |
logo_vorschau | string | false | | |
logo_mimetype | string | false | | |
videourl | string | false | | |
ueber_uns | string | false | | |
bewerbungsverfahren | string | false | | |
einstiegsmoeglichkeit | string | false | | |
praxis | string | false | | |
profil | string | false | | |
qualifikationen | string | false | | |
anzeige_typ | string | false | | |
postanschrift | string | false | | |
consultation | numeric | false | | 0 or 1|
hauptsitz | string | false | | |
standorte | string | false | | |
anzahl_mitarbeiter | string | false | | |
social_media_1 | string | false | | |
social_media_2 | string | false | | |
social_media_3 | string | false | | |
social_media_4 | string | false | | |
social_media_5 | string | false | | |


## Assign Branch to Exhibitor Profile

```shell
curl --location --request POST '{baseurl}/exhibitors/{exhibitorfairid}/profile/branch/{branch_group_id}/{locale}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "id": 19
}
```

### HTTP request

`POST {baseurl}/exhibitors/{exhibitorfairid}/profile/branch/{branch_group_id}/{locale}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| exhibitorfairid         | numeric | true    |         |
| branch_group_id         | numeric | true    |         |
| locale         | string | true    |         | possible values are "de_DE" and "en_GB"


## Unassign Branch from Exhibitor Profile

```shell
curl --location --request DELETE '{baseurl}/exhibitors/{exhibitorfairid}/profile/branch/{branch_group_id}/{locale}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {}
}
```

### HTTP request

`DELETE {baseurl}/exhibitors/{exhibitorfairid}/profile/branch/{branch_group_id}/{locale}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| exhibitorfairid         | numeric | true    |         |
| branch_group_id         | numeric | true    |         |
| locale         | string | true    |         | possible values are "de_DE" and "en_GB"


## Assign Keyword to Exhibitor Profile

```shell
curl --location --request POST '{baseurl}/exhibitors/{exhibitorfairid}/profile/keyword/{keyword_group_id}/{locale}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "id": 40
}
```

### HTTP request

`POST {baseurl}/exhibitors/{exhibitorfairid}/profile/keyword/{keyword_group_id}/{locale}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| exhibitorfairid         | numeric | true    |         |
| keyword_group_id         | numeric | true    |         |
| locale         | string | true    |         | possible values are "de_DE" and "en_GB"


## Unassign Keyword from Exhibitor Profile

```shell
curl --location --request DELETE '{baseurl}/exhibitors/{exhibitorfairid}/profile/keyword/{keyword_group_id}/{locale}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {}
}
```

### HTTP request

`DELETE {baseurl}/exhibitors/{exhibitorfairid}/profile/keyword/{keyword_group_id}/{locale}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| exhibitorfairid         | numeric | true    |         |
| keyword_group_id         | numeric | true    |         |
| locale         | string | true    |         | possible values are "de_DE" and "en_GB"


## Assign Brand to Exhibitor Profile

```shell
curl --location --request POST '{baseurl}/exhibitors/{exhibitorfairid}/profile/brand/{brand_group_id}/{locale}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {},
  "id": 40
}
```

### HTTP request

`POST {baseurl}/exhibitors/{exhibitorfairid}/profile/brand/{brand_group_id}/{locale}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| exhibitorfairid         | numeric | true    |         |
| brand_group_id         | numeric | true    |         |
| locale         | string | true    |         | possible values are "de_DE" and "en_GB"


## Unassign Brand from Exhibitor Profile

```shell
curl --location --request DELETE '{baseurl}/exhibitors/{exhibitorfairid}/profile/brand/{brand_group_id}/{locale}' \
--header 'X-API-Key: {API-Key}' \
--header 'Content-Type: application/json'
```
> The above command returns JSON structured like this:

```json
{
  "error": false,
  "error_message": {}
}
```

### HTTP request

`DELETE {baseurl}/exhibitors/{exhibitorfairid}/profile/brand/{brand_group_id}/{locale}`

### URL Parameters

| Parameter           | Type    | required | Default | Description |
| ------------------- | ------- | -------- | ------- | ----------- |
| exhibitorfairid         | numeric | true    |         |
| brand_group_id         | numeric | true    |         |
| locale         | string | true    |         | possible values are "de_DE" and "en_GB"
