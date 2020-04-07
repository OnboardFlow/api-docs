# Getting Started

## Authentication
OnboardFlow uses API Keys to allow access to the API. You can find your API Key on the [API Settings](https://onboardflow.com/quick-launch/?path=/settings/api/) page, when logged into your OnboardFlow account.

The API Key needs to be included in ALL API requests to the server in a header that looks like the following:

`Authorization: Bearer e3c0c748fe9b55386eecc07c339ec4099a8b9b0e`

<aside class="notice">
Remember to replace <code>e3c0c748fe9b55386eecc07c339ec4099a8b9b0e</code> with your own API Key!
</aside>

## Rate Limits
API calls are rate limited to ensure that we are able to provide a consistent quality of service and availability to all of our users. The limits on total calls are illustrated below:

- **Free Plan** - 50 API calls/day
- **Launch Plan** - 1,000 API calls/day
- **Growth Plan** - 5,000 API calls/day
- **Expansion Plan** - 10,000 API calls/day

<aside class="notice">
Please note that we reserve the right to revoke API access if we believe it is being used irresponsibly.
</aside>

## Error Codes
The OnboardFlow API uses the following error codes:

Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request is invalid.
401 | Unauthorized -- Your API key is wrong.
404 | Not Found -- The specified record or endpoint could not be found.
405 | Method Not Allowed -- You tried to access an endpoint with an invalid method.
406 | Not Acceptable -- You requested a format that isn't json.
429 | Too Many Requests -- You're requesting too many records! Slow down!
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.
