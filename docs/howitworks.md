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
  - [Account Verification](#account-verification)
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

As your customers do various things on your netowrk, such as: create new accounts, verify their credentials, book and use cars, etc. Those events create 'alerts' that can be viewed. You can keep up to date with these alerts in the Operational Dashboard.

Alerts have varying levels: Urgent, Important, OfInterest, Security and Noise. You can filter this level to focus on what is important to you. You can also dismiss any specific alert to keep the list shorter.

If you want to receive your alerts in other apps, such as: Slack, Intercom, Trello, email etc. you can setup Zapier.com to relay the alert to your favorite apps. See [Zapier Integration](zapier.html) for more details on how to set that up.

<<screenshot of the alert panel>>

> Note: The display of alerts is being improved overtime as we learn more about how operators use them, and what alerts are most important to operators.

### Verifications

In a car sharing network people must trust each other to borrow and rent vehicles. The car owners must trust that borrowers are legally qualified to drive their cars, and borrowers must trust car owners that cars are legally safe to drive, etc. Since these people may be using a specific service or specific car for the first time, trust is going to be need inferred from their network membership and from the feeeback and rating given by others on the network.

For these reasons, all Hourfleet networks support two things: Verifications and Ratings and Reviews.
  
Every car, car owner, and borrower has their own verifications. For exmaple, a borrower must have at least a verified email adddress, a verified phone number and a verified drivers license. A car must have a verified license plate and a verified certificate of road worthiness, etc.

Whenever a person or car is registered on your network, there is an ongoing process which they must go through to complete and maintain a list of verifications. The must get and stay fully verified to continue to use the service. Until they are fully verified, their use of the system will be limited. For example, until a borrower is fully verified they will not be able to actually use a car. Also, until a car is fully verified, borrowers will be unable to book or rent that car.

Some of these verifications, like: car license plate, are unlikely to change over time. Some of these verifications, like: email address will only change if the user manually changes their email address. Some of these verifications will automatically change over time, like a drivers license, when it expires.

Some of these verifications can be automatically verified by the Hourfleet system, such as a person's email address and credit cards. However, some of these verifications, like a drivers license, and possibly a car's license plate, can only be manually verified by the Network Operator, typically by way of some other government service/system.

The Network operator is responsible for monitoring and managing these verifications for the users of the network. 

The Hourfleet web app provides the tools from the Operations Dashboard to monitor and manage verifications of all users and cars as things change. i.e. as a new user registeres and provides all the information to get fully verified.

> Note: Monitoring and manging verifications is a mandatory activity for network operators, and must be performed continuously, as users and cars on their network can change status over time.

<<screenshots of verifying users>>


### Billing/Remittance

When a borrower of a car on your network has used and returned the car, they will need to be charged for that usage. Charges are always charged to a verified credit card.

The owner of the car in a P2P business will also need to be remmitted an amount for the use of their car. In a B2C business, the operator is the car owner, and will also need to be remitted for the use of the car. Remittance is always paid to a verified bank account.

While remittance can be calculated and can be performed automatically by Hourfleet, the automatic charging of usage and late charges is not always desirable for the network operator. For example, if one of your users has had a poor experience, you may want to discount or waive usage charges for them on a case by case basis. For this reason, all billing in Hourfleet is performed manually after the fact, by the network operator. 

> Note: the amount to charge a user is always automatically calculated for the network operator.
 

The Hourfleet web app has all the tools to manually view all charges and to manually bill the user.

<<Screenshot of billing a user for a booking>> 


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

In order to add a car to your network, the car needs to be 'listed' on the network. 

The listing of cars for P2P networks is usually done by the owner of the car. For B2C networks, cars are listed by the network operator. 

Once a car is registered, there is quite a rigorous process to get it verified so that it appears in search results for borrowers to find. Generally, the following must be configured before a car can be borrowed.

1. The car must be fully registered, and have all the basic information filled out. e.g. Year, Make, Model, Location, Photo, Prices, Usage Model, etc.
2. The car must have details of a Certificate of Road Worthiness, and this must be verified by the operator.
3. The car owner must be fully verified as a car owner. Requires the owner to have a verified: Email, Phone, BankAccount.
4. The car must have any future availability set for it by the car owner.
5. The car must not be set as 'Offline'.

Only when the above requirements are met, will the car appear in the search results (and on the map) as 'Available'. Otherwise it appears in the search results (and on the map) as 'Coming Soon', and cannot be booked or used.

> Note: At any time, any of the car's verifications and any of the car owners' verifications may become unverified (some are time based, some are action based - see [Verifications](#Verifications) for more details), at which point the car becomes unavailable, and dissapears from the list of 'available' cars in search results.

For car owners (P2P or B2C), it is imperative that they get themselves and their cars verified, and stay verified if the cars are to be used.

> Note: It is imperative that operators stay on top of any manual verifications that would block cars from being fully verified at any time.

## Borrowing Cars



What borrowing means, who can do it, and some of the constrints around borrowing. i.e. account verifications

### Usage Models

Immediate versus Scheduled models

How usage is charged, fees are determined, revenue share is calculated etc.

## Cloud Hosted Environment

Your Hourfleet web app, all web API's, all associated network infrastructure and databases are all hosted in the cloud on Microsoft Azure, in a region geographically close to your business.

The network infrastructure is managed by Hourfleet, you don't need to worry about managing any of that.

All the data that is created or collected from your customers or your business is stored in secure data repositories and backed up for you automatically in the cloud.

Backups are run once a day, and stored for 30 days.

> Note: all data that is created or collected from your customers or your business belongs to your business, and can be obtained at any time. Please contact Hourfleet support for assistance.

