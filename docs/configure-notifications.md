---
layout: default
title: Configure User Notifications.
---
# User Notifications

At various times, your customers are going to get notifications sent to them via email or TXT message (or both) as well as In-App notifications. 

If you wish, you can also customize the content of all of these notifications, both the email content and the TXT message content. 

## Notification Parts

There are 3 kinds of notifications:

- Email notifications
- SMS text message notifications
- Notice notifications (In-App alerts)

SMS text notifications are only single lines of text only (no markdown is supported).

Notice notifications (currently) use the same content as the SMS Text notifications.

Email notifications come in both an HTML version and a plain text version. We define a HTML and plain text version because still some email clients only support plain text. The plain text version is also often used in inbox lists for summaries in some email clients. 

The logical structure of an email looks like this:

- Header - Often just a multi-lined title
- Content
  - ​	Salutation - a greeting like "Welcome" or "Hi Jim Smith"
  - ​	Paragraphs - multiple lines of individual content (Markdown is supported)
  - ​	Action - an optional call to action link at the end of the main content. Just a large button to press, that links to a web page.
- Footer - bottom of the email containing general messages, branding and social links.

##Custom Configuration

You can see all the different notifications [on this page](notifications.html).

> Note: Customization is optional. You would only provide configuration for the notifications you wish to customize the default content. For each notification you wish to customize, you only need to provide the elements of it you wish to customize. Leaving any part of the configuration blank, results in default content for each of those parts.

Here is an example showing the configuration for a customization of the notification: `101` (sent when a borrower makes a booking request and is not yet fully verified themselves) . 

~~~
{
    "Id": 101,
    "Email": {
        "Subject": "Get verified to continue! Your Booking request for '-car.name-' for period -request.startdate- to -request.enddate- is waiting.",
        "HTML": {
            "Header": ["Get Verified\nTo Continue"],
            "Salutation": "Kia Ora -borrower.name-,",
            "Content": ["Your account must be verified in order for the owner of '-car.name-' to receive your booking request."],
            "Action": {
                "Text": "Become Verified",
                "Url": "https://demo.hourfleet.com/settings/account",
                "DisableClickTracking" : false,
            },
        },
        "PlainText": {
            "Header": "Get verified to continue.",
            "Content": ["You must get verified in order for the owner of '-car.name-' to receive your booking request."],
        }
    },
    Sms: {
        "Content": "Get verified to continue. Your booking of '%car.name%' is waiting. See %request.url%"
    }
}
~~~

You can view this message [here](http://docs.hourfleet.com/notifications.html#draft-request-borrower)

## Customizable Elements

The configuration above defines your customization of the default notification for notification `101`.

There are several parts you can customize. Lets look at each one.

Firstly, you can define a customization for all of the parts, or only the ones you want to customize. The parts you can customize are:

- **Email.Subject** - provide this only if you want to customize the mail subject line. Do not include this element if you wish to use the default subject line.
- **Email.HTML** -  provide this only if you want to customize the HTML version of the email. Do not include this element, if you wish to use the default HTML version.
  - **Email.HTML.Header** - provide this if you want to modify the header section of the email. Do not include this element, if you wish to use the default header.
  - **Email.HTML.Salutation** - provide this if you want to modify the salutation of the email. Do not include this element, if you wish to use the default salutation.
  - **Email.HTML.Content**- provide this if you want to modify the main HTML content of the email. Do not include this element, if you wish to use the default content. Each paragraph is a separate line of text in an array. Each line of text can include Markdown syntax. If you want to include bullet points, tables, or hyperlinks, etc.
  - **Email.HTML.Action**- provide this if you want to modify the main call to action (button) in the email. Do not include this element, if you wish to use the default action. You can customize the text and the hyperlink itself.
  - **Email.HTML.Footer** - is not customizable.
- **Email.PlainText** - provide this only if you want to customize the plain text version of the email. Do not include this element, if you wish to use the default plain text version.
  - **Email.PlainText.Header** - provide this if you want to modify the header section of the email. Do not include this element, if you wish to use the default header.
  - **Email.PlainText.Content**- provide this if you want to modify the main content of the email. Do not include this element, if you wish to use the default content. Each paragraph is a separate line of text in an array. Each line of text can include Markdown syntax. If you want to include bullet points, tables, or hyperlinks.
  - **Email.PlainText.Footer** - is not customizable.

- **Sms.Content** - provide this only if you want to customize the SMS message and In-App notice. Do not include this element, if you wish to use the default message. Note, substitutions in this content are always surrounded by `%` signs for example: `%car.name%`
