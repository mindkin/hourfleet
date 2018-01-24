---
layout: default
title: Notifications
---
# Notifications

For key events in the system, users will recieve SMS and Email notifications. For example when they join your network, or when they reserve or book a car.
Here you can see an example of all the sms and email notifications that get sent and at which key events they happen.
If you would like to be notified of these events at the same time as your customers you can do this with Zapier Integration.


## Events

###User Verifications
**302 - 305** | **User verifications:** *user.name*
302 | User has become verified as a borrower
303 | User has become unverified as a borrower
304 | User has become verified as a carowner
305 | User has become unverified as a carowner
306 | User's email address has changed: *user.name, verification.url*

4000 | User has invited themselves: *invitation.fullname, invitation.url*
4002 | User Account has been created: *user.fullname, user.url*
4010 | A password reset has been requested for an unknown email address: *email*
4011 | A password reset has been requested for a registered user: *email, url*
4012 | A password has been reset for a registered user: *email*

###Booking Requests
**101 - 109** | **Book Later requests:** *borrower.name, carowner.name, car.plate, car.name, car.photo, car.url, request.startdate, request.enddate, request.cancelleddate, request.cost.estimated, request.url, requests.url*
101 | (Borrower) Request has been drafted
102 | (Borrower) Request has been cancelled
103 | (Car Owner) Request has ben cancelled
104 | (Borrower) Request is now pending approval
105 | (Car Owner) Request is pending approval
106 | (Borrower) Request has been declined
107 | (Car Owner) Request has been declined
108 | (Borrower) Request has been expired (by System)
109 | (Car Owner) Request has been expired (by System

###Book Later Bookings
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

###Take Now Bookings
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
