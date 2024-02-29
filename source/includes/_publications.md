# Publications

## Get online medias

```shell
curl --location --request GET '{baseurl}/publications/online/' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "online_media": [
		{
            "language": "de_DE",
            "logo_preview": "sandbox.profairs2.tom.webcontact.de/downloads/get.cfm?component=com_publikation&method=getAusstellerMesseWebsite&fieldNameFile=logo_vorschau&fieldNameFileName=logo_name&fieldNameFileMimeType=logo_mimetype&aussteller_messen_id=7&type=attachment",
            "description": "Eintrag Onlinemedien (Ihr Text)",
            "video_url": "",
            "logo": "sandbox.profairs2.tom.webcontact.de/downloads/get.cfm?component=com_publikation&method=getAusstellerMesseWebsite&fieldNameFile=logo&fieldNameFileName=logo_name&fieldNameFileMimeType=logo_mimetype&aussteller_messen_id=7&type=attachment",
            "logo_name": "cms-640x640.jpg",
            "contactid": "",
            "logo_mimetype": "image/jpeg",
            "exhibitor_fairid": 7,
            "company_description": ""
        }
	]
}
```

### HTTP request

`GET {baseurl}/publications/online/`

### Query Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
fairid | numeric | false | |

## Get online media

```shell
curl --location --request GET '{baseurl}/publications/online/{exhibitor_fairid}' \
--header 'X-API-Key: {API-Key}' \
```

> The above command returns JSON structured like this:

```json
{
    "error": false,
    "online_media": [
        {
            "language": "de_DE",
            "logo_preview": "sandbox.profairs2.tom.webcontact.de/downloads/get.cfm?component=com_publikation&method=getAusstellerMesseWebsite&fieldNameFile=logo_vorschau&fieldNameFileName=logo_name&fieldNameFileMimeType=logo_mimetype&aussteller_messen_id=766&type=attachment",
            "description": "ProFairs ist eine webbasierte Eventmanagement-Software für Messen, die die Kommunikation mit den Ausstellern vereinfacht. Das war's.",
            "video_url": "",
            "logo": "sandbox.profairs2.tom.webcontact.de/downloads/get.cfm?component=com_publikation&method=getAusstellerMesseWebsite&fieldNameFile=logo&fieldNameFileName=logo_name&fieldNameFileMimeType=logo_mimetype&aussteller_messen_id=766&type=attachment",
            "logo_name": "logo webcontact.jpg",
            "contactid": "",
            "logo_mimetype": "image/jpeg",
            "exhibitor_fairid": 766,
            "company_description": ""
        }
    ]
}
```

### HTTP request

`GET {baseurl}/publications/online/{exhibitor_fairid}`

### URL Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitor_fairid | numeric | true | |

## Create online media

```shell
curl --location --request POST '{baseurl}/publications/online/' \
--header 'X-API-Key: {API-Key}' \
--form 'file=@"{file_path}"' \
--form 'file_preview=@"{file_path}"' \
--form 'exhibitor_fairid="1337"' \
--form 'language="de_DE"' \
--form 'description="Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod"' \
--form 'company_description="Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod"' \
--form 'file_name="{file_name}"' \
--form 'file_mimetype="{file_mimetype}"' \
--form 'video_url="https://..."' \
--form 'contactid="1337"'
```

> The above command returns JSON structured like this:

```json
{
    "language": "de_DE",
    "error": false,
    "exhibitor_fairid": "1337"
}
```

### HTTP request

`POST {baseurl}/publications/online/`

### Parameters

Parameter | Type | required | Default | Description
--------- | ---- | -------- | ------- | -----------
exhibitor_fairid | numeric | true | |
language | string | true | |
description | string | true | |
company_description | string | true | |
logo | binary | true | |
logo_name | string | false | |
video_url | string | false | |
contactid | numeric | true | |
