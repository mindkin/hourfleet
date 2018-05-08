---
layout: default
title: Release Notes
---
## 1.59.0 08/05/2018
### Improvements
* Added Summary section to Operations Dashboard to show current status of resources (inUse bookings, unverified cars, etc)

### Fixes

* Network Operator report data more accurate

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
* Manual billing becomes a lot easier. Ops selects a booking to bill and how much, the system then takes care of the rest.
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
