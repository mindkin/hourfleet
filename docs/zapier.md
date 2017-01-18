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

**NOTE: At the moment, you can only get notified when the users of your network are notified of key events in the system, like when they join your network, or when they reserve or book a car.**

This is how you can set Zapier.com up to notify you through one of your favourite apps, like Slack, etc.

NOTE: We are going to show you how you can get notified of all your user's Notifications in a Slack channel of your choice. 
But don't worry, even if you don't use Slack as your messaging app, and you use another app like Intercom or just Email, you can also get notified in the same way (as long as Zapier supports your app). 

Just follow the steps below, and select the app of your choice, the rest is very similar, and within no time you will be up and running.

# Creating a Zap

## Step 1: Create a new Zap

The first thing you need to do is create an account at [zapier.com](www.zapier.com), if you already have one, then just login.

Now, we are going to create a new Zap that connects Hourfleet to send user's notifications to your favorite messaging app. 

In this case we are going to show you connecting Hourfleet to Slack, and send all user's notifications to a specific Slack channel.

![Create a New Zap](images/Zapier_1.PNG)

## Step 2: Select the Hourfleet App

Before you can select the Hourfleet app, you will need to click on this link, and complete the invitation: [Hourfleet App Invitation](https://zapier.com/developer/invite/51326/fccef634d394c7efcb8248feb6ddb64c/)

You need to complete this invitation, because the Hourfleet App is not publically available or listed to just anyone.

** NOTE: Once you have been invited, you will need to search for the "hourfleet" app to select it.**
(Hourfleet is a private and privileged application and you will not find it listed in the Zapier directory without a search for it, and certainly not without completing the invitation to use it.)

![Select the Hourfleet App](images/Zapier_2.PNG)

Simply click on the app.

## Step 3: Latest Notifications

Click the "Latest Notifications", and press "Save+Continue"

![Select Latest Notifications](images/Zapier_3.PNG)

## Step 4: Your Account name

Next, you will be asked for the name of your Hourfleet account.

![Your Account Name](images/Zapier_4.PNG)

This is the name of your Hourfleet tenancy. (i.e. roamride)

## Step 5: Login to Hourfleet

Next you will need to login to Hourfleet.
You are going to use your account "zapier.services.appuser", and the password that you were provided for this account when you created your tenancy.

![Login](images/Zapier_5.PNG)

## Step 6: Authorize Zapier

Next, you will need to authorize that Zapier.com can have permission to access your data on your behalf.

![Authorize](images/Zapier_6.PNG)

If you are happy with this, then click the "Authorize" button

## Step 7: Complete App Registration

Now that Zapier is setup to access user notifications with your account, you should see the following messages to confirm and test that everything is setup correctly.

![Summary](images/Zapier_7.PNG)
![Test](images/Zapier_8.PNG)

## Step 8: Configure Receiving App

Now, we need to setup the app that is going to receive the user notification. IN this case, we are going to show you setting up a Slack channel, but you can choose any app that Zapier supports to do this.

Select "Slack" from the list of apps, or search for your favourite app here.

![Select Receiving App](images/Zapier_9.PNG)

## Step 9: Select Slack Channel

With Slack, we want to send the notification to a specific channel. So we need to select the "Send Channel Message" Action.

![Select Action](images/Zapier_10.PNG)

## Step 10: Connect to Slack Account

If you have not already logged into Zapier with your Slack account, you do that now, and press "Save+Continue"

![Connect to Slack](images/Zapier_11.PNG)

## Step 11: Setup the Receiving App

For a slack notification, you need to tell Zapier which channel to use, and who is going to be seen to send the user's notification (i.e. whether to use a bot or not).

![Setup Receiving App](images/Zapier_12.PNG)

Then, probably the most important part is to define the "Message Text" that is going to be posted to your slack channel.

In this section, you can create a message and substitute any of the fields that are included in a user's notification into the message. Simply select them from the dropdown on the right side of the "Message Text" field.

Finally save your changes. And Zapier will send a test notification to your slack channel so that you can see the result.
You can always come back and change the settings to get what you need.

# Notifications

Notification provide this data:

    | Meaning
--- | ---
ResourceId | The identifier of the resource [user]
ResourceType | Should always be "User"
EventId | The identifier of the notification (see table below for meaning)
EventType | Should always be "UserNotification"
EventCreatedDateUtc | The time the event was raised (UTC)
Description | Should always be the same as the EventId
Context.XXX | where XXX represents one of the field names in the table below, depending on the EventId:

Event Id | Context Fields
--- | ---
4000 | User has invited themselves: *invitation.fullname, invitation.url*
4002 | User Account has been created: *user.fullname, user.url*
101 - 109 | Book Later requests: *borrower.name, carowner.name, car.plate, car.name, car.photo, car.url, request.startdate, request.enddate, request.cancelleddate, request.cost.estimated, request.url, requests.url*
101 | (Borrower) Request has been drafted
102 | (Borrower) Request has been cancelled
103 | (Car Owner) Request has ben cancelled
104 | (Borrower) Request is now pending approval
105 | (Car Owner) Request is pending approval
106 | (Borrower) Request has been declined
107 | (Car Owner) Request has been declined
108 | (Borrower) Request has been expired (by System)
109 | (Car Owner) Request has been expired (by System)
201 - 216 | Book Later bookings: *borrower.name, carowner.name, car.plate, car.name, car.photo, car.url, car.homelocation.description, car.homelocation.address, car.currentlocation.address, booking.startdate, booking.enddate, booking.cancelleddate, booking.returneddate, booking.useddate, booking.completeddate, booking.cost.usage, booking.cost.estimated, booking.url, bookings.url, booking.comments.borrowercancellation, booking.comments.borrowerreturned, booking.comments.carownercancellation, booking.comments.carownercompletion*
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
221 - 234 | Take Now takings: *borrower.name, carowner.name, car.plate, car.name, car.photo, car.url, car.homelocation.description, car.homelocation.address, car.currentlocation.address, taking.reserveddate, taking.nouseexpireson, taking.noreturnexpireson, taking.cancelleddate, taking.useddate, taking.returneddate, taking.rejecteddate, taking.cost.usage, taking.url, takings.url*
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
302 - 305 | User verifications: *user.name*
302 | User has become verified as a borrower
303 | User has become unverified as a borrower
304 | User has become verified as a carowner
305 | User has become unverified as a carowner
306 | User's email address has changed: *user.name, verification.url*
