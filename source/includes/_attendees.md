# Attendees

## Get All Attendees

```shell
curl "https://api.onboardflow.com/api/attendees/"
  -X GET
  -H "Authorization: Token e3c0c748fe9b55386eecc07c339ec4099a8b9b0e"
```

> The above command returns JSON structured like this:

```json
{
    "count": 294,
    "next": "https://api.onboardflow.com/api/attendees/?page=2",
    "previous": null,
    "results":[{
        "id": 246,
        "url": "https://api.onboardflow.com/api/attendees/246/",
        "email": "joe@bloggs.com",
        "name": "Joe Bloggs",
        "event_id": 24,
        "event_name": "Demo Summit ABC",
        "created_at": "2019-04-18T19:51:24.073422"
    },{
        "id": 246,
        "url": "https://api.onboardflow.com/api/attendees/246/",
        "email": "joe@bloggs.com",
        "name": "Joe Bloggs",
        "event_id": 24,
        "event_name": "Demo Summit ABC",
        "created_at": "2019-04-18T19:51:24.073422"
        ...
    }]
}
```

This endpoint retrieves all Attendees linked to your account.

### HTTP Request

`GET https://api.onboardflow.com/api/attendees/`

### Query Parameters

Parameter | Description
--------- | ------- | -----------
event | The ID of the event you want to filter the list of Attendees by

## Get an Attendee

```shell
curl "https://api.onboardflow.com/api/attendees/1234/"
  -X GET
  -H "Authorization: Token e3c0c748fe9b55386eecc07c339ec4099a8b9b0e"
```

> The above command returns JSON structured like this:

```json
{
    "id": 246,
    "url": "https://api.onboardflow.com/api/attendees/246/",
    "email": "joe@bloggs.com",
    "name": "Joe Bloggs",
    "event_id": 24,
    "event_name": "Demo Summit ABC",
    "created_at": "2019-04-18T19:51:24.073422"
    ...
}
```

This endpoint retrieves an Attendee.

### HTTP Request

`GET https://api.onboardflow.com/api/attendees/<ID>/`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the Attendee to retrieve

## Add an Attendee


```shell
curl "https://api.onboardflow.com/api/attendees/"
  -X POST
  -d '{"event":1234, "email":"joe@bloggs.com", "name":"Joe Bloggs"}'
  -H "Content-Type: application/json"
  -H "Authorization: Token e3c0c748fe9b55386eecc07c339ec4099a8b9b0e"
```

> The above command returns JSON structured like this:

```json
{
    "id": 246,
    "url": "https://api.onboardflow.com/api/attendees/246/",
    "email": "joe@bloggs.com",
    "name": "Joe Bloggs",
    "event_id": 24,
    "event_name": "Demo Summit ABC",
    "created_at": "2019-04-18T19:51:24.073422"
    ...
}
```

This endpoint creates a new Attendee for the Event passed.

<aside class="warning">Please note that once the Attendee has been added, you may still need to add them to Talks. It is also assumed that any Attendee added, has accepted your terms and conditions and has agreed to be added to this Event and emailed regarding the event (with reminders and notifications relating to the talks they are booked into).</aside>


### HTTP Request

`POST https://api.onboardflow.com/api/attendees/`

### URL Parameters

Parameter | Required | Description
--------- | ----------- | -----------
event | Yes | The ID of the Event you want to add this attendee to
email | Yes | The email address of the Attendee you're adding
name | Yes | The name of the Attendee you're adding
ticket_id | No | The ID of the Ticket you want to add for this attendee
