---
layout: default
title: Integrations
---
# Supported Integrations
Hourfleet depends on one mandatory third-party integration ([Stripe](http://stripe.com)), and supports a number of optional online services. 

In all cases, configuring this integration requires you to: 
1. Sign in to your account with the integraton provider
1. Create the relevant API keys
1. Send those API keys to Hourfleet Support on your private Slack channel, or by email to `support@hourfleet.com` and then delete any reference to these keys from your computer. Remember to check your email's 'Sent Items' too.

## Stripe

You will need a Stripe account to properly operate an Hourfleet Car Share. 

If you don't alread have a Stripe account you'll need to [register](https://dashboard.stripe.com/register) one. If you need to register we recommend you take some time [to learn about Stripe](https://stripe.com/customers). 

The next step is to configure your Hourfleet Car Share with your Stripe API keys. 

This enables your Car Share to bill your customers when they use your car sharing service, and it enables your customers to capture their credit card information in your Car Share. Without which, they cannot setup their credit cards.

**IMPORTANT:** If you do not configure yiour Hourfleet Car Share correctly with your Stripe information, your customers will experience errors when they try to register their user accounts, and provide credit card information.

From your Stripe Dashboard, click `Developers`, then `API Keys`, and then `+ Create restricted key`

![](images/RestrictedKey2.png)  

Give the key the name `Hourfleet`. All your permissions should be showing `None`. Go through and check each  of the permissions shown as needing `Read and write` as shown below.

![](images/RestrictedKeyA.PNG) 

.. and ..  

![](images/RestrictedKeyB.PNG) 


Now click `Create key`

![](images/RestrictedKey2.png)  

Now it's time to colect the two keys that Hourfleet needs. First save the `Publishable key`. Then in the Restricted API key panel by Hourfleet, click `Reveal live key token` and the `Restricted key` will be displayed. It's restrcted for a reason - don't leave this lying around!

The `Publishable Key` will begin `pk_live_`, and the `Restricted Key` will begin `rk_live_`  

Send both those keys to Hourfleet Support on your private Slack channel, or by email to `support@hourfleet.com`. If applicable delete this email from your Sent Items folder too.

**Important**: Your relationship with Stripe is governed by your acceptance of their Terms of Service. We are unable to manage any aspect of your relationship with Stripe, or to advocate for you. Other than initiating charges to your customers as covered by our Terms of Service, we are unable to act for or on your behalf.

## LiveChat Widgets

In the Hourfleet App you can choose to display a LiveChat widget to offer live support to your customers.
At present, Hourfleet supports: FReshDesk and Intercom.

If you wish to add LiveChat from one of these services, please register an account with those services first. Then return here and follow the guidance below to integrate it into the Hourfleet App.

### LiveChat using Freshdesk.com (Optional)

Once you have signed up and selected a Freshdesk plan that includes LiveChat, you will need to provide your: 'ApiKey' and 'Settings', which can be obtained from the 'Admin' console of your Freshdesk subscription.

* Login to your Freshdesk site: https://yourname.freshdesk.com
* Click on the 'LiveChat' icon

![](images/FreshDesk-Console-LiveChat.png)

* Make sure Live Chat is 'enabled'
* Make sure your app is enabled.
* Click on the 'Edit' button to the right of your app
* Click on the 'Widget Code' tab
* In the javascript they provide, you need to find and extract the value of the URL that looks like this: 'https://xxxxxxxxxxx.cloudfront.net'. The xxxxxxxx part is your 'ApiKey'
* Now, find the value of the 'window.livechat_setting='xxxxxxxxxxxxxxxxxxxxxxxxx....'. The large blob of text between the quotations marks is the value of your 'Settings' (not including the quotation marks).

Send that key to Hourfleet Support on your private Slack channel, or by email to `support@hourfleet.com`. If applicable delete this email from your Sent Items folder too.

### LiveChat using Intercom.com (Optional)

Once you have signed up and selected a plan that includes Intercom 'Acquire', you need to provide your 'ApiKey', which can be obtained form the 'App Settings' console of your Intercom subscription.

* Login to Intercom at: https://app.intercom.io
* Click on your avatar (bottom left-hand corner of page) and click 'App Settings'

![](images/Intercom-Console-AppSettings.png)

* Click on the 'API Keys' menu (to the left)
* The 'APP ID" is the value of your 'ApiKey'

Send that key to Hourfleet Support on your private Slack channel, or by email to `support@hourfleet.com`. If applicable delete this email from your Sent Items folder too.

## Google Analytics (Optional)

If you wish to track site usage using Google Analytics, you can do that by providing your 'Tracking Id' found in the 'Administration -> Property Settings' page of your Google Analytics configuration page, for your Google account.

Send that Tracking Id to Hourfleet Support on your private Slack channel, or by email to `support@hourfleet.com`. If applicable delete this email from your Sent Items folder too.
