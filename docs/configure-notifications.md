---
layout: default
title: Configure User Notifications.
---
# User Notifications

At various times, the users of your network are going to get notifications sent to them via email or TXT message (or both). 

You can watch these notifications in your favorite tool by setting up integration between Hourfleet and many other apps by using Zapier.com. See [Zapier Integration](zapier.html) for more details on that.

If you wish, you can also customize the content of all of these messages, both the email content and the TXT message content. 

You can see examples of these email notifications [here](notifications.html).

There are many, many notifications, so the example below will show only the configuration for the notification: `101`. 

>  Note: For each notification, the configuration is optional. You would only provide configuration for the notifications you wish to customize. And for each notification you only need to provide the elements of it you wish to customize. Leaving any part of the configuration blank, results in default content for each of those parts. 

~~~
"Notifications": {
  "Templates":[
    {
      "Id": 101,
      "Email": {
        "Subject": "Get verified to continue! Your Booking request for '-car.name-' for period -request.startdate- to -request.enddate- is waiting.",
        "HTML": {
              "Header": ["Get Verified\nTo Continue"],
              "Salutation": "Kia Ora -borrower.name-,",
              "Content": ["Your account must be verified in order for the owner of '-car.name-' to receive your booking request."],
              "Action": "Become Verified",
        },
        "PlainText": {
            "Header": "Get verified to continue.",
            "Salutation": "Kia Ora -borrower.name-,",
            "Content": ["You must get verified in order for the owner of '-car.name-' to receive your booking request."],
        }
    },
    Sms: {
      "Content": "Get verified to continue. Your booking of '-car.name-' is waiting. See -request.url-"
      }
    }
  ]
}
~~~

Here is an example of the email message for notification `101`, branded for the 'Roam' network.

> Note: that the section contain substitutions (between the characters `-`) for example `-car.name-`. By including these substitutions in the text, you can plug in those values from the notification itself. You can see the appropriate substitutions for each notification in the [Notifications](notifications.html) page.

![Email Notification](images/EmailPreviews/requestDrafted_borrower.PNG)
