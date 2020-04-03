# Customers

## Creating a Customer

```shell
curl "https://gateway.onboardflow.com/api/v1/customer/"
  -X POST
  -d '{"site_key":"f37F2PPh","event_date":1583020800,"user_id":"user_123XYZ","customer_id":"cus_123XYZ","customer_first_name":"Joe","customer_has_payment_method":true,"customer_email":"test@onboardflow.com"}'
  -H "Content-Type: application/json"
  -H "Authorization: Token e3c0c748fe9b55386eecc07c339ec4099a8b9b0e"
```

> The above command returns JSON structured like this:

```json
{
    "success": true,
    "data": {
        "id": 979924,
        "event_provider": "API",
        "site_user": {},
        "site_hash": "f37F2PPh",
        "session_id": "f37F2PPh-1585922303",
        "event_date": 1583020800000,
        "event_value": "1923c497cf0fc93ff63414795ec58c59d4ccab38",
        "event_type": "PROVIDER_EVENT",
        "event_meta": {
            "data": {
                "customer": {
                    "id": "cus_123XYZ",
                    "email": "test@onboardflow.com",
                    "user_id": "user_123XYZ",
                    "image_url": null,
                    "last_name": null,
                    "first_name": "Joe",
                    "has_payment_method": true
                }
            },
            "type": "CUSTOMER_CREATED",
            "created": 1583020800
        },
        "updated": 1585918703000,
        "created": 1585918703000
    }
}
```

This method should be called when a new customer is created (typically at the point at which they start a trial).


### HTTP Request

`POST https://gateway.onboardflow.com/api/v1/customer/`

### Data Parameters

Parameter | Description | Type | Required
--------- | ----------- | ---- | --------
site_key | The unique site key of the OnboardFlow site | String | Yes
event_date | The date the customer was created | DateTime (Unix Timestamp) | Yes
user_id | The unique ID of the user this customer record belongs to (typically this will be the ID of your internal user record) | String | Yes
customer_id | The unique ID of the customer being created (if you use a Payment Platform like Stripe this **must** be the exact same customer ID stored there) | String | Yes
customer_email | The email address of the customer being created | String | Yes
customer_first_name | The first name of the customer being created | String
customer_last_name | The last name of the customer being created | String
customer_image_url | The absolute URL of the customers profile image (if applicable) | String
customer_has_payment_method | A boolean indicating whether this customer has attached a payment method or not | Boolean | Yes


## Updating a Customer

```shell
curl "https://gateway.onboardflow.com/api/v1/customer/"
  -X PUT
  -d '{"site_key":"f37F2PPh","event_date":1583020800,"user_id":"user_123XYZ","customer_id":"cus_123XYZ","customer_first_name":"Joe","customer_has_payment_method":true,"customer_email":"test@onboardflow.com"}'
  -H "Content-Type: application/json"
  -H "Authorization: Token e3c0c748fe9b55386eecc07c339ec4099a8b9b0e"
```

> The above command returns JSON structured like this:

```json
{
    "success": true,
    "data": {
        "id": 979924,
        "event_provider": "API",
        "site_user": {},
        "site_hash": "f37F2PPh",
        "session_id": "f37F2PPh-1585922303",
        "event_date": 1583020800000,
        "event_value": "1923c497cf0fc93ff63414795ec58c59d4ccab38",
        "event_type": "PROVIDER_EVENT",
        "event_meta": {
            "data": {
                "customer": {
                    "id": "cus_123XYZ",
                    "email": "test@onboardflow.com",
                    "user_id": "user_123XYZ",
                    "image_url": null,
                    "last_name": null,
                    "first_name": "Joe",
                    "has_payment_method": true
                }
            },
            "type": "CUSTOMER_UPDATED",
            "created": 1583020800
        },
        "updated": 1585918703000,
        "created": 1585918703000
    }
}
```

This method should be called when a customer has updated their details (such as their name, email address, profile picture URL or when they've added a payment method).


### HTTP Request

`PUT https://gateway.onboardflow.com/api/v1/customer/`

### Data Parameters

Parameter | Description | Type | Required
--------- | ----------- | ---- | --------
site_key | The unique site key of the OnboardFlow site | String | Yes
event_date | The date the customer was updated | DateTime (Unix Timestamp) | Yes
user_id | The unique ID of the user this customer record belongs to (typically this will be the ID of your internal user record) | String | Yes
customer_id | The unique ID of the customer being updated (if you use a Payment Platform like Stripe this **must** be the exact same customer ID stored there) | String | Yes
customer_email | The email address of the customer being updated | String | Yes
customer_first_name | The first name of the customer being updated | String
customer_last_name | The last name of the customer being updated | String
customer_image_url | The absolute URL of the customers profile image (if applicable) | String
customer_has_payment_method | A boolean indicating whether this customer has attached a payment method or not | Boolean | Yes
