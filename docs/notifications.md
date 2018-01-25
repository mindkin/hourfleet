---
layout: default
title: Notifications
---

[TOC]

# Notifications

For key events in the system, users will receive SMS and Email notifications. For example when they join your network, or when they book a car.
Here you can see an example of all the SMS and Email notifications that get sent and at which key events they happen.
If you would like to be notified of these events at the same time as your customers you can do this through Zapier Integration. To find out how to do this visit the [Zapier Integration](zapier.html) page.



## Accounts

### Invitation (User)

This notification is sent to the *User* when they request an invitation to create an account on your network.

Substitutions Available:

`invitation.fullname`
`invitation.url`

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Account Created (User)

This notification is sent to the *User* when they created an account on your network.

Substitutions Available:

`user.fullname`
`user.url`

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Attempted Password Reset (User)

This notification is sent to the *Email Address* used when a *User* requests a password reset on an email address that is not registered on your network.

Substitutions Available:

`email`

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Password Reset Request (User)

This notification is sent to the *Email Address* used when a *User* requests a password reset on an email address that is registered on your network.

Substitutions Available:

`email`
`url`

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Password Reset (User)

This notification is sent to the *User* when they successfully reset their account password.

Substitutions Available:

`email`

**Email**

`IMAGE`

**SMS**

`IMAGE`



## Verifications

### Verified Borrower (User)

This notification is sent to the *User* when they have been verified for all the requirements needed to borrow a car on your network.

Substitutions Available:

`user`

**Email**

`IMAGE`

**SMS**

`IMAGE`



## Booking Requests

Substitutions Available:

`borrower.name`
`carowner.name`
`car.plate`
`car.name`
`car.photo`
`car.url`
`request.startdate`
`request.enddate`
`request.cancelleddate`
`request.cost.estimated`
`request.url`
`requests.url`


### Draft Request (Borrower)

This notification is sent when a borrower makes a booking request and is not fully verified.

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Pending Request (Borrower)

This notification is sent to the *Borrower* when a booking request is pending.

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Pending Request (Car Owner)

This notification is sent to the *Car Owner* when a booking request is pending.

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Cancelled Request (Borrower)

This notification is sent to the *Borrower* when they cancel a booking request.

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Cancelled Request (Car Owner)

This notification is sent to the *Car Owner* when a *Borrower* cancels a booking request.

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Declined Request (Borrower)

This notification is sent to the *Borrower* when their booking request has been declined.

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Declined Request (Car Owner)

This notification is sent to the *Car Owner* when they decline a booking request.

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Expired Request (Borrower)

This notification is sent to the *Borrower* when their booking request has expired.

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Expired Request (Car Owner)

This notification is sent to the *Car Owner* when a booking request has expired.

**Email**

`IMAGE`

**SMS**

`IMAGE`



## 'Book Later' Bookings

Substitutions Available:

`borrower.name`
`carowner.name`
`car.plate`
`car.name`
`car.photo`
`car.url`
`car.homelocation.description`
`car.homelocation.address`
`car.currentlocation.address`
`booking.startdate`
`booking.enddate`
`booking.cancelleddate`
`booking.returneddate`
`booking.useddate`
`booking.completeddate`
`booking.cost.usage`
`booking.cost.estimated`
`booking.url`
`bookings.url`
`booking.comments.borrowercancellation`
`booking.comments.borrowerreturned`
`booking.comments.carownercancellation`
`booking.comments.carownercompletion`

### Approved Request (Borrower)

This notification is sent to the *Borrower* when their booking request has been approved and is now a booking.

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Approved Request (Car Owner)

This notification is sent to the *Car Owner* when they approve a booking request and is now a booking.

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Cancelled Booking (Borrower)

This notification is sent to the *Car Owner* when a booking has been cancelled.

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Cancelled Booking (Car Owner)

This notification is sent to the *Car Owner* when a booking has been cancelled.

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Due to Begin Booking (Borrower)

This notification is sent to the *Borrower* about their upcoming booking.

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Due to Begin Booking (Car Owner)

This notification is sent to the *Car Owner* about the upcoming booking of their vehicle.

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Booking Begun (Borrower)

This notification is sent to the *Borrower* once their booking has been started.

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Booking Begun (Car Owner)

This notification is sent to the *Car Owner* when the *Borrower* has started their booking.

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Booking Returned (Borrower)

This notification is sent to the *Borrower* when they have returned the vehicle and finished their booking.

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Booking Returned (Car Owner)

This notification is sent to the *Car Owner* when the *Borrower* has returned their vehicle and finished their booking.

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Booking Completed (Borrower)

This notification is sent to the *Borrower* when the *Car Owner* completes the booking or the system auto-completes it.

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Booking Completed (Car Owner)

This notification is sent to the *Car Owner* when they complete a booking or the system has auto-completed one.

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Booking Due to End (Borrower)

This notification is sent to the *Borrower* when their booking is due to end soon.

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Booking Due to End (Car Owner)

This notification is sent to the *Car Owner* when the booking of their vehicle is due to end soon.

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Booking Extended (Borrower)

This notification is sent to the *Borrower* after they have extended their booking period.

**Email**

`IMAGE`

**SMS**

`IMAGE`

### Booking Extended (Car Owner)

This notification is sent to the *Car Owner* after the *Borrower* has extended their booking period.

**Email**

`IMAGE`

**SMS**

`IMAGE`
