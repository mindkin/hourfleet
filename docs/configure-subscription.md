---
layout: default
title: Configure Subscription.
---
# Subscription

Every car sharing network has a subscription model that determines pricing and limits on the network.

Your subscription plans is one of the plans seen at [Hourfleet](http://www.hourfleet.com).

> Note: You cannot configure this section of your configuration

~~~
"Subscription": { // This is the how the "Business" plan from http://www.hourfleet.com/#pricing is represented
	"Costs": {
		"PerLicense": 349,
		"PerCar": 10,
		"PerCarkit": 30,
		"PerUser": 5
	},
	"Limits": {
		"Cars": 50,
	},
	"Renewal": {
		"DayOfMonth": 5, // The day of the month when monthly cost are dated
	},
	"BeganDateUtc": "2018-05-04T12:00:00.00Z" // The date that subscription began
}
~~~

## Change Subscription

Head over to your [account dashboard](https://secure.hourfleet.com/user/dashboard), to cancel or change your subscription.