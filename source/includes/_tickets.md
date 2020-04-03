# Tickets

## Get All Tickets

```shell
curl "https://api.onboardflow.com/api/tickets/"
  -X GET
  -H "Authorization: Token e3c0c748fe9b55386eecc07c339ec4099a8b9b0e"
```

> The above command returns JSON structured like this:

```json
{
    "count": 2,
    "next": null,
    "previous": null,
    "results": [
        {
            "id": 2,
            "url": "https://api.onboardflow.com/api/tickets/30/",
            "name": "Premium Access",
            "event_id": 1,
            "event_name": "Test",
            "created_at": "2019-12-06T16:38:30.024291"
        },
        {
            "id": 1,
            "url": "https://api.onboardflow.com/api/tickets/1/",
            "name": "Free Access",
            "event_id": 1,
            "event_name": "Test",
            "created_at": "2019-10-28T15:45:23.699053"
        }
    ]
}
```

This endpoint retrieves all Tickets linked to your account.

### HTTP Request

`GET https://api.onboardflow.com/api/tickets/`

### Query Parameters

Parameter | Description
--------- | ------- | -----------
event | The ID of the event you want to filter the list of Tickets by

## Get a Ticket

```shell
curl "https://api.onboardflow.com/api/tickets/1/"
  -X GET
  -H "Authorization: Token e3c0c748fe9b55386eecc07c339ec4099a8b9b0e"
```

> The above command returns JSON structured like this:

```json
{
    "id": 1,
    "url": "http://api.onboardflow.com/api/tickets/1/",
    "name": "Free Access",
    "event_id": 1,
    "event_name": "Test",
    "created_at": "2019-10-28T15:45:23.699053"
}
```

This endpoint retrieves a single Ticket.

### HTTP Request

`GET https://api.onboardflow.com/api/tickets/<ID>/`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Ticket to retrieve
