---
layout: default
title: What You Need to Provide
---
# What You Need to Provide

Setting up a new car sharing business can be complicated. There is much to think about besides having a web site and some cars. 
You are going to need to run a legitimate company in your geography, and worry about things like: Terms Of Service, Privacy Policies, Tier1 Support, Social Media, etc.

While the Hourfleet platform can provide many of the online tools to help manage your customers and car sharing, you are still going to need to sort out some commericial relationships with supporting businesses so that the platform automate most of the work for you.

These are the things that you need to do:

* Create a Merchant Account with your Bank
* *[New Zealand Network Operators]* - Create a PayStation account that can remit to your merchant bank account
* *[New Zealand Network Operators]* - Create a RunTheRed account, so that your customers can receive SMS TX message alerts, and so that your cars can be operated keylessly.
* Create a Terms Of Service agreement
* Create a Privacy Policy
* Create a front door website to inform and capture your customers, and a site that can lead your customers to register and use cars in your network.

# Paystation Details
*[New Zealand Network Operators Only]*
Once you have secured a Merchant Bank account, you can create an account with www.Paystation.co.nz.
You will be needing to create an account that gives you the ability to charge credit cards.

Hourfleet integrates with Paystation to collect and verify your customer's credit cards, using what is called a 3-party payment flow, using payment tokens.
Hourfleet does not capture nor store credit card information. Instead, Hourfleet hosts (in a web page iframe) a Paystation credit card form that Paystation provides, and all credit card details from your customers are handled directly by Paystation. 
PCI-DSS (Payment Card Industry Data Security Standard) is the set of rules that govern how businesses should handle customer credit card information, and Paystation is fully PCI compliant. 

Once you have created you Paystation account, Hourfleet requires that you provide the following information:

* GatewayId
* ApiKey
      
These are provided to your by Paystation after creating your account.
In addtion to making payments to your customers through the Hourfleet web site, Paystation provides you the ability to manually charge yoru customers using their website. This can be handy for resolving customer issues outside the scope of what Hourfleet can do for you.

# RunTheRed Details
*[New Zealand Network Operators Only]*

Hourfleet integrates with www.RunTheRed.co.nz as a text messaging gateway used by HourFleet for sending alerts to your customers, and instructions to the cars in your network.

You need to create your own accoutn with RunTheRed and obtain a shortcode so that Hourfleet can use this service.

Once you have created you RunTheRed account, Hourfleet requires that you provide the following information:

* GatewayKey
* ShortCode
* Username
* Password
