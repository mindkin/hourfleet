---
layout: default
title: Release Notes
---


# Release Notes Moved

Release Notes are now posted as a Changelog in our feedback channel: http://feedback.hourfleet.com/changelog


## 1.87.0 - 01/04/2019

### Fixes

* Fixed Google recaptcha not appearing sometimes on registration page

## 1.86.0 - 30/03/2019

### Improvements

* Hourfleet has improved its support for PWA's and users are now presented with the ability to install the Hourfleet if they are in a supported browser.
* App installation guidance has also been improved to detect a users browser and offer a quick install button if supported.
* Bookings can now be reallocated by the vehicle owner to other available vehicles. This can be done for bookings that are Approved or or currently In Use.
* Vehicle owners are now told if there may be any bookings affected by taking their vehicle offline, and can try reallocate them if possible.
* Added an error message if starting a booking fails.
* Small Performance improvements to fetching Borrower, Vehicle Owner and Operator list of bookings.

## 1.85.1 - 20/03/2019

This release contained small updates and incremental work on current stories tracked on feedback.hourfleet.com

## 1.85.0 - 19/03/2019

### Improvements

* Booking start dates and end dates can now be changed after a booking has been approved as long as it has not begun.

### Fixes

* Fixed a bug with the booking date input which would incorrectly display the current date after a reset.
* Fixed an issue where vehicles would be displayed as available 'right now' on the search page even if they weren't.

## 1.84.2 - 12/03/2019

### Improvements

* Add an availability calendar to a car profile for Operations
* Operators can now search for bookings based on a date range

## 1.84.1 - 09/03/2019

### Improvements

* A vehicles 'quick actions' for an operator are now smarter about where they link to based on context

### Fixes

* Fixed missing 'No Vehicles' message on Operators Vehicle Search

## 1.84.0 - 25/02/2019

### Improvements

* Operators can now easily get to a Users profile, verifications and bookings after selecting a user

### Fixes

* After billing a booking, the booking page is updated to contain the latest information (billed)

## 1.83.3 - 22/02/2019

### Improvements

* Operators can now search for a booking based on it's reference number
* Operators can now jump to search users or search vehicles from the Operations Dashboard

## 1.83.2 - 12/02/2019

This release mostly contained improvements to GENIII carkit functionality

### Improvements

* Operators can now choose a carkit version when registering a carkit

### Fixes

* Added abililty to navigate directly to Ops Update Carkit using URL

## 1.83.1 - 18/02/2019

### Improvements

* Vehicles listed by a user are now displayed on a users profile for network operators. Note: this is subject to change in future releases.
* A vehicles location description is now displayed on the location page for a booking, in addition to the vehicle description page

### Fixes

* Bookings made on an 'auto-approve' configured vehicle will direct borrowers to their bookings view instead of an empty request view

## 1.83.0 - 11/02/2019
Included in this release is the requested User Search functionality for network operators which can be accessed through the operators dashboard. This allows operators to search for their customer based on Name, Email address or phone number.

### Improvements

* Reporting on a vehicles condition during a booking can now be accessed at any time in a booking.
* Faster lookup for In Use/Approved bookings and In Use Trips when redirecting to a users home page.
* A selected vehicle on the Ops Search Cars page will automatically open to show its quick actions, and to better signify which vehicle is currently being managed.

### Fixes
* Fixed an issue where some vehicle license plates would not display on the search page correctly.
* Vehicle ratings are now showing on search results again for networks that support Peer-to-peer.

## 1.82.1 - 30/01/2019

This release is a service maintenance fix, and contains no new features. Only performance improvements and minor bug fixes.

## 1.82.0 - 28/01/2019

### Improvements

* Quicker access to various sources of information in 'Manage Requests/Bookings/Takings' pages.
* Quicker access to various actions of a car in the 'My Cars' page.
* Car Condition Capture - borrowers are now prompted (before starting a booking) to capture the condition of the car (i.e. record damage before use). This step can be skipped. Whereupon they can see the register of damage on the car, and can then upload photos and text describing any new damage/conditions they find on the car.
* Operators can now search across cars in their network (by: license plate or by: make and model) and then view information about those cars.

### Fixes

* Perf improvements with loading network operator data in the web app.
* Fixed incorrect `-sender.name-` substitution in notifications for new converstaion updates.
* Fixed ordering of recently updated verifications in operator summary, so that recently changed verifications always appear high up in the list.
* Fixed issue with older versions of web app still lingering after new version deployment.

## 1.81.1 - 07/01/2019

### Improvements

* A criminal conviction complementary statement is now configurable by the network operator.

## 1.81.0 - 06/01/2019

### Improvements

* Car license plate has now been internationalised to include selection of a jurisdiction (Country/State), which is configurable by the operator.
* Road Worthiness (Certificate/Inspection) has been internatioanlised.

## 1.80.7 - 03/01/2019

### Fixes

* Fixed pagination in verifications and APIs 

## 1.80.6 - 02/01/2019

This release is a service maintenance fix, and contains no new features. Only performance improvements and minor bug fixes.

### Fixes

* Issue matching DOB formats in password reset answers.

## 1.80.5 - 31/12/2018

This release is a service maintenance fix, and contains no new features. Only contains performance improvements

## 1.80.4 - 20/12/2018

### Improvements

* Hourfleet now supports lighter colored navigation themes.
* Ops Carkits area has been updated and now has the ability to navigate back to a vehicle without requiring searching again.

