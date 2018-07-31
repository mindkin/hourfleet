---
layout: default
title: Zapier Integration
---
# What is Zapier?

Zapier.com is really powerful, online platform for integrating web apps with each other. 

For example, you can use Zapier to have your emails forwarded to a Slack channel or to your Facebook account.
But that is not all. There are 100's of apps that you can connect together! 

## Hourfleet and Zapier

Hourfleet supports Zapier! so that means you can now get information about your car sharing network by connecting Hourfleet to your favourtie apps using Zapier zaps of your own!

> NOTE: At the moment, you can only get notified when the users of your network are notified of key events in Hourfleet, like when they join your network, or when they reserve or book a car.

This is how you can set Zapier.com up to notify you through one of your favourite apps, like Slack, etc.

>  NOTE: We are going to show you how you can get notified of all your user's Notifications in a Slack channel of your choice. 

But don't worry, even if you don't use Slack as your messaging app, and you use another app like Intercom or just Email, you can also get notified in the same way (as long as Zapier supports your app). 

Just follow the steps below, and select the app of your choice, the rest is very similar, and within no time you will be up and running.

# Creating a Zap

## Step 0: Login to Zapier

The first thing you need to do is create an account at [zapier.com](http://www.zapier.com), if you already have one, then just login.

Now, we are going to create a new Zap that connects Hourfleet to send user's notifications to your favorite messaging app. 

In this case we are going to show you connecting Hourfleet to Slack, and send all user's notifications to a specific Slack channel.

## Step 1: Accept the Invitation

Before you can select the Hourfleet app, you will need to click on this link, 

and accept this invitation: [Hourfleet Zap Invitation](https://zapier.com/developer/invite/95156/56d7bcf69452e20c2d857f6c96063846/)



> Note: You need to accept this invitation, because the Hourfleet Zap is not publicly available.

![Accept the Invitation](images/Zapier_1.PNG)

Just click "Accept Invite & Build A Zap"

## Step 2: Create The Zap

![Create The Zap](images/Zapier_2.PNG)



Just click "Create this Zap"

## Step 3: Latest Notifications

Just click "Save+Continue"

![Select Latest Notifications](images/Zapier_3.PNG)

## Step 4: Connect to Hourfleet

![Connect](images/Zapier_4.PNG)

Just click "Connect"

## Step 5: Provide Your Network Info

A new browser window will popup.

![Name Your Network](images/Zapier_5.PNG)

Here you are going to enter your network name, and some client credentials (Client ID and Client Secret)  that you must obtain for your network from Hourfleet support.

> Note: The name of your Hourfleet network is your subdomain of hourfleet.com. For example, if your Hourfleet network is at https://myrides.hourfleet.com, then your network name is `myrides`.

Obtain your Client ID, Client Secret from Hourfleet support, enter those, and your network name.

Then press "Yes, Continue".

## Step 6: Login

Then you will see this window, where you are going to need to login.

![Login To Hourfleet](images/Zapier_6.PNG)

Your username will be: `zapier.services.appuser`

Your password, you will obtain directly from Hourfleet support for your network.

Press "SIGN IN"

## Step 7: Authorize Zapier

You will be then prompted to authorize Zapier.com to have access to data from your network.

If you agree, just press "AUTHORIZE".

![Authorize](images/Zapier_7.PNG)

## Step 8: Test The Zap

The Zap is now created, and its time to test it is working.

![Test The Zap](images/Zapier_8.PNG)

Just click "Test"

You should then see a "Success" message

![Test Success](images/Zapier_9.PNG)

## Step 9: Integrate

The, just click "Save + Continue"

![Integrate](images/Zapier_10.PNG)

At this point your Zap is created, but it has nothing to integrate with yet.

You now need to setup the application that will receive data from Hourfleet.

> Note: In this example, we are going to set up the Zap to send Hourfleet notifications to a Slack channel you might have.

Just click "Continue", and you will pick an example to work with.

> Note: The examples you will be seeing are coming from your Hourfleet network.

![Test Success](images/Zapier_11.PNG)

Just click "Continue"

![Add A Step](images/Zapier_12.PNG)

On the left hand side, just click "Add a Step"

![Add A Step](images/Zapier_13.PNG)

And on the right type "Slack", and select Slack from the dropdown.

![Select Slack](images/Zapier_13.PNG)

Once Slack is selected you will select the "Send Channel Message"

![Send Channel Message](images/Zapier_14.PNG)

and click "Save + Continue"

![Connect To Slack](images/Zapier_15.PNG)

Just click "Connect"

A new browser window will pop up asking to to Authorize you to connect Zapier to your Slack Team

![Authorize Zapier](images/Zapier_16.PNG)

If you agree, just scroll to the bottom, and click "Authorize"

![Authorize Zapier](images/Zapier_17.PNG)

Just click "Save + Continue"

![Authorize Zapier](images/Zapier_18.PNG)

Now, you need to pick a slack "Channel" to send messages to, and the "Message Text" you want to send to Slack. All other fields are defaulted for you.

> Note: You are free to choose the format and data in the message. You can substitute any of the fields that are included in a user's notification into the message. Simply select them from the dropdown on the right side of the "Message Text" field.

In this example, we have chosen the general message: `[Resource ID] was notified of [Event ID] at [Event Created Date Utc]` where the `[value]` in the square brackets is selected from the drop down list.

> Note: You can see the Notifications section below for an explanation of all the fields that are available for all notifications. Note, that some fields are valid for only some notifications. The example above, will work for all notifications, but is too general for very much use.

Once, you are done with the Slack channel options, click the "Continue" button.

On the next page you can test the integration, by sending a notification to your Slack channel.

![Authorize Zapier](images/Zapier_19.PNG)

Just click "Send Test to Slack", and you should see a message appear instantly in your chosen slack channel, looking like this:

![Slack Notification](images/Zapier_20.PNG)

When you are done testing, just click the "Finish" button.

## Step 10: Turn On Your Zap

Then you will need to turn on your Zap to start working.

![Turn On Your Zap](images/Zapier_21.PNG)

Congratulations you have successfully integrated Slack with Hourfleet notifications!

## Notification Data

Hourfleet notifications provide the following fields, which can be selected (from the "Message Text" dropdown) when you setup your Zap.

>  Note: For a more detailed explanation of what notifications get sent out and when, check out the [Notifications Page](notifications.html)

## Field Names

Field | Meaning
--- | ---
ResourceId | The identifier of the resource [user]
ResourceType | Should always be "User"
EventId | The identifier of the notification (see table below for meaning)
EventType | Should always be "UserNotification"
EventCreatedDateUtc | The time the event was raised (UTC)
Description | Should always be the same as the EventId
Context.XXX | where XXX represents one of the *field* names in the table below, depending on the EventId
--- | ---

## Event Specific Fields

Event Id | Context Fields
--- | ---
4000 | User has invited themselves: *invitation.fullname, invitation.url*
4002 | User Account has been created: *user.fullname, user.url*
4010 | A password reset has been requested for an unknown email address: *email*
4011 | A password reset has been requested for a registered user: *email, url*
4012 | A password has been reset for a registered user: *email*
**101 - 109** | **Book Later requests:** *borrower.name, carowner.name, car.plate, car.name, car.photo, car.url, request.startdate, request.enddate, request.cancelleddate, request.cost.estimated, request.url, requests.url*
101 | (Borrower) Request has been drafted
102 | (Borrower) Request has been cancelled
103 | (Car Owner) Request has ben cancelled
104 | (Borrower) Request is now pending approval
105 | (Car Owner) Request is pending approval
106 | (Borrower) Request has been declined
107 | (Car Owner) Request has been declined
108 | (Borrower) Request has been expired (by System)
109 | (Car Owner) Request has been expired (by System)
**201 - 216** | **Book Later bookings:** *borrower.name, carowner.name, car.plate, car.name, car.photo, car.url, car.homelocation.description, car.homelocation.address, car.currentlocation.address, booking.startdate, booking.enddate, booking.cancelleddate, booking.returneddate, booking.useddate, booking.completeddate, booking.cost.usage, booking.cost.estimated, booking.url, bookings.url, booking.comments.borrowercancellation, booking.comments.borrowerreturned, booking.comments.carownercancellation, booking.comments.carownercompletion*
201 | (Borrower) Booking has been approved
202 | (Car Owner) Booking has been approved
203 | (Borrower) Booking has been cancelled
204 | (Car Owner) Booking has been cancelled
205 | (Borrower) Booking has been used (by Borrower)
206 | (Car Owner) Booking has been used (by Borrower)
207 | (Borrower) Booking has been returned
208 | (Car Owner) Booking has been returned
209 | (Borrower) Booking has been completed
210 | (Car Owner) Booking has been completed
211 | (Borrower) Booking will be starting soon
212 | (Car Owner) Booking will be starting soon
213 | (Borrower) Booking will be ending soon
214 | (Car Owner) Booking will be ending soon
215 | (Borrower) Booking has been extended
216 | (Car Owner) Booking has been extended
**221 - 234** | **Take Now takings:** *borrower.name, carowner.name, car.plate, car.name, car.photo, car.url, car.homelocation.description, car.homelocation.address, car.currentlocation.address, taking.reserveddate, taking.nouseexpireson, taking.noreturnexpireson, taking.cancelleddate, taking.useddate, taking.returneddate, taking.rejecteddate, taking.cost.usage, taking.url, takings.url*
221 | (Borrower) Taking has been reserved
222 | (Car Owner)  Taking has been reserved
223 | (Borrower)  Taking has been cancelled
224 | (Car Owner) Taking has been cancelled
225 | (Borrower) Taking has been expired (by System)
226 | (Car Owner) Taking has been expired (by System)
227 | (Borrower)  Taking has been used (by Borrower)
228 | (Car Owner) Taking has been used (by Borrower)
229 | (Borrower) Taking has been rejected
230 | (Car Owner) Taking has been rejected
231 | (Borrower) Taking will be ending soon
232 | (Car Owner) Taking will be ending soon
233 | (Borrower) Taking has been returned
234 | (Car Owner) Taking has been returned
**302 - 306** | **User verifications:** *user.name*
302 | User has become verified as a borrower
303 | User has become unverified as a borrower
304 | User has become verified as a carowner
305 | User has become unverified as a carowner
306 | User's email address has changed: *user.name, verification.url*
