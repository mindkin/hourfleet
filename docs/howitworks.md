---
layout: default
title: How Things Work
---
#  How Things Work

Typically, your car sharing business is already going to have its own website and landing pages where you attract, advertise and track and convert your customers. 

Your website is likely to have information such as: Pricing Plans, Fees, Terms of Service, Privacy Policy, Customer Case Studies, Company Info and other information, typically in multiple pages (URL's). For the purposes of this documentation, we will refer to these pages of your website as the 'Landing Pages' of your car sharing business.

As a tenant on the Hourfleet platform, you will get a branded web app of your own that will look and feel like your website and landing pages. But this web app will have a different URL than your landing page. 

Your Hourfleet web app will be hosted for you at: https://yourcompany.hourfleet.com. 

### Table of Contents
- [Web App Integration](#web-app-integration)
  - [Customer Support Page](#customer-support-page)
- [Operational Management](#operational-management)
  - [Activity Monitoring](#activity-monitoring)
  - [Verifications](#verifications)
  - [Billing/Remittance](#billing/remittance)
  - [Carkit Management](#carkit-management)
- [Listing Cars](#listing-cars)
- [Borrowing Cars](#borrowing-cars)
  - [Usage Models](#usage-models)
- [Cloud Hosted Environment](#cloud-hosted-environment)

## Web App Integration

The Hourfleet web app is where your customers will manage their account with your car sharing network, manage their profile, and they will book/reserve and list cars there too. Basically, they do everything with cars on the web app.

The Hourfleet web app however will not be able to provide things to your customers like: your Terms of Service or Privacy policy, etc.. But instead, it will provide the ability to link users to those things on the landing pages of your own website, from various links in the Hourfleet web app.

The list of links in the web app that link to your website are:

* Home (Landing Page) - the user is returned here after logging out of the web app.
* Terms Of Service - the user is directed here to read your terms of service, generally when being asked to accept them.
* Privacy Policy - the user is directed here to read your privacy policy in places where infromation is taken from them.
* How It Works - the user is directed here to read about how your network works, and reads any information specific to how your network works.
* About - you can provide information about about your business or people
* Contact - you can provide information for contacting the people and services of your business  
* Fees - you can provide pricing and fees information
* Documentation - A place you can provide additional documentation, like forms, etc.

An example of the links in the Hourfleet web app can be seen in the footer section of the web app. It looks something like this:

![Page Links](images/Footer.png)

All of the links in the list above (except the 'Home' link) can be optionally configured, and hidden if not configured. See [You Configure](http://docs.hourfleet.com/youconfigure.html) for the technical details.

> Note: The 'Home' link must always be defined. All other links are optional.

### Customer Support Page

In addition to all the pages above, the Hourfleet web app offers you a ready made pre-formatted 'Support' page that displays support contact information and insurance information for your customers to use when they need assistance using the web app, or assistance when borrowing cars out on the road.

This support page is pre-formatted with information you provide in your tenancy configuration. An example of the support page can be seen here.

![Support Page](images/SupportPage.png)

## Operational Management

The Hourfleet web app includes a number of administration pages to help you operate and monitor your car sharing network. These administration pages are only available to priviledged users of the Hourfleet web app.

You can control and nominate one or more people in your business to manage your business in the administratiokn pages of the web app. Those people will log into the web app just like your customers, but they will have access to a number of tools that your customers would not see and not have access to.

<<screenshot fo the operations menu>>

These tools include the ability to:

* Monitor activity on your network, such as when new users register, when users create bookings, etc.
* Manage your user accounts and their verifications.
* Manage the charging and remitance of your customers.
* Configure, manage and test your physical keyless devices.

> Note: Hourfleet is constantly striving to provide its customers with the most relevant tools for managing your network. So please let us know what is missing and we will try to provide you the best experience for managing your network.

### Activity Monitoring

As your customers do various things on your network, such as: create new accounts, verify their credentials, book and use cars, etc. Those events create 'alerts' that can be viewed. You can keep up to date with these alerts in the Operational Dashboard.

Alerts have varying levels: Urgent, Important, OfInterest, Security and Noise. You can filter this level to focus on what is important to you. You can also dismiss any specific alert to keep the list shorter.

If you want to receive your alerts in other apps, such as: Slack, Intercom, Trello, email etc. you can setup Zapier.com to relay the alert to your favorite apps. See [Zapier Integration](zapier.html) for more details on how to set that up.

<<screenshot of the alert panel>>

> Note: The display of alerts is being improved overtime as we learn more about how operators use them, and what alerts are most important to operators.

### Verifications

In a car sharing network people must trust each other to borrow and rent vehicles. The car owners must at least trust the network that borrowers are legally qualified to drive their cars, and borrowers must at least trust car owners that cars are legally safe to drive. Everyone on the network, borrowers and car owners will want trust to some degree that everyone involved is legitimate, and the network has limited that kind of risk as much as it can. 
Since many people may be using the network or specific car for the first time, trust is going to be need inferred from the other party's network membership and from the feeeback and rating given by others on the network about them.

For these reasons, and others, all Hourfleet networks support two things: Verifications and Ratings and Reviews.

Rating and reviews are well understood today. People using a service (i.e a car sharing service) get the option to rate and give open and honest feedback about their experience of the service, and of the people providing it to them. They typically do this in the hope that it helps or benefits others coming after them make either a good purchase or a poor purchase choice. Today, with many online services, this is a common experience, and it is expected whenever its difficult to establish initial trust between the individuals participating in the service (i.e. between the owner of the car, and the person using it temporarily). Your car sharing network is no different, where many people may not have very extensive experience with the other people providing them service. Particularly in the P2P networks, feedback and ratings are critical to making it succeed.


In terms of qualifying people and qualifying the minimum level of  service they provide (i.e. renting their car), ratings and feedback are not enough to define a minimum level of quality. Every car, car owner, and borrower needs to be verified as well.

Every user and every car on your network will have its own set of verifications. Depending whether you are a borrower, car owner or car, your set of verifications will differ. For example, a borrower must have, at least: a verified email adddress, a verified phone number, a verified credit card and a verified drivers license. A car owner must have at least: a verified email address, a verififed phone number and a verified bank account. A car must have: a verified license plate and a verified certificate of road worthiness.

Whenever a person or car is registered on your network, there is an ongoing process which they must go through continuously to complete and maintain their list of verifications. The must get and stay fully verified to continue to use the service. Until they are fully verified, their use of the service will be limited. For example, until a borrower is fully verified they will not be able to actually use a car. Similarly, until a car is fully verified, borrowers will be unable to book or rent that car.

Some of these verifications, like: car license plate, are not going to change over time. Some of these verifications, like: email address will only change if the user manually changes their email address. Some of these verifications will automatically change over time, like a drivers license, or credit card, when it expires.

Some of these verifications can be automatically verified by the Hourfleet system, such as a person's email address or their credit card, etc. However, some of these verifications, like a drivers license, and possibly a car's license plate, can only be manually verified by the Network Operator, typically by way of some other government service/system.

The network operator, your business, is therefore responsible for monitoring and managing these verifications for the users of the network. 

The Hourfleet web app provides the tools from the Operations Dashboard to monitor and manage verifications of all users and cars as things change. i.e. as a new user registers and provides all the information to get fully verified.

> Note: Monitoring and manging verifications is a mandatory activity for network operators, and must be performed continuously, as users and cars on their network can change status over time.

<<screenshots of verifying users>>


### Billing/Remittance

When a borrower of a car on your network has used and returned the car, they will need to be charged for that usage. Charges are always charged to a verified credit card.

The owner of the car in a P2P business will also need to be remitted an amount for the use of their car. In a B2C business, the operator is the car owner, and will also need to be remitted for the use of the car. Remittance is always paid to a verified bank account.

While usage charges and remittance can be calculated and could technically be performed automatically by Hourfleet, doing this automatically for every usage is not always desirable for a network operator. For example, if one of your borrowers has had a very poor experience within your network, you may decide as the network operator to discount or waive usage charges for them on a case by case basis. 

For these kinds of reasons, all charing and remitting in Hourfleet is performed manually after the fact, by the network operator. All remittance and charging is performed after a booking is closed out and settled by the car owner, and is added to a backlog that can be managed by operators.

> Note: the amount to charge a borrower, and the amount to remit the car owner, is always automatically calculated for you to make the act of reconciling the charges and remittance as easy as possible.

The Hourfleet web app has all the tools to manually view all charges and to manually bill the user.

<<Screenshot of billing a user for a booking>> 

#### Usage Charges and Settlements

Each hourfleet tenancy decides its own financial model for how its car sharing network charges borrowers and remits its car owners. The financial model in all cases can be quite complex depending on your commerical arrangements with: your customers (borrowers and car owners) and your insurerance company.

> Note: In a B2C car sharing network, the network operator is typically (but not always) the owner of the cars on the network (a car owner could also be a 3rd party), whereas in a P2P car sharing network, other members of the network typically (but not always) own the cars. Car ownership should be understood to be separate from whether the network is B2C or P2P.

Refering to the [network operator configuration](youconfigure.html#business-models) you can see the various options you have in the financial model of your car sharing network. Notice that your car sharing network can support either a B2C model, or a P2P model, not both. 

In a B2C model, a network operator typically owns the cars, and is remitted all the usage charges, less any payouts it must make to an insurer.

In a P2P model, a network operator typically shares the revenue generated by borrowers renting out the cars of the car owners, less any insurance payouts.

In either model, insurance payouts can be a combination of a fix fee, plus some share rate, or none of these things.

> Special Case: A network, like a trial network, promotional network of wholey subscription based network, may not want to charge borrowers anything for using any of the cars on the network, and therefore there will be no revenue from usage at all.

This B2C and P2P parts of the financial model determine the fixed revenue of the business. The variable amount of revenue generated by actual usage of the cars by borrowers is determined by the 'Usage Model' or each car. Both B2C and P2P models support both 'Scheduled' and 'Immediate' usage models.

In a 'Scheduled' model, where cars are 'booked' ahead of time for a known period of time, revenue depends on the hourly/daily/weekly prices set by the car owner. Actual revenue depends on how much (to nearest minute) of usage the car is used by the borrower within the schedule. Late fees and fixed penalties are mandatory for schedule infractions, depending on tolerances set by the network.

In an 'Immediate'model, where cars are not booked, but used on demand (if available), for an unknown period of time, revenue also depends on hourly/daily/weekly prices set by the car owner. Revenue depends on how much (to nearest minute) of usage the car is used by the borrower. Late fees and penalties are only used in cases of gross over usage depending on maximums set by network operator. 

In either model, there are also booking fees per usage that can be applied, and various timescales that can be defined controlling late fees and fixed penalties.

Together, both the 'Ownership' and 'Usage' models provide the financial models for actual charges and remittance for both borrower and car owner.

> Note: In the Hourfleet web app, when it comes time to calculate any charges or remit any settlements, a full breakdown of the amounts will be presented to the user.

<<screenshot of charges for a user at the end of a booking, with latet fees>>
<<screenshot of remittance for a car owner when billing>>


### Carkit Management 

If the cars on your network support keyless access by smartphone, each car will need to have a carkit installed within it. The carkit is paired with the car after it is installed physcially in the car.

> Note: the installation of carkits is not covered here. But once physcially installed into a car, the carkit will need to be removed and re-configured to be physcially installed into another car.

Typically, after installing the carkit physcially into the car, the installer of the carkit will need to pair the carkit with the car in the Hourfleet web app. They would do that in the 'Manage Carkits' page of the web app.

<<screenshot of pairing a carkit with car in ops panel>>
 
To pair a carkit with a car in your network you will need to know the following information:

* The SIMM identifier of the carkit. This is printed on teh actual carkit.

Once the carkit is paired with a car on your network, you can manually operate various functions to test the car, including Locking and Unlocking the car.

> Note: if one of your customers get in trouble while using a car, this is the same function you can use to help them Lock/Unlock their car.

<<screenshot of the carkit control panel>>

## Listing Cars

In order for a car to be used on your network, the car needs to be 'listed' on the network by one of the current users on the network. 

The listing of cars for P2P networks is usually done by the owner of the car. For B2C networks, cars are listed by the network operator, or perhaps some 3rd party.

Once a car is registered, there is quite a rigorous process by the car owner to get it verified so that it appears in search results for borrowers to find. Generally, the following must be configured before a car can be borrowed.

1. The car must be fully registered, and have all the basic information filled out. e.g. Year, Make, Model, Location, Photo, Prices, Usage Model, etc.
2. The car must have details of a Certificate of Road Worthiness, and this must be verified by the operator.
3. The car owner must be fully verified as a car owner. Requires the owner to have a verified: Email, Phone, BankAccount.
4. The car must have any future availability set for it by the car owner.
5. The car must not be set as 'Offline'.

Only when the above requirements are met, will the car appear in the search results (and on the map) as 'Available'. Otherwise it appears in the search results (and on the map) as 'Coming Soon', and cannot be booked or used.

> Note: At any time, any of the car's verifications and any of the car owners' verifications may become unverified (some are time based, some are action based - see [Verifications](#verifications) for more details), at which point the car becomes unavailable, and dissapears from the list of 'available' cars in search results.

For car owners (P2P or B2C), it is imperative that they get themselves and their cars verified, and stay verified if the cars are to be used.

> Note: It is imperative that operators stay on top of any manual verifications that would block cars from being fully verified at any time.

## Borrowing Cars

To borrow a car on any network the borrower must be registered on that network, and they must be fully verified.

To be fully verified a user must first:

1. Create an account on the network, by providing an email and name, and accept the terms of service of the network.
2. Verify their email address (an email is sent to them for this purpose)
3. Verify their phone number. This is currently done manually by the newtork operator.
4. Provide their drivers license in their profile. The network operator must verify this manually.
5. Provide their credit card details in their profile. This is automatically verified when they register their card.

Only when the user has completed teh above checklist will they be able to actually use any car on the network. 

In the meantime, as long as the user has created an account on the network, they will be able to make requests to book scheduled' cars, but will still need to get verified before it is time to use the car, otherwise the booking will expire.

> Note: if at any time the user becomes unverified, the ability to use a car is restricted until they restore their verifications.

### Using a Car

There are two usage models that govern how borrowing a car works on your network:

* Scheduled - (a.k.a Book Later) In this model, cars must be booked in advance, and are generally booked for a known amount of time. The borower shows up at the car and uses it at (or very close to) the time they booked it. The car owner gets the option to approve requests manually ahead of time, and can choose the best request to fit their needs (i.e. times, durations, costs, reputations etc.). Or they can auto-approve the requests and requests are approved as long as the car is available (first in first served).
* Immediate - (a.k.a Take Now) In this model, there are no bookings, and no approvals. Borrowers walk up to a car wherever it is and reserve it right away. They have a short period of time to actually use the car (i.e. start the rental), before it becomes available to others to reserve and use. The borower uses the car as long as they like (within max limits set by the network operator), and returns it when they no longer need it.

Any network can support both models at the same time, and every car determines which model it uses at any one time. The car owner can change the usage model anytime (except under certain circumstances). For example, a car can be setup for the 'Scheduled' usage model and borrowers can make bookings and use the car. Some time later, the car owner may decide to switch to the 'Immediate'usage model, and now borrowers can take the car immediately anytime its not already in use, no bookings required. 

> Note: A car owner cannot swap from 'Immediate'to 'Scheduled' when there are future booking already scheduled.

#### Scheduled Bookings

Bookings work like most people imagine they should. 

* First, a borrower makes a 'Request' to rent a car, for a specific period of time. They get the chance to ask a question of the car owner, for example: "I'd like to take my child with me on this trip, would you be able to include one of your baby car seats in the car please".
* A booking 'Request' is sent to the car owner to approve. (Unless the car owner has configured the car for auto-approval, in which case, the request is immediately approved as long as the car is available). 
* The car owner, when they get to it, looks at all their booking requests and considers which to approve, or which to decline. If there are multiple requests for the car at the same time, the car owner will compare the requests to see which works out best for them, approve one or none, and decline the others.
* If a car owner does not approve or decline a request up until (e.g 15mins) before the booking should actually start, then the request is automatically expired. 
* If a request is approved, then the borrower is notified, the schedule, home location, and prices are locked in for the borrower.
* Before the booking is due to start, the borrower has the option to request an extension to the schedule, but only if the car is available for that whole time.
* Before the booking actually starts, the borrower will use the app to find the car (on a map). 
* The borrower can actually start the booking early (within e.g 15mins before scheduled start), if the car is at the home location, and the previous booking is done.
* The borrower starts the booking (in the app), they open the car and they drive it away. They will have up until (e.g 15mins) before the scheduled end of the booking to actually start the booking and use the car, otherwise the booking will expire, assuming the borrower was a "no show".
* After use, the borrower must return the car to its agreed home location, or close by. In some cases, like urban on-street parking, it may not actually be possible to return the car to its designated home location (as the park may be occupied), so the borrower must make an effort to park it as close as possible. Ultimately, the car owner will decide whether the final location is acceptable to them.
* The borrower completes the booking (in the app) and locks the car. They give feedback about their experience of the car to the car owner.
* If the borrower returns the car late, and its more than (e.g 5mins) past scheduled end time, then a one time late fee penalty is applied (e.g $50), and for every minute late there is an hourly late fee applied (e.g $1/min).
* After the borrower returns the car (in the app) the owner can review the final booking, and must accept the final situation of the car. They can choose to give feedback at this point. If the car owner does not complete the booking within (e.g 3 days) the booking is auto-completed on their behalf.
* Finally, once the booking is completed, the borrower is charged all usage/late fees, and the car owner is remitted their earnings.

> Note: In the process above, all example times and costs given are defaults, and are configurable for your specific network. These settings are all defined in your configuration for the 'Scheduled'. usage model. See the [configuration](#youconfigure.html#business-model) for more details.

#### Immediate Takings


#### Keyless Access

For cars that support Keyless access, borrowers walk up to where the car is located, and from their smartphone, in the web app, they start their 'booking' (Scheduled) or 'rental' (Immediate) in the app. They then Unlock the car from their smartphone. Once inside the car, there will be a 'Start' button on the dashboard to start the car and drive it away.

While they have the car, the app will track them on a map, that shows them where to return the car when they are done. The app also keeps track of the usage time, costs, and fees for them.

When they are done, and they return the car, they will complete the booking/rental in the app, ensuring the car is returned to the correct location, and it is left locked. They can review their charges and give feedback at that point.

Later, the borrower can view their past booking/rental and they will be billed by the network operator.

The car owner is notified of all the steps of the booking/rental process. At the end, they must confirm the completion of the booking/rental, where they can see a summary or their earnings.

> The car owner is strongly encouraged to be involved in the completion process, and monitor their car usage, but it is optional. If they don't take any actions within set periods of time, the booking will be auto-completed for them, so that billing and other processes can proceed.

During the whole process, there is an opportunity for the borrower and car owner to communicate directly, on any issues.

#### Key Exchange

For cars that are NOT Keyless access, the borrower and car owner will make arrangements to exchange car keys. 

<<describe the process in more detail>>


## Cloud Hosted Environment

Your Hourfleet web app, all web API's, all associated network infrastructure and databases are all hosted in the cloud on Microsoft Azure, in a region geographically close to your business.

The network infrastructure is managed by Hourfleet, you don't need to worry about managing any of that.

All the data that is created or collected from your customers or your business is stored in secure data repositories and backed up for you automatically in the cloud.

Backups are run once a day, and stored for 30 days.

> Note: all data that is created or collected from your customers or your business belongs to your business, and can be obtained at any time. Please contact Hourfleet support for assistance.

