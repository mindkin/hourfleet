---
layout: default
title: Webhook Integration
---
# Webhook Events

Hourfleet is built on a REST API.

This means that anything and everything that you and your customers can do in the App, can also be done by any system on the internet, by calling HTTP methods. See [API](api.html) for more details.

As well as calling the various API's that Hourfleet has, Hourfleet can also notify you of certain events that occur during normal operation of your Car Share. Like when a new user joins your Car Share.

The mechanism by which this notification occurs is called 'Webhooks'.

## How do they work?

Hourfleet publishes certain events at certain times.

If you are interested in these events, you **subscribe** to these events, by simply defining the event you are interested in and a **URL** to call when that event occurs. This is know as a Webhook.

Once you have registered a subscriber to a webhook, Hourfleet will now call your URL (**publish**) with information about the specific event your subscribed to.

## How do you subscribe?

To subscribe to a webhook, you need to call an secure API, to set up a webhook subscription.

Before you do that, you will **need to know a URL** of some computer somewhere on the internet or cloud to receive that webhook notification. 

There are many of these endpoints (we call them) on the internet to receive these notifications. 

Some people have their own websites or web services that they can receive these notifications. Some people have built their own cloud apps that can receive these notifications for them (i.e. Azure Functions, or Amazon Lambdas, etc.).

For those not technically savvy, there are services out there (like [Zapier.com](www.zapier.com) and [Automate.io](www.automate.io)) that can receive the notification from Hourfleet, and relay that notification to another app that you might use (like Slack, Intercom, or email inbox, etc.) effectively turning Hourfleet into another source of notifications you already have in your business.

Either way, once you have a public URL to some site or service, you can register that URL as a subscriber to Hourfleet to receive a webhook notification.

OK, some technical details now. 

### What does a notification look like?

Let's assume that you have setup a URL (using one of the methods noted above) to receive your webhook from Hourfleet and your URL looks something like this: `https://myapp.com/webhooks/123456789`

AND you are interested in the event called: `carbooking_approve`

Then, once you subscribe with this URL, Hourfleet will send a notification to your URL, that would look something like this:

```
POST https://myapp.com/webhooks/123456789 HTTP/1.1
Accept: application/json
User-Agent: ServiceStack .NET Client 5.40
Accept-Encoding: gzip,deflate
X-Webhook-Delivery: 7a6224aad9c8400fb0a70b8a71262400
X-Webhook-Event: carbooking_approve
Content-Type: application/json
Host: myapp.com
Request-Id: |1f8d932d-4f0a0142f97a8306.
Content-Length: 26
Expect: 100-continue

{
	"Name":"carbooking_approve",
    "Id": "12345678-1234-1234-1234-1234-123456789012",
    "Reference": "ABCD1234",
    "CarId": "12345678-1234-1234-1234-1234-123456789012",
    "StartDateUtc": "2019-07-03T12:00:00.000Z",
    "EndDateUtc": "2019-07-04T06:00:00.000Z",
}
```

> Note: Hourfleet will always send you a HTTP POST request to your URL.

### Let's setup the webhook

Let's assume we are not technically savvy, and we have no websites or services out there on the internet of our own. 

We decide to create an account with [Zapier.com](www.zapier.com) and we want Zapier to relay the notification to a channel in our Slack workspace. We will assume that we use Slack for notifications in our business. 

>  Note: It does not have to be Slack, you could just as easily use any email inbox or any of 1000 apps that you already have in your business - you decide.

OK, so *conceptually*, this is what we will do (exact details omitted for brevity):

1. We will login to Zapier, and create a new Zap.
2. We will configure the Zap to receive a 'Webhook', and then send that notification as a message on a channel in a Slack workspace.
3. We start by configuring the 'Webhook' to 'catch' a notification, and Zapier will generate a URL for you.
4. We make a note of this URL. 
5. Next we need to train the Zap with a sample of what kind of notification it will get. (like the one above). We will use a common tool like [PostMan]([https://www.getpostman.com](https://www.getpostman.com/)) (or other API tool) to send the request above to the URL of our webhook in Zapier, to train the Zap.
6. Once the Zap receives the sample notification, it will decode the notification and learn about the various fields in the notification.
7. Then its time to configure the Zap to send the notification to Slack.
8. We now connect to our Slack workspace, and select a channel.
9. We configure the Zap to send a message to the channel with some content like 'Hi From Hourfleet' and we can also include any of the data in the notification that the Zap learned about. 

> Note: You can see from the sample notification above that you can do a lot with the data in the notification. You might also decide to send an email, or create a link in the Hourfleet App with some pieces of that data too.

### Let's subscribe to Hourfleet

Now that we have Zapier setup to handle our webhook all we now need to do is subscribe to receive the webhook events from Hourfleet.

TO BE CONTINUED