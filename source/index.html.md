---
title: OnboardFlow API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://onboardflow.com'>&copy; onboardflow.com</a>

includes:
  - customers
  - subscriptions
  - events
  - errors

search: true
---

# Introduction

Welcome to the [OnboardFlow](https://onboardflow.com) API.

We have language examples in Shell (with other platform examples coming soon)! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

OnboardFlow uses API Keys to allow access to the API. You can find your API Key on the [API Settings](https://onboardflow.com/quick-launch/?path=/settings/api/) page, when logged into your OnboardFlow account.

The API Key needs to be included in ALL API requests to the server in a header that looks like the following:

`Authorization: Bearer e3c0c748fe9b55386eecc07c339ec4099a8b9b0e`

<aside class="notice">
Remember to replace <code>e3c0c748fe9b55386eecc07c339ec4099a8b9b0e</code> with your own API Key!
</aside>
