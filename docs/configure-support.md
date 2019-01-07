---
layout: default
title: Configure Support.
---
# Support

These settings are displayed in various places around the web app that reference support/assistance for your customers. It also includes the ability to use third party support service like Google Analytics and live chat widgets. Hourfleet generates a support page for your web app using some of these details that helps provide guidance for your users. You can choose to link to your own external support page (see [Navigation Configuration](configure.html#Navigation)).

~~~
	"Support": { 
		"Guidance": "If there is an issue with a car during your booking we  recommend first contacting the owner. You can find their contact information under the owner section of your booking",
		"Social": {
			"Facebook": {
				"Url": "https://www.facebook.com/yourcompany/"
			},
			"Twitter": {
				"Url": "https://twitter.com/yourcompany"
			},
			"LinkedIn": {
				"Url": "https://www.linkedin.com/company/yourcompany"
			},
			"Instagram": {
				"Url": "https://www.instagram.com/yourcompany"
			},
			"Blog": {
				"Url": "https://yourcompany.wordpress.com"
			},
			"Other": {
				"Url": ""
			}
		},
		"Company": {
			"Name": "Your Company Limited",
			"PhoneNumber": "0800-555-1212",
			"Email": "support@yourcompany.co.nz",
			"Address": {
				"Street1": "99 Your Way",
				"Street2": "",
				"Town": "Yourville",
				"Jurisdiction": "New Zealand"
			}
		},
		"Insurer": {
			"Guidance": "To lodge a claim please contact our insurer directly. You will need to provide them with a completed insurance claim form.",
			"Name": "Acme Insurance",
			"ClaimForm": {
				"Title": "",
				"Url": "http://www.yourcompanys.com/Docs/insurance_claim_form.pdf"
			},
			"PhoneNumber": "0800-555-1212",
			"Email": "claims@acmeinsurance.co.nz"
		},
		"LiveChat": {
			"FreshDesk": {
				"ApiKey": "xxxxx",
				"Settings": "BASE64ENCODEDSTRING"
			},
			"Intercom": {
				"ApiKey": "xxxxx",
			},
		},
		"Analytics": {
			"Google" : {
				"TrackingId": "UA-XXXXX-Y"
			}
		}
	},
~~~



An example of the Support page that is generated for you can be seen here:

![Support Page](images/SupportPage.png)

## LiveChat

This section defines the LiveChat widgets that Hourfleet supports. Currently, FreshDesk.com or Intercom.io.
You will need to sign-up for an account with either of these providers. 

You cannot configure to have LiveChat for both, chose one or the other or neither.

### FreshDesk.com
Once you have signed up and selected a plan that includes LiveChat, you will need to provide your: 'ApiKey' and 'Settings', which can be obtained from the 'Admin' console of your Freshdesk subscription.

* Login to your Freshdesk site: https://yourname.freshdesk.com
* Click on the 'LiveChat' icon

![](images/FreshDesk-Console-LiveChat.png)

* Make sure Live Chat is 'enabled'
* Make sure your app is enabled.
* Click on the 'Edit' button to the right of your app
* Click on the 'Widget Code' tab
* In the javascript they provide, you need to find and extract the value of the URL that looks like this: 'https://xxxxxxxxxxx.cloudfront.net'. The xxxxxxxx part is your 'ApiKey'
* Now, find the value of the 'window.livechat_setting='xxxxxxxxxxxxxxxxxxxxxxxxx....'. The large blob of text between the quotations marks is the value of your 'Settings' (not including the quotation marks).

### Intercom.io

Once you have signed up and selected a plan that includes Intercom 'Acquire', you need to provide your 'ApiKey', which can be obtained form the 'App Settings' console of your Intercom subscription.

* Login to Intercom at: https://app.intercom.io
* Click on your avatar (bottom left-hand corner of page) and click 'App Settings'

![](images/Intercom-Console-AppSettings.png)

* Click on the 'API Keys' menu (to the left)
* The 'APP ID" is the value of your 'ApiKey'

## Google Analytics

If you wish to track site usage using Google Analytics, you can do that by providing your 'Tracking Id' found in the 'Administration -> Property Settings' page of your Google Analytics configuration page, for your Google account.

> Note: Hourfleet will include the standard javascript that [Google Analytics instructs](https://developers.google.com/analytics/devguides/collection/analyticsjs/) to add to every web page, configured with your 'Tracking Id'.
