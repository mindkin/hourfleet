---
layout: default
title: What You Need to Provide
---
# What You Need to Provide

Setting up a new car sharing business can be complicated. There is much to think about besides having a web site and some cars. 
You are going to need to run a legitimate company in your geography, and worry about things like: Terms Of Service, Privacy Policies, Tier1 Support, Marketing, Social Media, etc.

One of the things you are going to get (see [What Is In The Box](inthebox.html)) is a cloud tenancy on the Hourfleet platform with your own app for your customers. While the Hourfleet platform provides many of the online tools to help manage your customers and operate your car sharing, you are still going to need to sort out some commericial relationships with supporting businesses so that the platform automate most of the work for you.

These are broadly some of the things that you need to do:

* Create a Merchant Account with your Bank
* *[New Zealand Network Operators]* - Create a PayStation account that can charge your customers credit card and remit to your merchant bank account
* *[New Zealand Network Operators]* - Create a RunTheRed account, so that your customers can receive SMS TXT message alerts, and so that your cars can be operated remotely (keyless-access).
* Construct a Terms Of Service agreement with your Lawyers
* Create a Privacy Policy with your Lawyers
* Create a 'front door' website to inform and capture your customers, and that can lead your customers to register and use cars in your network.



# Paystation Account
*[New Zealand Network Operators Only]*
Once you have secured a Merchant Bank account, you can create an account with [www.Paystation.co.nz](www.Paystation.co.nz).
You will need to create an account that gives you the ability to charge your customers credit cards, and make payments into your bank account.

Hourfleet integrates with Paystation to collect and verify your customer's credit cards, using what is called a *3-party with tokenisation*. 

To get started you need to follow the [Getting Started](http://www.paystation.co.nz/how_to_get_started) process outlined by Paystation.

As part of that process you will need to fill out the onboarding form. On that form you will see a section called: "Software Integrator". You will need to put the following Details:

![Paystation Application Form](images/Paystation-Onboarding-Form-SoftwareIntegrator.png)

Hourfleet does not capture nor store credit card information. Instead, Hourfleet hosts (in a web page iframe) a Paystation credit card form that Paystation provides, and all credit card details from your customers are handled directly by Paystation. Hourfleet then stores a token which is then used to charge your customers credit card, when you bill them. 

PCI-DSS (Payment Card Industry Data Security Standard) is the set of rules that govern how businesses should handle customer credit card information, and Paystation is fully PCI compliant.

## Technical Setup

In addition to filling out the paper form, you need to work with paystation to configure a few things so Hourfleet can integrate with Paystation, so that you cann bill your customers.

First, you will need to tell Paystation to configure the following URL's in order for Hourfleet to be able to collect credit card information from your customers, and for you to bill your customers.

They are:

* Return URL: https://yourtenancy.hourfleet.com:4431/api/payments/gateway/cards/confirmation
* POST URL: https://yourtenancy.hourfleet.com:4431/api/payments/gateway/cards

Once Paystation have setup your account, Hourfleet requires that you provide the following information for your tenancy:

* GatewayId
* PaystationId

These details are provided to you by Paystation after creating your account.

## IP Protection
Paystation has IP security to ensure that credit card details and charging only occurs from trusted servers, such as the servers in your tenancy.

Paystation requires that once your tenancy is created they configure IP protection with the IP address of your tenancy'.
You will need to set that up with them directly.

You can ask us for this IP address, or you can also find it our yourself by doing a:

```
ping yourtenancy.hourfleet.com
```

## Responsive UI

In addition to filling out the paper form, by either phone or email, you will need to request from Paystation that they turn ON the "Hosted Responsive Format". This is Paystation's version of the credit card entry form that scales well for your web app when viewed on a mobile phone. Without it, the Paystation form is hard for mobile users to enter their credit card information. It looks something like this:

![Paystation Responsive Form](images/Paystation-ResponsiveForm.png)

## Incomplete Transaction Notifications

When a user tries to register their credit card in your website and it fails (i.e. wrong card number, or insufficient funds, etc) the user will be notified then and there in the app. However, if they go to register their card, and they do not complete the process fully (i.e. they abandon it, or put in wrong details and then abandon, or get an error and abandon) then Paystation will send you a notification email called a 'Incomplete Transaction Notification'. You will need to provide an email addres to Paystation for those notifications, for example: support@yourcompany.com

## Go-Live

Once that is all setup, Paystation requires that you go through their "Go-Live" procedure before your customers can start being billed. That process is outlined here: [Go Live Procedure](http://www.paystation.co.nz/Go-Live-Procedure). For that you will need to publish your 'Refund Policy' online in your website (usually stated somewhere in your Terms of Service). And then notify Hourfleet support that you are ready to start processing payments.

## Additional Payment Tools

Note: In addition to making payments to your customers through the Hourfleet web site, Paystation also provides you the ability to manually charge your customers using their website. This can be handy for resolving customer issues outside the scope of what Hourfleet can do for you. 

On their site, Paystation  provides you with a full suite of manual payments products, i.e. PayMe invoicing, and payment transaction reporting. [Paystation Admin](https://admin.paystation.co.nz/)

# Modica Account
*[New Zealand Network Operators Only]*

Hourfleet integrates with [www.modica.co.nz](www.modica.co.nz) (formerly RunTheRed) as a text messaging gateway used by HourFleet for sending alerts to your customers, and instructions to the cars in your network.

You need to create your own account with Modica and obtain a shortcode so that Hourfleet can use this service.
The service you are creating needs to support the following: Text Messaging, and Delivery Receipts (DLR), but *not* Mobile Origination (MO). 

## Technical Setup

Please contact Modica directly to setup your account.

Once you have created you Modica account and confirmed that it's working using the Modica management tool, Hourfleet requires that you provide the following information for your tenancy:

* GatewayKey
* ShortCode
* Username
* Password

For delivery receipts to work, you need to inform Modica of the we address where they must send DLR's:

* DLR URL: https://yourtenancy.hourfleet.com:4431/api/sms/status/${messageId}/update?dlr=${dlr}

## Additional Management Tools

Modica will also provide you a login to their site ([manage.runthered.com](https://manage.runthered.com)) so that you can monitor an track all your text messages, and configure your account.
