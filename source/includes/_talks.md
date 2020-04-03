# Talks

## Get All Talks

```shell
curl "https://api.onboardflow.com/api/talks/"
  -X GET
  -H "Authorization: Token e3c0c748fe9b55386eecc07c339ec4099a8b9b0e"
```

> The above command returns JSON structured like this:

```json
{
    "count": 62,
    "next": "https://api.onboardflow.com/api/talks/?page=2",
    "previous": null,
    "results": [{
        "id": 636,
        "title": "3 common Writing & Publishing mistakes to avoid",
        "date": "2019-05-09T08:05:23.860467",
        "event": "https://api.onboardflow.com/api/events/24/",
        "speakers": [
            {
                "id": 809,
                "event": 24,
                "first_name": "Ursula",
                "last_name": "Cork",
                "company": "Company ABC",
                "company_title": "Head of Growth",
                "headshot": "https://api.onboardflow.com/media/uploads/image-17.png",
                "expert_creds": "As a Head of Growth I'm one of the best. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip .",
                "bio": "Prior to working at Cyberdyne Systems, I held senior positions acrosss a wide range of industries. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qu.",
                "is_active": true
            }
        ],
        "categories": [
            {
                "id": 554,
                "event": 24,
                "title": "PPC & Adwords",
                "description": null
            },
            {
                "id": 552,
                "event": 24,
                "title": "Personal Development",
                "description": null
            }
        ],
        "is_active": true,
        "is_featured": true
    },{
        "id": 636,
        "title": "3 common Writing & Publishing mistakes to avoid",
        "date": "2019-05-09T08:05:23.860467",
        "event": "https://api.onboardflow.com/api/events/24/",
        ...
    }]
}
```

This endpoint retrieves all Talks linked to your account.

### HTTP Request

`GET https://api.onboardflow.com/api/talks/`

### Query Parameters

Parameter | Description
--------- | ------- | -----------
event | The ID of the Event you want to filter the Talks list by
is_active | Set this to True to filter Talks that are currently marked as Active (or not)

## Get a Talk

```shell
curl "https://api.onboardflow.com/api/talks/1234/"
  -X GET
  -H "Authorization: Token e3c0c748fe9b55386eecc07c339ec4099a8b9b0e"
```

> The above command returns JSON structured like this:

```json
{
    "id": 636,
    "title": "3 common Writing & Publishing mistakes to avoid",
    "date": "2019-05-09T08:05:23.860467",
    "event": "https://api.onboardflow.com/api/events/24/",
    ...
}
```

This endpoint retrieves a Talk.

### HTTP Request

`GET https://api.onboardflow.com/api/talks/<ID>/`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Talk to retrieve
