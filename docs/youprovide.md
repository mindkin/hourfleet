---
layout: default
title: What You Need to Provide
---
# What You Need to Provide

Setting up a new car sharing business can be complicated. There is quite a bit to think about besides having a web site, an app and some cars.

You are also going to need to run a legitimate company in your country and jurisdiction, and worry about things like: Insurance, Terms Of Service, Privacy Policies, Tier1 Support, Marketing, Social Media, etc.

One of the things you are going to get with Hourfleet (see [What Is In The Box](inthebox.html)) is your own cloud 'tenancy' on the Hourfleet platform with your own branded app for your customers, with other tools for managing your car sharing business. While the Hourfleet platform provides many of the online tools to help manage your customers and operate your car sharing, you are still going to need to sort out a few commericial relationships with supporting businesses so that the platform automate most of the work for you.

These are broadly some of the things that you need to do:

* Create an account with Stripe.com, so that you can charge your customers' credit cards
* Construct a Terms Of Service agreement with your Lawyers
* Create a Privacy Policy with your Lawyers
* Create a 'landing page' website to inform and capture your customers, and that can lead your customers to register and use cars in your network.

# Stripe Account
If you don't alread have a Stripe account you'll need to [https://dashboard.stripe.com/register](register). If you need to do this, we recommend you take some time [https://stripe.com/customers](to learn about Stripe).


![Paystation Application Form](images/Paystation-Onboarding-Form-SoftwareIntegrator.png)


# Modica Account
*[New Zealand Network Operators Only]*

Hourfleet integrates with [www.modica.co.nz](http://www.modica.co.nz) (formerly RunTheRed) as a text messaging gateway used by HourFleet for sending alerts to your customers, and instructions to the cars in your network.

You need to create your own account with Modica, through contacting Modica directly, and you need to obtain a shortcode so that Hourfleet can connect to your Modica account.

The Modica service you are registering for needs to support the following: 

* Text Messaging, with Delivery Receipts (DLR)
* But *not* Mobile Origination (MO). 

## Technical Setup

Please contact Modica directly to setup your account.

You can call Lorelena Kulatea-Viki directly on +64 21 844 538 (email: lorelena@modicagroup.com), she is Head of Service Delivery at Modica, and she knows all about setting your account up. 

For delivery receipts to work, you need to inform Modica of the URL where they must send DLR's:

* DLR URL: https://yourtenancy.hourfleet.com:4431/api/sms/status/${messageId}/update?dlr=${dlr}


Once you have created you Modica account and confirmed that it's working using the Modica management tool which you will get from Modica, Hourfleet then requires that you provide the following information for your tenancy.

Please email the following details to: admin@mindkin.co.nz, and state your name and the name of your car sharing network.

* GatewayKey
* ShortCode
* Username
* Password

> These details are provided to you by Modica after creating your account.

The Hourfleet team will then complete the connection between your car sharing network and your Modica account.

## Additional Management Tools

Modica will also provide you a login to their site ([manage.runthered.com](https://manage.runthered.com)) so that you can monitor an track all your text messages, and configure your account.
