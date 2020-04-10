# Events

## Logging a UX Event

```shell
curl "https://gateway.onboardflow.com/api/v1/tracker/event/"
  -X POST
  -d '{"s":"f37F2PPh","site_user":{"id":"user_123XYZ","customer_id":"cus_123XYZ","custom_properties":{"projects_created":7}},"event":"PAGE_VIEW","value":"/manage/settings/","meta":{"title":"App Settings Page"}}'
  -H "Content-Type: application/json"
  -H "Authorization: Token e3c0c748fe9b55386eecc07c339ec4099a8b9b0e"
```

> The above command returns JSON structured like this:

```json
{
    "success": true,
    "data": {
        "event_date": 1585920768000,
        "event_provider": "JSTRACKER",
        "event_value": "/manage/settings/",
        "id": 979927,
        "site_hash": "f37F2PPh",
        "event_type": "PAGE_VIEW",
        "event_meta": {
            "title": "App Settings Page"
        },
        "site_user": {
            "id": "user_123XYZ",
            "customer_id": "cus_123XYZ",
            "custom_properties": {
                "projects_created": 7
            }
        },
        "created": 1585920768000,
        "updated": 1585920768000
    }
}
```

Once installed, our [JavaScript Tracker](https://onboardflow.com/quick-launch/?path=/settings/tracker/install/) will automatically log page views as well as any custom UX events you've setup. However, sometimes it can be useful to log custom UX events via a simple API call. It might also be required to post UX events via the API if you are unable to install the JavaScript Tracker on your app (i.e. if you run a Mobile or Desktop app, rather than a Web app).


### HTTP Request

`POST https://gateway.onboardflow.com/api/v1/tracker/event/`

### Data Parameters

Parameter | Description | Type | Required
--------- | ----------- | ---- | --------
s | The unique site key of the OnboardFlow site | String | Yes
event | The type of UX event you are logging. Possible options are **PAGE_VIEW**, **CLICK** or **CUSTOM** | String | Yes
event_date | The date the UX event took place | DateTime (Unix Timestamp) | Yes
site_user | A dictionary containing details of the user that should be linked to this UX event. At a minimum this should contain an id and customer_id (i.e. {"id": "user_123XYZ", "customer_id":"cus_123XYZ"}). [Read more about setting User and Customer ID's here](https://help.onboardflow.com/article/10-identify-your-user). | Dictionary | Yes
value | If this is a page view event, this should be the URL of the page being viewed. If it's a click it could be the ID of the element or video being watched. No matter what the event is being logged here, this should basically be a value that helps us group similar events in the future (i.e. the URL of the page, ID of the video being watched, class or ID of the button being clicked etc).  | String | Yes
meta | If logging a page view or perhaps a video view, then you can set additional properties here about the event. I.e. setting the title would be achieved by setting this to {"title":"App Settings Page"}. Please note that currently, only 'title' is officially supported. | Dictionary | Yes