## 1.80.3 - 19/12/2018

### Improvements

* The action bar on the manage request/booking/takenow pages has been updated for quicker access to messages and upload photos.
* Vehicle Booking rates can now have a custom currency amounts instead of being restricted to a list of rate values.
* Changed the layout of Edit Car Details pages so guidence is clearer.
* Pricing for hourly/daily/weekly rates are now free form, and not restricted by lists of values.

### Fixes

* Validation on the vehicle description and car location description have been fixed to have the correct maximum character limit (is now 5000 instead of 1000)

## 1.80.2 12/12/2018

### Improvements

* Adjust vertical size of the messages window for bookings and requests to avoid potential scrolling problems

### Fixes

* Fixed a display bug where clicking a 'read' notification would duplicate itself in the list
* Fixed ordering of unverified users so they are once again ordered by last created date

## 1.80.1 12/12/2018

### Improvements

* Conversations have been improved to now support sending image (alone or as attachment) and sending personal notes (messages that are private)
* Notifications are now sent to participating parties of a conversation when a new message is received. 
* Unverified Users and Cars show the most recently updated, instead of simply being order by most recent.
* Small performance optimisation for showing users a list of their current bookings and  history.
* Replaced some image icons with font icons for improve usability
* Optomised required cache download size
* Changed the 'Expand Image' dialog for viewing drivers licenes and conversation images to use the original image size, or the largest supported size.
* Visual changes to uploaded images to removed transparent banding and provide a more consistant appearance across the site.

## 1.80.0 26/11/2018

### Improvements

* Turned on perf optimizations for search API's

## 1.79.0 23/11/2018

This release contains major changes to Hourfleets API's with the purpose of improving the speed of the Hourfleet software site wide.
Improvements should be noticable when fetching verifications and a list of bookings. This is only the first phase of planned improvements with more targeted improvements coming in the future.

### Fixes

* Fixed the disabled toggle control for a vehicles offline status allowing it's status to be turned off and on again.

## 1.77.0 14/11/2018

This is a major release that brings with it improvements to how notifications are sent and displayed for users.
Notifications are now displayed to a user in the app (in addition receiving emails and sms), including specific notifications linking directly to important actions e.g. 'Booking about to begin' links to their booking.
Another major improvement is that users now have control over which notifications they wish to receive. They now have the ability to turn off the sending of emails or sms for most notifications in the preferences tab of their account details.

### Improvements

* Performance of the cars and users verifications pages for operators.
* The 'update app' message has changed to a small clickable bubble for desktop users.
* Added links to My Cars and List a Car for Operators in their Operations Dashboard

### Fixes

* fixed a display issue where the 'drivers license about to expire' warning would display for a user that had no drivers license listed.
* Includes a fix for a bug that was introduced in 1.76.2 where old user account verifications may not display for the operator.

## 1.76.2 28/10/2018

### Improvements

