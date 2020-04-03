# Subscriptions

## Creating a Subscription

```shell
curl "https://gateway.onboardflow.com/api/v1/subscription/"
  -X POST
  -d '{"site_key":"f37F2PPh","event_date":1583020800,"subscription_name":"Pro","customer_id":"cus_123XYZ","subscription_id":"sub_123XYZ","subscription_value":49.99,"subscription_started_at":1583020800,"subscription_trial_start":1583020800,"subscription_trial_end":1583020800,"subscription_currency":"USD","subscription_status":"active","subscription_interval":"MONTH"}'
  -H "Content-Type: application/json"
  -H "Authorization: Token e3c0c748fe9b55386eecc07c339ec4099a8b9b0e"
```

> The above command returns JSON structured like this:

```json
{
    "success": true,
    "data": {
        "id": 979925,
        "event_provider": "API",
        "site_user": {},
        "session_id": "f37F2PPh-1585922793",
        "event_date": 1583020800000,
        "event_value": "1ec049ab69e84b58d7466816a791a6fd0fe36fa9",
        "event_type": "PROVIDER_EVENT",
        "event_meta": {
            "data": {
                "customer": {
                    "id": "cus_123XYZ"
                },
                "subscription": {
                    "id": "sub_123XYZ",
                    "name": "Pro",
                    "value": 49.99,
                    "status": "active",
                    "currency": "USD",
                    "interval": "MONTH",
                    "trial_end": 1583020800,
                    "product_id": null,
                    "started_at": 1583020800,
                    "trial_start": 1583020800
                }
            },
            "type": "SUBSCRIPTION_CREATED",
            "created": 1583020800
        },
        "updated": 1585919193000,
        "site_hash": "f37F2PPh",
        "created": 1585919193000
    }
}
```

This method should be called when a customer starts a new subscription (typically at the point at which they start a trial).


### HTTP Request

`POST https://gateway.onboardflow.com/api/v1/subscription/`

### Data Parameters

Parameter | Description | Type | Required
--------- | ----------- | ---- | --------
site_key | The unique site key of the OnboardFlow site | String | Yes
event_date | The date the subscription was created | DateTime (Unix Timestamp) | Yes
customer_id | The unique ID of the customer this subscription is linked to (if you use a Payment Platform like Stripe this **must** be the exact same customer ID stored there) | String | Yes
subscription_id | The unique ID of the subscription (if you use a Payment Platform like Stripe this **must** be the exact same subscription ID stored there) | String | Yes
subscription_name | The name of the subscription (usually this is the name of the plan, such as "Pro") | String | Yes
subscription_status | The status of the subscription (possible values are **trialing**, **active** and **cancelled**). | String | Yes
subscription_interval | What is the renewal cycle of this subscription? Possible values are **DAY**, **WEEK**, **MONTH** and **YEAR**  | String | Yes
subscription_value | The value of the subscription (this must take into account any discounts applied - if applicable) | Decimal | Yes
subscription_currency | The currency is this subscription charged in? This must be a valid [3 character ISO 4217 code](https://en.wikipedia.org/wiki/ISO_4217) | String | Yes
subscription_started_at | The date and time that the subscription was created | DateTime (Unix Timestamp) | Yes
subscription_trial_start | The date and time that the trial started (or is due to start) | DateTime (Unix Timestamp) | Yes
subscription_trial_end | The date and time that the trial ended (or is due to end) | DateTime (Unix Timestamp) | Yes


## Updating a Subscription

```shell
curl "https://gateway.onboardflow.com/api/v1/subscription/"
  -X PUT
  -d '{"site_key":"f37F2PPh","event_date":1583020800,"subscription_name":"Pro","customer_id":"cus_123XYZ","subscription_id":"sub_123XYZ","subscription_value":49.99,"subscription_started_at":1583020800,"subscription_trial_start":1583020800,"subscription_trial_end":1583020800,"subscription_currency":"USD","subscription_status":"active","subscription_interval":"MONTH"}'
  -H "Content-Type: application/json"
  -H "Authorization: Token e3c0c748fe9b55386eecc07c339ec4099a8b9b0e"
```

> The above command returns JSON structured like this:

```json
{
    "success": true,
    "data": {
        "id": 979925,
        "event_provider": "API",
        "site_user": {},
        "session_id": "f37F2PPh-1585922793",
        "event_date": 1583020800000,
        "event_value": "1ec049ab69e84b58d7466816a791a6fd0fe36fa9",
        "event_type": "PROVIDER_EVENT",
        "event_meta": {
            "data": {
                "customer": {
                    "id": "cus_123XYZ"
                },
                "subscription": {
                    "id": "sub_123XYZ",
                    "name": "Pro",
                    "value": 49.99,
                    "status": "active",
                    "currency": "USD",
                    "interval": "MONTH",
                    "trial_end": 1583020800,
                    "product_id": null,
                    "started_at": 1583020800,
                    "trial_start": 1583020800
                }
            },
            "type": "SUBSCRIPTION_UPDATED",
            "created": 1583020800
        },
        "updated": 1585919193000,
        "site_hash": "f37F2PPh",
        "created": 1585919193000
    }
}
```

This method should be called when a customer's subscription has changed (for example, this could be when its status changes or if they switch to another plan).


### HTTP Request

`PUT https://gateway.onboardflow.com/api/v1/subscription/`

### Data Parameters

Parameter | Description | Type | Required
--------- | ----------- | ---- | --------
site_key | The unique site key of the OnboardFlow site | String | Yes
event_date | The date the subscription was updated | DateTime (Unix Timestamp) | Yes
customer_id | The unique ID of the customer this subscription is linked to (if you use a Payment Platform like Stripe this **must** be the exact same customer ID stored there) | String | Yes
subscription_id | The unique ID of the subscription (if you use a Payment Platform like Stripe this **must** be the exact same subscription ID stored there) | String | Yes
subscription_name | The name of the subscription (usually this is the name of the plan, such as "Pro") | String | Yes
subscription_status | The status of the subscription (possible values are **trialing**, **active** and **cancelled**). | String | Yes
subscription_interval | What is the renewal cycle of this subscription? Possible values are **DAY**, **WEEK**, **MONTH** and **YEAR**  | String | Yes
subscription_value | The value of the subscription (this must take into account any discounts applied - if applicable) | Decimal | Yes
subscription_currency | The currency is this subscription charged in? This must be a valid [3 character ISO 4217 code](https://en.wikipedia.org/wiki/ISO_4217) | String | Yes
subscription_started_at | The date and time that the subscription was created | DateTime (Unix Timestamp) | Yes
subscription_trial_start | The date and time that the trial started (or is due to start) | DateTime (Unix Timestamp) | Yes
subscription_trial_end | The date and time that the trial ended (or is due to end) | DateTime (Unix Timestamp) | Yes
