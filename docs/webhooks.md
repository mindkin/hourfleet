---
layout: default
title: Webhook Integration
---
# Webhook Events

Hourfleet is built on a REST API.

This means that anything and everything that you and your customers can do in the App, can also be done by any system on the internet, by calling HTTP methods. See [API](api.html) for more details.

As well as calling the various API's that Hourfleet has, Hourfleet can also notify you of certain events that occur during normal operation of your Car Share. Like when a new user joins your Car Share.

The mechanism by which this notification occurs is called 'Webhooks'.

## What Webhook notifications are available?

The following table lists the available webhooks notifications that Hourfleet raises today.

| Category      | Notification Name   | Description                                |
| ------------- | ------------------- | ------------------------------------------ |
| UserAccounts  | useraccount_create  | A new user account was created             |
| Profiles      | profile_update      | A user's profile was updated               |
| Verifications | verification_update | A user's or car's verification was changed |
| Feedback      | feedback_update     | A user's or car's feedback was updated     |
|               | feedback_delete     | A user's or car's feedback was deleted     |
| Bookings      | carbooking_approve  | A booking for a car was approved           |
|               | carbooking_cancel   | The booking was cancelled                  |
|               | carbooking_use      | The booking was started (car was used)     |
|               | carbooking_extend   | The booking was extended longer or shorter |
|               | carbooking_return   | The booking was ended (car was returned)   |
|               | carbooking_complete | The booking was completed                  |

## How do they work?

Hourfleet publishes certain notification/events at certain times during its operation.

If you are interested in these events, you would **subscribe** to these events by simply defining: 1) the event you are interested in and 2) a **URL** to call when that event occurs. This is known as a Webhook (catching an event with a hook, on the web).

Once you have registered your subscriber URL to a webhook, Hourfleet will now call your URL (**publish**) with information about the specific event you subscribed to.

## How do you subscribe?

To subscribe to a webhook, you need to call an secure API, to set up a webhook subscription.

However, before you can do that, you will **need to know a URL** of some computer somewhere on the internet or in the cloud to receive that webhook notification. 

There are many of these URL endpoints (we call them) on the internet to receive these kinds of notifications. 

Some people have their own websites or web services that they can receive these notifications. Some people have built their own cloud apps that can receive these notifications for them (i.e. Azure Functions, or Amazon Lambdas, etc.).

For those not technically savvy, there are services out there (like [Zapier.com](www.zapier.com) and [Automate.io](www.automate.io)) that can receive the notification from Hourfleet, and relay that notification to another app that you might already use (like Slack, Intercom, or email inbox, etc.) effectively turning Hourfleet into another source of notifications you already have in your business.

Either way, once you have a public URL to some site or service, you can register that URL as a subscriber to Hourfleet to receive a webhook notification.

OK, some technical details now. 

### What does a notification look like?

Let's assume that you have setup a URL (using one of the methods noted above) to receive your webhook from Hourfleet and your URL looks something like this: `https://myapp.com/webhooks/123456789`

AND you are interested in the Hourfleet event called: `carbooking_approve`

Then, once you subscribe with this URL, Hourfleet will send a notification to your URL. The notification would look something like this (over the web):

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
5. Next we need to train the Zap with a sample of what kind of notification it will get. (like the one above). We will use a common tool like [PostMan]([https://www.getpostman.com](https://www.getpostman.com/)) (or other API tool like CURL) to send the request above to the URL of our webhook in Zapier, to train the Zap.
6. Once the Zap receives the sample notification, it will decode the notification and learn about the various fields in the notification.
7. Then its time to configure the Zap to send the notification to Slack.
8. We now connect to our Slack workspace, and select a channel.
9. We configure the Zap to send a message to the channel with some content like 'Hi From Hourfleet' and we can also include any of the data in the notification that the Zap learned about. 

> Note: You can see from the sample notification above that you can do a lot with the data in the notification. You might also decide to send an email, or create a link in the Hourfleet App with some pieces of that data too.

### Let's subscribe to Hourfleet

Now that we have Zapier setup to handle our webhook all we now need to do is subscribe to receive the webhook events from Hourfleet.

For this step we will need a tool like [PostMan]([https://www.getpostman.com](https://www.getpostman.com/)) (or other API tool like CURL) in order to subscribe to webhooks in Hourfleet.

We are going to use POSTMAN to subscribe to an Hourfleet webhook, using the URL we made in the previous steps, and also with the name of a notification we are interested in from the table at the top of this page.

For this example, lets use `https://myapp.com/webhooks/123456789` (that we got from our Zap) for the URL and `carbooking_approve` for the notification name (from table above).

In POSTMAN, we need to configure the 'Authorization' to use 'OAuth 2' to obtain a token, that we will then need to use to call Hourfleet.

We configure POSTMAN to use a `Grant Type` of 'Authorization Code', and we define these properties:

- AuthURL: `https://yourcarshare.hourfleet.com:4432/api/oauth/auth`
- TokenURL: `https://yourcarshare.hourfleet.com:4432/api/oauth/token`
- ClientID: `BD3C4D5F-867C-42B1-8155-02E0A5050CE1`
- ClientSecret: \<you obtain this from Hourfleet Support Team>
- Scope: `https://www.mindkin.co.nz/auth/useraccount.profile`

Now, you will get a popup window asking for a login. You response with:

- username: `zapier.services.appuser`
- Password: \<you obtain this from Hourfleet Support Team>

Postman now has an 'access_token' that you can use to make a request to any Hourfleet API.

Now configure the following request in POSTMAN:

* Verb: `POST`

* URL: https://yourcarshare.hourfleet.com:4431/api/webhooks/subscriptions

* Body: `raw`, 'JSON (application/json)'

* Body Content: `{"name":"My Notification","events":["carbooking_approve"],"config":{"url":"https://myapp.com/webhooks/123456789",}}`

Now 'Send' the request.

You should get a HTTP 200 response.

Your webhook is now all setup and ready to be fired by Hourfleet.