* This release includes the automatic notification and expiring of user drivers licenses. A [new email template](notifications.html#expiring-drivers-license-user) has been included and there has been messaging added to the user's Account Settings page to communicate when their drivers license is nearing expiry or has expired.
* The account settings page has been updated as part of the ongoing changes to make verifications easier to understand.

## 1.76.1 26/10/2018

### Improvements

* Vehicle and User verifications are now split into verified and unverified with unverified details being displayed first.
* A cars registration details on the ops verifications page can now not be verified/unverified by an ops user (auto-verified details)
* If a car autoapproves booking requests, when a request is made the user will be redirected to their bookings page instead of an empty request page.
* Car Make, Model and License plate are now added to the menu/sidebar when managing a car or editing it's details
* Several improvements to how dates and times are managed for the user both when booking a car and also for the car owner managing car availability: 
    * For borrowers (making a booking):
        * When selecting a start date beyond the end date, then end date is adjusted ahead of the start date by an hour.
        * When selecting the same value for the start and end date, the end date is adjusted ahead of the start date by an hour.
    * For car owners (managing availability for a car):
        * When selecting a start date beyond the end date, then end date is adjusted ahead of the start date by an hour.
        * When selecting the same value for the start and end date, the end date is adjusted ahead of the start date by an hour.
        * Initially, the rest of the current day is pre-selected to be added, and is visualised in the calender. 
        * When switching to 'All Day', the next day is automatically selected. 
        * When changing a new date, it is visualised in the calendar. The current time is visualised in the calendar. 

### Fixes

* Fixed refreshing of availabilities once a booking by a borrower has been made.
* Removed Vehicle Make, Model and Year in license section of a cars verification details

## 1.75.0 7/09/2018

### Fixes

* Fixed operator dashboard metric calculations for 'Became Unverified' cars and users
* Increased the cache time to live, which should speed up time to navigate data on pages

## 1.74.0 5/09/2018

### Fixes

* Fixed operator dashboard metric calculations for 'Unverified' cars and users

## 1.73.0 4/09/2018

### Fixes

* Fixed operator dashboard metric calculations for 'InUse' vehicles

## 1.72.0 27/08/2018

### Improvements

* Added rate limits to all API's, and critical security related API's
* Localised the driver license to the specific network, and allowed networks to define the jurisdictions of licenses it accepts.

### Fixes

* Replaced example dates used in validation messages (i.e. for DOB) to show an example of single digit entry for the day and the month to clarify what format is required for entry.
* Fixed incorrect display of criminal convictions in the verifications page for a user, and added a visual indicator of whether the user had declared a criminal conviction or not.

## 1.71.1 15/08/2018

### Improvements

* Added a notification message for borrower (217) and car owner (218) to notify them that the car has not yet returned in the app by the borrower by the time of the scheduled end of the booking.

### Fixes

* Fixed missing `booking.returneddate` substitution in 'complete booking' (208, 209) notifications when forced completed.
* Fixed crash when Redis cache throws an error 

## 1.70.2 9/08/2018

### Improvements

* (Zapier integration) Added 'EmailAddress' field to all user notifications
* (Zapier integration) Added 'booking.requesteddate' field to all user notifications for bookings

### Fixes

* Added confirmation to complete booking if the booking is not yet returned
* Fixed error in app when trying to extend abooking past the max duration of a booking for that car
* Fixed bug with users not being able to login after changing their email address
* Fixed mixed locales being used for formatting dates in user notifications

## 1.70.1 6/08/2018

### Fixes

* 'Last Updated' on Ops Verification Pages now updates after the call to get new verifications succeeds instead of before
* Fixed a display bug that causes a different car's details to change when taking a car offline/online on the 'My Cars' page
* Only show the borrower cancellation reasons if an owner is borrowing their own car and cancelling
* Only show the Key Exchange usage option unless a car has its carkit registered by the network
* Coming Soon pins are shown on the search page

## 1.70.0 3/08/2018

This is a major release that introduces 'Key Exchange' to bookings. That is, bookings without a carkit fitted in the car.
Car owners are now able to designate their vehicles as 'Key Exchange' (switch between 'Key Exchange' and 'Keyless'). 

[Key Exchange](howitworks.html#key-exchange) defines a rental model where physical car keys must be exchanged between borrowers and car owners, and the pick up and drop off of vehicles must be pre-arranged between those parties before and after renting the car. As a tool to facilitate the extra communication, the app now supports in-app conversations between the borrower and car owner during all stages of the booking process.
Key Exchange is not available to cars configured for the 'Immediate' usage model.

### Improvements

* Car owners can now select between 3 usage models: 'Scheduled - Key Exchange' (when no carkit is installed), 'Scheduled - Keyless', and 'Immediate - Keyless', but only when a carkit is installed. By default all cars are configured as 'Key Exchange'.
* Car owners can disable the carkit (when it is installed) to permit the car to be used in 'Scheduled - Key Exchange', on a per booking basis.
* Borrowers and car owners can now 'chat' in the app during the entire booking process (in all usage models).
* When errors are seen in the web app, more error details can be revealed as to the origin of the issue, to aid in error reporting.
* The criteria for cars to become searchable (and visible on the map as 'Coming Soon') has been relaxed to just requiring the car owner to complete all registration details. Whereas before, car owners also needed license plate and road worthiness verifications to be manually verified.
* When cancelling a scheduled booking or rejecting a immediate booking, a user now needs to select a reason for the cancellation/rejection to help potential conflict resolution in Key Exchange.
* There are several improvements to the 'My Bookings' page for borrowers, and 'Manage Request' for both parties.
* There are several improvements to usability of managing verifications in the operators dashboard.

### Fixes

* Pagination in the verifications pages in operators dashboard is now limited to the number of pages of the actual number of results available.
* When selecting a home location (or searching for a locaiton of a car) the user should no longer be presented non-street addresses to select.
* Duplicated email/TXT notifications should no longer be sent to borrowers or car owners notifying upcomign or past events.
* Fixed the missing error message when signing-in with an email address that was not recognized.
* Completed l10n of remaining dates, times, currencies, metrics etc.
* The 'Hourfleet USer Notifications' zap (on Zapier.com) is now fully configurable to work with any Hourfleet network.
* Fixed the displaying of 'unknown' when requesting a car for a period greater than what is allowed. A more user friendly representation of this condition is in use now.
* Fixed a display bug in the 'Private Message' control which would show "CommentMessage" if a network was configured to support B2C
* Fixed the displaying of multiple booking ranges on the 'Manage Booking' page once a booking has been returned or completed

## 1.69.4 12/07/2018

### Fixes

* Fixed bug in `en-NZ` date formats for input of DOB and other dates

## 1.69.3 10/07/2018

### Improvements

* Added support for /,( and ) characters when defining network car types

### Fixes

* Fixed a validation issue on the Car Details - Identity page where a worthiness expiry date

## 1.69.2 09/07/2018

### Fixes

* Password reset that includes a D.O.B has been fixed to compare the right date
* Changed Drivers License form to accept dates in current locale, and these dates are displayed in current locale (user's profile, verifications page, etc)
* Fixed unreadable date for Road Worthiness expiry date

## 1.68.0 02/07/2018

### Fixes

* Fixed CSS preventing scrolling of search results on the Find a Car page
* Fixed displaying of mobile icons on the network configuration page, where the images wouldn't show even if they were configured.

## 1.67.0 29/06/2018

### Improvements

* Strengthened authentication of instructions between carkit and platform.
* Added 'operations' link to navigation system

## 1.66.1 22/06/2018

### Improvements

* Better localization support for english language locales.
* The find cars page now centers on and zooms to the configured geofence for each network
* The geofence for each network is configurable to a country or city (any locality) in that country
* An operator can choose to provide their own support page and be linked to it, instead of using the provided one.
* An operator can now define and customize a list of vehicle types which the network should support (e.g. Car, MiniVan, Truck, etc)

## 1.64 15/06/2018

This platform update replaces the RunTheRed/Modica SMS gateway provider with Plivo.com provider, making it possible to send TXT anywhere in the world. All mobile phone numbers of all users will be automatically adjusted to become internationally dialable, with the inclusion of the '+' prefix and country code. (Some numbers that were not valid mobile phone numbers will be discarded). Operators will also configure a default country code. 

### Improvements

* Added ability for operators to provide their own support page.
* Reduced configuration for operators, as SMS provider moved to platform.

## 1.63 11/06/2018

### Improvements

* Added configuration for notification templates 4010, 4011 + 4012
* Removed unneeded white space from email templates
* Added User.Firstname and User.Lastname to available substitutions for notifications

### Fixes

* Fixed url to a car profile in notifications that would direct to a 404 page

## 1.62 08/06/2018

### Improvements

* Certificate of Worthiness renamed to Safety Certifications
* Reduced white space between paragraphs in emails
* Remove trailing ',' on email salutation for better configuration
* Improved formatting for distances, currency, percentages and dates

## 1.61.2 01/06/2018

### Fixes

* Moved Stripe Cofiguration to Tennant Settings

## 1.61.0 30/05/2018

This platform update replaces the Paystation Payment provider (NZD currencies only) with a global Stripe Payment provider for handling global currencies and global remittance.
Credit Card numbers from network users that were taken on previous versions of the Hourfleet platform, will not longer be valid, and network users will automatically become unverified, as their Paystation credit card details will be removed. They will need to re-register their credit cards to become verified again. 

### Improvements

* Changed the way percentages are calculated for the network operator report
* Updated APIs to allow changing of network locale
* Removed Home Location field from Register Car page
* Replaced Paystation with Stripe as the default payment provider
* App Loading screen now uses values defined by the network operator (navigation color + spinner)

### Fixes
* Added missing spinners on the Edit Car Detail pages


## 1.60.1 09/05/2018
### Fixes

* Licence Fees in Network Summary report now use a subscription began date for calculating past costs

## 1.59.0-1.60.0 08/05/2018
### Improvements

* Added Summary section to Operations Dashboard to show current status of resources (inUse bookings, unverified cars, etc)

### Fixes

* Network Operator report data more accurate
* Fixed startup error with 'operators' migrator

## 1.58.0 05/05/2018

### Improvements

* Graphs are added to new users and new listings on the Ops Dashboard comparing current period to last 2
* Added a subscription plan to the Network Configuration file
* Added a Configuration page to Operations which displays the current Network Configuration

### Fixes

* Searching on an unknown address/location on the search page will display a message instead of not searching
* Updated the Ops Dashboard reports for better distinctions between a summary and an activity focused report

## 1.57.0 24/04/2018

### Improvements

* Updated 'period' selector in ops dashboard
* Added aggregated reporting for bookings and takings

### Fixes

* Added safeguard to prevent 'userprofile' and 'verification' records being created (on-demand) for non-user accounts.

## 1.56.0 22/04/2018

### Improvements

* Metrics for car listings and bookings now available on the Ops Dashboard.
* There are now graphs showing the previous periods in comparison to the current view period for Cars and Users
* A network's theme color now uses the navigation color in the network config so navigation is blended with the browser on mobile devices
* The ops alerts panel is now removed as it shows redundant information

### Fixes

* Fixed a bug that causes the verifications list to become hidden
* Error messages are now shown on the Ops Verifications pages

## 1.55.4 18/04/2018

### Improvements

* Metrics for number of new, unverified and total Users is now available on the Ops Dashboard.

## 1.55.3 12/04/2018

### Improvements

* The navigation has been changed where all page links are now contained in the mobile menu and the sidebar only appears on larger screen sizes.
* The Operations Dashboard has had an overhaul and now has specific contexts to find operational activities like billing, verifing users or managing carkits.

## 1.54.0 22/03/2018

### Fixes

* Fixed empty pages in search results (various result sets, including: specifically availability and verifications)

## 1.53.0 20/03/2018

Only minor infrastructure changes and performance optimizations in this release.

## 1.52.0 14/03/2018

An intermediary build, was not released, and rolled back.

## 1.51.0 13/03/2018

### Improvements

* Upgraded all web servers to HTTP/2 for increased performance
* The web app now qualifies as a Progressive Web Application (PWA), and support offline view in the app.
* We now hide the 'Manage' section on the bookings page when there are no actions to take e.g. after a booking has completed

### Fixes

* Changed salutations of all email templates to use 'Hi' instead of 'Kia Ora' 
* Operations staff can now only change one verification at a time. Previously, this process could get out of sync.
* Recently updated cars now appear at the top of the verifications list
* When taking a car offline, the spinner for that car is shown. Previously, spinners for all cars were shown.
* Fixed typo on NZ drivers license form.

## 1.50.0 24/02/2018

This release is just a routine maintenance build including very minor changes.

## 1.49.0 21/02/2018

This release separates all web components into separate scalable units for future optimization. 

### Improvements

* Car's name of the car you are editing is now included in the sidebar

### Fixes

* Images are now cached in browser, improving download response times.
* Drivers license entry form updated to allow older driver licenses (older than 1970).
* Booking calendar displays week (rather than day) by default
* Date format of calendar now localized for NZ.

## 1.48.0 16/02/2018

### Improvements

* Improvements to the Request Booking Calendar with the inclusion of a 'day' view and more distinct color seperation between available and unavailable times.
* The Request Booking Date Controls will now alert the user if their requested time period is outside the booking periods defined by the network and car owner.
* When the Minimum Booking Period and the Maximum Booking Period are equal (e.g. bookings MUST be a 15 minutes) then only a start date and time when requesting a car is available, with the end time being automatically set
* Increased the spacing between the buttons in a bookings 'manage booking' control for better usability on small form factors

### Fixes

* Added headers to the sidebar menu
* Updated api rules to better support starting a booking near its end time during a short booking period
* A car's Max Booking Duration Setting can no longer be less than a network defined Minimum Booking Period

## 1.47.0 14/02/2018

### Improvements

* Wording for private messages during a booking changed to instead reflect leaving comments for B2C networks
* Certain notifications no longer are sent for short duration bookings
* Improved usability of the date picker when making a booking request
* UI changes made for Ops Verifications page to improve usability and reduced unneeded information
* Ops Verifications page will now update every 30 seconds with the latest verifications
* Ability for Ops Users to clear specific network cache's
* The Mobile Menu on small form devices is now includes current page sections e.g. User Settings contains Account Details, Profile Details, Reset Password. e.t.c.
* References to 'My Listings' has been changed to say 'My Cars'


### Fixes

* Updated the display of future bookings on a car availability calendar to appear less like availability slots
* Cancelling a booking restores the availability slot
* Fixed a bug which caused a zero length booking to appear when making a booking
* Fixed a bug that would cause a failing search for cars when using a non existing street address
* Fixed a bug which causes a user to become unknownly unauthorised when signed out from a different device

## 1.46.0 07/02/2018

### Improvements

* Now can customize teh copy of all email/SMS notifications
* A new search page that can be centered on a street address

### Fixes

* Not being able to book a car for minimum duration
* Email substitutions now look for the most common dashes. (i.e. hyphen or en-dash or em-dash)

## 1.45.0 06/02/2018

### Improvements

* All Emails and TXT notification messages can be fully customized. 

## 1.44.0 05/02/2018

### Improvements

* Addition of more comprehensive health checks for all API's
* Updated language used in agreement to terms, feedback page, and messaging between owners and borrowers.
* Removed the 'how to find a car' help link on search page
* Increased performance of sending email/TXT notifications
* Displaying message history (between owner and borrower) in booking
* Page menu for current section is highlighted
* User account page replaces profile details page in menus
* User is now directed to verifications after creating their account
* Added a sign-up page for operations staff
* Operators can now control whether to show or hide the mobile app link in the footer
* Operators can now add their own Google Analytics to the web app
* Now support a ZeroCharge network, where there are zero usage charged to any borrower
* Now display "No Charge" for all pricing for a ZeroCharge network

## Fixes

* Fixed URL validation to prevent subdomain access
* Removed car park owner verifications UI
* Social media links (and header) are hidden when not configured (in footer and support page)
* Calendar is now displayed when booking a car
* Removed operator control of 'DisplayDurations' on a taking in favour of controlling same functionality of a ZeroCharge network
* Fixed a bug in locating a car when returned home
* Removed ability for car owner to see location information of existing inuse bookings
* Removed multi-language switching controls in footer

## 1.43.0 12/01/2018

### Improvements

* Addition of jobs to replay failed logging data

## 1.42.0 10/01/2018

Redeployment of the platform into new Azure infrastructure, including new monitoring and SSL certificates.

## 1.41.0 04/10/2018

### Improvements

* The platform has been upgraded to support multiple-tenants, and increase in capacity and throughput (via load balancing infrastructure).

## 1.40.1 - 1.40.4 17/10/2017

### Improvements

* Various security updates.

## 1.40.0 30/09/2017

### Improvements

* 'Forget password' now supports adaptive secret questions based on profile information provided by user (e.g. driverslicense, dateofbirth, bankaccount, creditcard numbers, etc).
* New operational alerts for password reset activity, and account lockout activity.
* All operational alerts (above 'Noise' level) persist for a minimum of 7 days.
* A users account will now be locked out for several minutes if they fail authentication more than a few times in a row.

## 1.38.0 15/09/2017

### Improvements

* Registered users can now reset their password (with secret questions and answers)

### Fixes

* Operation alerts now are hidden when clicking the trash can

## 1.35.10 28/08/2017

### Improvements

* Important/Security OPS Alerts now stay around for a week. With ability for OPS users to mark alerts as 'read' to hide them. 
* Better reporting of failures and alerts with integrations to Paystation and RunTheRed.
* OPs Dashboard is opened automatically for any "OPS" role user.

## 1.35.8 07/08/2017

### Fixes

* Fixed bug in the generation of storage identifiers based upon DateTime.UtcNow, and it not creating unique enough ids within short timeframes.

## 1.35.1 - 1.35.7 03/08/2017 - 07/08/2017

These releases are a series that refactor the Azure Infrastructure (i.e resource groups), and add additional diagnosis information for Alerting issues found in Production.

### Improvements

* Minor imporvements in data quality in operational alerts and presentation of them

## 1.35.0 03/08/2017

This was a maintenance fix related to changing only the storage connection configuration for the migrated data of roamride to dedicated store.

## 1.34.0 30/07/2017

### Improvements

* Added Operations Alert for any pages requests that return 404, in a summary for the period
* Improved alerting to allow significant alerts like 'Security' and 'RequiresAction' to live for longer periods i.e. a week, and require manual dissmissal - coming in future release.

## 1.33.0 28/07/2017

The new deployment in this release decreases Azure VM sizes; from 'Standard_D2' (for web roles) and 'Standard_D1' (for Worker roles) to 'Medium' (for web roles) and 'Small' (for worker roles).

### Improvements

* Removed crash report on web sites for a 404 or any other HTTPException

## 1.32.0 22/07/2017

The new deployment in this release increases Azure VM sizes; from 'Medium' (for web roles) and 'Small' (for Worker roles) to 'Standard_D2' (for web roles) and 'Standard_D1' (for worker roles).

### Improvements

* Replaced SSE with WebHooks for reliability
* Borrower request history consistent with Borrower booking history
* Takings history (for borrower)
* Taking history (for owner)
* Tidied Operations control of a car

### Fixes

* Search page alignment to compensate for sticky footer
* Sticky footer in IE
* removed duplicate in CSS Styles
* Added magnifying image of drivers license in Operations
* More emphasis on drivers contact details


## 1.30.0 (23/03/2017 - roamride only)

### Improvements

* All search API's now have metadata attached.
* Added zoom into dirers license photos (in Ops Dashboard)
* Improved paging in Ops verifications

### Fixes

* Fixed scaling of profile images in Firefox and IE

## 1.28.0 (13/02/2017)

### Improvements

* Upgraded the OAuth2 dialogs and error messages 

### Fixes

* Fixed Google re-Captcha validation

## 1.27.0 (02/02/2017)

### Fixes

* Fixed intermittent 403- forbbidden exceptions (missing roles), and improved performance of each API call.

## 1.26.0 (26/01/2017)

### Improvements

* Added pagination control to Verification page in Operations dashboard to page through unverified users and cars
* Added product version number to mobile menu (under 'More' option).
* Added better (human friendly) error pages when connecting Zapier to API

### Fixes

* Fixed google captcha validation bug, preventing new users registering on site
* Fixed up GettingStarted page and removed all references to 'Roam', and tailored it for a B2C only business model.
* Fixed cyclic-signin page where after signin the user is redirected back to signin again, appearing like the button click on 'Sign In' had failed first time.

## 1.25.0 (19/01/2017)

### Improvements

* Added current version of app to footer.
* Added self-update feature to web app, so that when new releases are deployed they are downloaded, and users will be auto-magically, notified, and will be encouraged to upgrade.

### Fixes

* Fixed cache invalidation for some API's related to changing car usage models and online/offline status
* Fixed bug displaying duration before a booking about to start

## 1.24.0 (17/01/2017)

### Improvements

* Added new 'Access Car' tab to BookLater pages.

### Fixes

* Fixed HTML5 caching issues
* When a user account is verified, the missing verification messges are removed from profile page.

## 1.23.0 (15/01/2017)

### Fixes

* Fixed problem with secured pages not redirecting to signin page

## 1.22.0 (14/01/2017 - roamride only)

### Fixes

* Fixed 401 race condition (in webapp) when cached tokens are lost
* Fixed presentation format of durations (Usage/Overdue) in Takings/Bookings

## 1.21.0 (10/01/2017 - withheld)

### Fixes

* Fixed 401 race condition (in webapp) when cached tokens are lost
* Removed duplicate bookings when a booking is billed in OPS dashboard

## 1.20.0 (28/12/2016)

### Improvements

* Added "Authorization Flow" for OAuth authorization
* Increased upload size of photos to 5000pixels in either width or height to support Iphone 7 devices.

## 1.18.9/1.18.10 (19/12/2016)

### Improvements

* Improved URL formatting on wrapped apps

### Fixes

* Added fix for the Intercom Chat window to reboot it after a shutdown
* Added fix for spaces and other punctuation characters in first and last names


## 1.18.8 (17/12/2016)

### Improvements

* Added url for creating a web app which will redirect if it is already a web app
* The car owner verification badge on the user profile is hidden if network doesn't support P2P
* Added meta tag for iOS apps to share the same name as the Network provider by default

### Fixes

* Google maps no longer requires user location information before initialisation 

## 1.18.7 (15/12/2016)

### Improvements

* Click on a search pin doesn't change the map zoom level
* The 'Book Now' button for 'Take Now' cars has been renamed to 'Reserved'

### Fixes

* Remaining verification count doesn't include car owner details when Network doesn't support P2P
* Pend request link on rides/bookings has been fixed
* The 'Reserved' button for a search result is hidden when the car is unavailable

## 1.18.6 (13/12/2016)

### Improvements

* Removed the User Notification Settings page
* Added loading icon on search page when fetching all cars
* The order 'Take Now', 'Book Later' and requests are now propperly order in the car owner history and ops bookings
* Hiding owner verification requirements on User Accounts page when a network doesn't support P2P

### Fixes

* Reduced caching times for Requests/Bookings/Takings so that takings/bookings are refreshed in UI

## 1.18.4/1.18.5 (12/12/2016)

### Improvements

* Search results now ommits 'Immediate' usage cars that are reserved or in-use
* Email notifications to borrowers for operators that dont support diplaying costs, no longer show costs

### Fixes

* Fixed bug in email that replaces dollar values with partial costs
* Cached operator data is refreshed frequently
* Broadend input validation to accomadate common punctuation, and shorter/longer names

## 1.18.3 (11/12/2016)

### Improvements

* Privacy statement on invite page now configurable by operator
* Car history items now ordered by their Start Date
* Added a returned message to Car History items
* Add the rating and feedback message to a 'Take Now' history item
* Added check for iphone web app to hide the unsupported browser message

### Fixes

* Navigation Links no longer appear if operator doesn't supply a url for them.
* Validation error for email field on login changed to 'email' instead of 'user name'
* 'Take Now' emails are now populated with a url to the trip.
* Removed ui-state option from Tabbed Directive which was causing browser console errors.

## 1.18.2 (8/12/2016)

### Improvements

* A Car Owners historical Requests, Scheduled Bookings and Take Now Bookings are condensed into a single list.
* Added a 'Back to My Listings' on a car's edit details page.
* Added spinner and failure message on the Manage Request page for cancelling a request.

### Fixes

* Spacing between search results remain when selecting a result.
* Fixed javascript error that prevented a 'Take Now' unlock button from sending an unlock command.
* Fixed text for car seats and booster seats on a car's profile page

## 1.18.1 (6/12/2016)

### Improvements

* Removed 'dangerous' actions from car requests page, instead request and booking actions can be done on their standalone pages.
* 'Take Now' booking actions and car lock/unlock buttons are moved into a tab menu.
* Footer now sticks to bottom of the page when there is not a lot of content.

## 1.18.0 (6/12/2016)

### Fixes

* Car Offline warning message during a 'Take Now' booking only displays if the booking is currently in use.

## 1.17.8 (1/12/2016)

### Fixes

* Async buffered recording (logging/auditing/tracing/diagnostics) replaced with background sync version

## 1.17.6 (30/11/2016) (Deployment rolled back)

### Improvements

* Invite (Join) page can be prepopulated with URL Query parameters as an extension of onboarding process
* Removed 'Remember Me' checkbox from login (as redundant). All logins are remembered, and expire after 14 days regardless.
* NetworkOperator configuration API added.
* Increased hourly/daily/weekly pricing choices (to support B2C cars)
* Added pricing guidance (ThirdParty cars)
* Added insurance valuation limits to operator configuration

### Fixes

* Fixed reversed Offline/Online text
* Fixed button/link color in email templates
* Fixed render bug in 4000 (invite) template 

## 1.17.5 (24/11/2016)

### Improvements

* Integrated Intercom and Freshdesk LiveChat widget (configurable by NetworkOperator)
* Updated web site navigation between Marketing site and Operational site
* Support displaying duration instead of cost/pricing (configurable by NetworkOperator)
* Added control for changing car's Offline/Online status

### Fixes

* Fixed bug with expiring authentication tokens too soon

## 1.17.4 (22/11/2016)

### Improvements

* Added visual improvements in diplay of IOS and Android apps, when creating icons from web app.
* Hidden various pages and UI elements from user (i.e. car ratings) when the car is owned by NetworkOperator (B2C)
* Added all lifecycle notifications for a TakeNow rental
* Added notification reminder to borrower if TakeNow rental is nearing max duration
* Added NetworkOperator configuration for Freshdesk.com or Intercom.io LiveChat
* Added NetworkOperator configuration to control whether to display costs or durations for TakeNow rentals 

## 1.17.3 (18/11/2016)

### Improvements

* Added Instagram to social configuration
* Added trip summary to Reserve-Use-return flow of TakeNow
* Added Reserve-Use-Reject and Reserve-Reject and reserve-Use-ForceReturn flows to the app
* Added auto-Expiry of expired reservations in TakeNow
* Merged TakeNow reservations with BookLater requests and bookings into one consolidated list on 'My Bookings' page
* Added TakeNow uses to car owners summary page
* Added Rating fallback upon return in Reserver-Use-Return flow
* Added TakeNow completed reservations to OPeration dashboard for billing.
* Updated car search UI to differentiate cars that are 'BookLater' from cars that are 'TakeNow'
* Removed the Browser warning for Safari browsers
* Added car owner's view of a TakeNow reservation

## 1.17.2 (6/11/2016)

### Improvements

* Created the TakeNow usage flow, including the Reserve-Use-return and Reserve-Cancel/Expire flows.
* Added the costing and usage models for TakeNow 
* Updated car profile UI to differentiate cars that are 'BookLater' from cars that are 'TakeNow'
* A car can now be designated with a usage type (Immediate/Scheduled) and edit settings for each usage type. A car can be switched between the two usage models at any time (given certain constraints).
* Redirect users to either their current Taking or Booking if they have one on the go at that time.

### Fixes

* Flicking spinner
* Some minor email formatting changes
* moved (Acme) test site in production

## 1.17.1 (26/10/2016)

### Improvements

* Tailored emails for each newtwork operator
* Minor changes to network operator theming

### Fixes

* 'Start Booking' button put back in place

## 1.17 (25/10/2016)

### Improvements

* The platform has been split to separate the 'Marketing' portal of the network operator from the 'Operational' site. Network operator 'Operational' sites are now deployed to dedicated cloud services and data repositories, and custom domains: `{netop}.hourfleet.com`
* The 'Operational' site has been whitelabelled for each Network Operator.
* Email templates have been whitelabelled for each Network operator.
* Network Operator customization has been factored into static (Cloud) configuration (one per deployment)
* Numerous customizations are available for a network operator including:
    * Site branding
    * SEO data, icons and images
    * Navigation between sites
    * Support information (Company, Insurer, emergency contact etc.)
    * Culture and Timezone
    * Social media links

## 1.12 (8/10/2016)

### Improvements

* Viewing a users public profile can be done without signing in
* Mapping of car transmission type on search page (auto -> Automatic)

### Fixes

* Translation error in footer link

## 1.10.3 (9/10/2016)

### Fixes

* Fixed the web app remapping 401 to 500

## 1.10.2 (8/10/2016)

### Fixes

* Bug preventing changing password

## 1.10.1 (6/10/206)

### Improvements

* Changed Hourfleet data storage scheme

## 1.9.0 (6/10/2016)

### Improvements

* Improved Display of car details/rating on Rides/History
* Rating and Feedback to public car profile, plus style changes
* Added new Authorization scheme to Hourfleet
* Added 503 page

### Fixes

* Request public feedback no longer requires being signed in.
* Fixed issue where verified badges on user profile would not show unless you were recognized as a borrower or car owner
* Fixed bad 503 handling of the Application Caching in browser
* Custom web server errors no longer apply to the web api

## 1.8.3 (25/09/2016)

### Improvements

* Added license plate details for each car on My Listings page
* Added the rating badge to profile-image directive
* Added car rating, year and transmission type to search page results
* Added 'request now' link to search page results which opens car profile modal. Creates fallback if google maps doesn't load.
* Added User ratings to Car, Bookings and Request pages.
* Recently Changed users now appear at the top of the ops verification list

### Fixes

* Changed getrating spinner text on Users public page to say getting rating instead of getting feedback

## 1.8.2 (17/09/2016)

### Improvements

* Home page can now be translated into French
* Created a page to show users public information

### Fixes

* Changes mapping issue that prevented the saving of feedback.

## 1.8.1 (25/08/2016)

### Improvements

* Separated Booking content into different tabs for clearer reading
* Roamm is now Hourfleet.api!

## 1.6.1 (15/08/2016)

### Improvements

* Created owner view and controls on the stand alone Booking Request page
* Added leaving and reply to messages when taking an action on a request
* Updated Scout Serialisation to support Gen4 instructions

### Fixes

* Deserialisation methods for ScoutSerializer
* Bug that allowed an owner to fetch a canceled or expired pending request

## 1.5.5 (27/07/2016)

### Improvements

* Added live Freshdesk chat support
* Now using new queue buffering of logs

### Fixes

* Spell check across the site!

## 1.5.4 (23/07/2016)

### Improvements

* Created a standalone booking request page for borrowers.
* Added default sorting for all searches
* Integrate new IRecorder performance improvements

### Fixes

* Replaced the ability to leave a message when returning a booking.
* Fixed issue with missing fonts in cache

## 1.5.1 (12/07/2016)

### Improvements

* Header menu items are now grouped in a drop-down to allow for more items.
* The 'Bill User' button is now disabled when billing someone to prevent multiple billings.
* It is now possible to settle a booking without billing a user.

### Fixes

* Fixed horizontal scrolling issue with mobile menu when used in mobile browsers
* Updated Google Maps configuration to meet new API requirements and reduce load.

## 1.5.0 (7/07/2016)

### Improvements

* Menu items when on tablet/mobile resolutions are now displayed similar to mobile apps and transition in from the left rather than from the top of the screen. Mobile menu can now accommodate more menu items.
* Manual billing becomes a lot easier. Ops selects a booking to bill and how much, Hourfleet then takes care of the rest.
* Ops can now see if a cars bookings still needs billing and by what amount or if a booking's bill has been settled.
* Updated Cloud diagnostics
* The 'lock car' step that would make borrowers think they had finished their booking has been removed. Roam now locks the car before finishing the booking.

### Fixes

* Fixed typo that prevented users uploading back image of driver's license

## 1.4.6 (28/06/2016)

### Improvements

* Refactored the WorkerRole design pattern to handle forced stops more gracefully, and avoid ThreadAbortExceptions, and improve parallel processing utilization.

## 1.4.5 (26/06/2016)

### Improvements

* Added Roam Borrower video to home page
* Added 2016 Gold Awards Finalist badge to home page

### Fixes

* Creative Commons label on register page no longer sits over top of register button on certain screen sizes
  
## 1.4.4 (24/06/2016)

### Fixes

* HTML5 caching, so that new versions of the app are reloaded when browsing to the site

## 1.4.3 (21/06/2016)

### Improvements

* Improved performance (caching and speed) of the signin process
* Added flare to the signin and signup process

### Fixes

* Fixed more neglected UI tests
* Fixed missing substitutions in borrower emails
* Fixed editing of Criminal Conviction in Profile page
  
## 1.4.2 (22/06/2016)

### Improvements

* Added docs page: https://www.roamride.co.nz/docs
* Combined Signin and Signup pages into single page (removing modals, and associated problems)
* Changed the car registration process to remove Key Compatibility as a prerequisite for car registration

### Fixes

* Fixed the comparison of variable pricing in UI tests
* Fixed/removed neglected UI tests that have started filing in recent releases
* Fixed display in in CurrencyFilter
  

(release notes began 22 June 2016 at version 1.4.2)
