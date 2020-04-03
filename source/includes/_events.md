# Events

## Get All Events

```shell
curl "https://api.onboardflow.com/api/events/"
  -X GET
  -H "Authorization: Token e3c0c748fe9b55386eecc07c339ec4099a8b9b0e"
```

> The above command returns JSON structured like this:

```json
{
    "count": 17,
    "next": "https://api.onboardflow.com/api/events/?page=2",
    "previous": null,
    "results":[{
        "id":"1234",
        "url":"https://api.onboardflow.com/api/events/1234/",
        "title":"Demo Event ABC",
        "event_url":"https://event.example.com",
        "first_talk_at":"2019-05-19T11:53:52",
        "last_talk_at":"2019-05-31T12:44:00",
        "is_live": true,
        "is_archived": false,
        "is_evergreen": false,
        "is_open_for_registrations": true
    },{
        "id":"1234",
        "url":"https://api.onboardflow.com:8000/api/events/1234/",
        "title":"Demo Event ABC",
        "event_url":"https://event.example.com",
        "first_talk_at":"2019-05-19T11:53:52",
        "last_talk_at":"2019-05-31T12:44:00"
        ...
    }]
}
```

This endpoint retrieves all Events linked to your account.

### HTTP Request

`GET https://api.onboardflow.com/api/events/`

### Query Parameters

Parameter | Description
--------- | ------- | -----------
is_live | Set this to True to filter Events that are currently marked as Live
is_archived | Set this to True to filter Events that are currently marked as Archived
is_evergreen | Set this to True to filter Events that are setup as Evergreen events
is_open_for_registrations | Set this to True to filter Events that are open for registrations

## Get an Event

```shell
curl "https://api.onboardflow.com/api/events/1234/"
  -X GET
  -H "Authorization: Token e3c0c748fe9b55386eecc07c339ec4099a8b9b0e"
```

> The above command returns JSON structured like this:

```json
{
    "id":"1234",
    "url":"https://api.onboardflow.com/api/events/1234/",
    "title":"Demo Event ABC",
    "event_url":"https://event.example.com",
    "first_talk_at":"2019-05-19T11:53:52",
    "last_talk_at":"2019-05-31T12:44:00",
    ...
}
```

This endpoint retrieves an event.

### HTTP Request

`GET https://api.onboardflow.com/api/events/<ID>/`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Event to retrieve

## Archive an Event


```shell
curl "https://api.onboardflow.com/api/events/1234/archive/"
  -X POST
  -H "Authorization: Token e3c0c748fe9b55386eecc07c339ec4099a8b9b0e"
```

> The above command returns JSON structured like this:

```json
{
    "id":"1234",
    "url":"https://api.onboardflow.com/api/events/1234/",
    "title":"Demo Event ABC",
    "event_url":"https://event.example.com",
    "first_talk_at":"2019-05-19T11:53:52",
    "last_talk_at":"2019-05-31T12:44:00",
    ...
}
```

This endpoint archives an Event.

<aside class="warning">Please note that archiving an Event will make it invisible to the public.</aside>


### HTTP Request

`POST https://api.onboardflow.com/api/events/<ID>/archive/`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Event to archive
