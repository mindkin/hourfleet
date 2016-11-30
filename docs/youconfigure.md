---
layout: default
title: What You Can Configure
---
# What You Can Configure

When you join Hourfleet, you are going to get your own hosted "Operational" car sharing web site at an address like: *https://yourcompany.hourfleet.com*.

That site will be customized for your customers to look and feel like your business. But there are a few things you need to tell us so that it works like your business.
You can see this "Operational Site" and the other things you are going to get at [What Is In The Box](inthebox.html)

# What Is A Network Operator?
To Hourfleet you (and your business) are known as a "Network Operator", since you operate a car sharing network on the Hourfleet platform. 

As a Network Operator you are likely to have many things unique to your business, such as: your own brand, your own social media presense, and different rules about how your price and charge your customers for sharing cars on your network. 

You probably already have your own website for your business that is focused upon capturing new customers and providing that all important front door to your business, to turn interested brwosers into paying customers. You'll want to keep that website, so Hourfleet will extend your website to provide all the tools you and your customers need to run your car sharing business.

## Your Configuration
But first we need to know some stuff about how you want Hourfleet to run your business for you.

~~~
{
	"Support": { // Displayed on the support page of your operational site, and various places that reference support/assistance
		"Guidance": "If there is an issue with a car during your booking we  recommend first contacting the owner. You can find their contact information under the owner section of your booking",
		"Social": {
			"Facebook": {
				"Url": "https://www.facebook.com/acmeride/"
			},
			"Twitter": {
				"Url": "https://twitter.com/acmeride"
			},
			"LinkedIn": {
				"Url": "https://www.linkedin.com/company/acmeride"
			},
			"Instagram": {
				"Url": "https://www.instagram.com/acmeride"
			},
			"Blog": {
				"Url": "https://acmeride.wordpress.com"
			},
			"Other": {
				"Url": ""
			}
		},
		"Company": {
			"Name": "Acmeride Limited",
			"PhoneNumber": "0800-555-1212",
			"Email": "support@acmeride.co.nz",
			"Address": {
				"Street1": "99 One Acmeride Way",
				"Street2": "",
				"Town": "Acmeville",
				"Jurisdiction": "New Zealand"
			}
		},
		"Insurer": {
			"Guidance": "To lodge a claim please contact our insurer directly. You will need to provide them with a completed insurance claim form.",
			"Name": "Acme Insurance",
			"ClaimForm": {
				"Title": "",
				"Url": "http://www.acmerides.com/Docs/insurance_claim_form.pdf"
			},
			"PhoneNumber": "0800-555-1212",
			"Email": "claims@acmeinsurance.co.nz"
		},
		"LiveChat": {
			"FreshDesk": {
				"ApiKey": "xxxxx",
				"Settings": "BASE64ENCODEDSTRING"
			},
			"Intercom": {
				"ApiKey": "xxxxx",
			},
		}
	},
	"Branding": {
		"Name": {
			"Singular": "Acme", // The name used all over the App
			"Plural": "Acme",
			"Possessive": "Acme's"
		},
		"Seo": { // used primarily in SEO attributes, and for open graph information (http://ogp.me/)
			"Title": "Acme",
			"ImageUrl": "http://www.acmerides.com/Images/logo.jpeg",
			"Description": "Acme connects people who need a car with people who have a car that's sometimes idle.",
			"SiteName": "Acme Car Sharing",
			"Url": "http://www.acmerides.com"
		},
		"Styles": { // The colors used to brand your operational site
			"PrimaryColor": "#03e4ac",
			"LinkColor": "#17c197",
			"TextColor": "#232c33",
			"BkColor": "#ecf0f1",
			"FooterBkColor": "#ecf0f1",
			"Navigation": {
				"HoverColor": "#03e4ac",
				"BkColor": "#324359"
			}
		},
		"Social": { // Links to your social apps
			"Facebook": {
				"Url": "https://www.facebook.com/acmeride/"
			},
			"Twitter": {
				"Url": "https://twitter.com/acmeride"
			},
			"LinkedIn": {
				"Url": "https://www.linkedin.com/company/acmeride"
			},
			"Instagram": {
				"Url": "https://www.instagram.com/acmeride"
			},
			"Blog": {
				"Url": "https://acmeride.wordpress.com"
			},
			"Other": {
				"Url": ""
			}
		},
		"Images": {
			"DesktopImageUrl": "http://www.acmerides.com/Images/logo_navbar.png", // Image at top of every page in desktop sizes
			"MobileImageUrl": "http://www.acmerides.com/Images/logo_navbar_mobile.png", // Image at top of every page in mobile sizes
			"FavIconUrl": "http://www.acmerides.com/Images/favicon.ico",
			"BusyInlineUrl": "http://www.acmerides.com/Images/loader_inline.gif", // Used to display progress for individual actions
			"BusyPageUrl": "http://www.acmerides.com/Images/loader_page.gif", // Used to display progress for whole pages
			"BusyButtonUrl": "http://www.acmerides.com/Images/loader_button.gif" // Used to display progress on certain buttons
		},
		"Mobile": {
			"Ios": { // Images used to create a native app on your iPhone home screen
				"IconUrl": "http://www.acmerides.com/Images/apple-icon.jpg",
				"Icon72Url": "http://www.acmerides.com/Images/apple-icon.jpg",
				"Icon114Url": "http://www.acmerides.com/Images/apple-icon.jpg",
				
			},
			"Android": { // Images used to create a native app on your Android home screen
				"Icon72Url": "http://www.acmerides.com/Images/android-icon.jpg",
				"Icon192Url": "http://www.acmerides.com/Images/android-icon.jpg",
				
			}
		}
	},
	"Navigation": { // URL's that are linked to from your operational site to your own website 
		"HomeUrl": "http://www.acmerides.com",
		"AboutUrl": "http://www.acmerides.com/about",
		"ContactUrl": "http://www.acmerides.com/contact",
		"DocsUrl": "http://www.acmerides.com/docs",
		"TermsOfServiceUrl": "http://www.acmerides.com/terms",
		"PrivacyUrl": "http://www.acmerides.com/privacy",
		"FeesUrl": "http://www.acmerides.com/fees",
		"FaqUrl": "http://www.acmerides.com/faq",
		"ReturnUrl": "http://www.acmerides.com"
	},
	"BusinessModel": {
	        "Insurance": {
		    "MaxValuedAt": 50000,
		    "MinValuedAt": 1000,
		},
		"Ownership": {
			"P2P": {
				"IsSupported": true, // Will you support your customers registering their own cars on your network?
				"Revenue": {
					"OperatorShareRate": 0.20, // Percentage of revenue your business takes from a P2P rental
					"Insurer": {
						"ShareRate": 0.20, // Percentage of revenue your insurer takes from a P2P rental
						"MinDailyInsurancePremium": 7.20, // Minimums your insurer might define
						"MinHourlyInsurancePremium": 1.60,
						"MinInsurancePremium": 1.60,
						"MinWeeklyInsurancePremium": 36.0
					}
				}
			},
			"B2C": {
				"IsSupported": false, // Will you provide your own cars on your network?
				"Revenue": {
					"OperatorShareRate": 1.0, // Percentage of revenue your business takes from a B2C rental
					"Insurer": {
						"ShareRate": 0, // Percentage of revenue your insurer takes from a B2C rental
						"MinDailyInsurancePremium": 0, // Minimums your insurer might define
						"MinHourlyInsurancePremium": 0,
						"MinInsurancePremium": 0,
						"MinWeeklyInsurancePremium": 0
					}
				}
			}
		},
		"Usage": {
			"Scheduled": { // Cars that can be scheduled for using the 'BookLater' usage model
				"Pricing": {
					"ReservationFee": 3, // Fee payable once a reservation is approved by the car owner
					"LateFees": {
						"MaxLateFeeCap": 500, // No matter how late, the total late fees cannot exceed this amount
						"PerInstance": 50, // One-off flat fee per late return
						"PerMinute": 1 // Per minute after a late return
					}
				},
				"Timing": {
					"FlagFallPeriodMinutes": 15, // A rental completed in less than this time, incurs no usage charge
					"MinimumActionBeforeStartPeriodMinutes": 15, // How soon before the rental starts can it not be approved, declined or extended anymore
					"MinimumRequestPeriodMinutes": 30, // Minimum size of a reservation
					"UseBeforeStartPeriodMinutes": 15, //How long before the scheduled time can the next borrower start their reservation if the car is ready and waiting for them
					"AutoCompleteAfterNoCompletionPeriodMinutes": 4320, // How long after the car is returned by borrower will it be auto-completed by the system on behalf of the owner
					"AutoCompleteAfterNoUsePeriodMinutes": 15, //How long before the end of the reservation will the rental be auto-completed by the system on behalf of the borrower, if they havent started the rental.
					"LateFees": {
						"GracePeriodMinutes": 15 // How long after the car is due back, that late fees start accumulating
					}
				}
			},
			"Immediate": { // Cars that require no booking ahead of time and use the 'TakeNow' usage model
				"Pricing": {
					"ReservationFee": 0, // Fee payable once a car is reserved by the borrower
					"LateFees": {
						"MaxLateFeeCap": 500, // No matter how late, the total late fees cannot exceed this amount
						"PerInstance": 50, // One-off flat fee per late return
						"PerMinute": 1 // Per minute after a late return
					}
				},
				"Timing": {
					"FlagFallPeriodMinutes": 15, // A rental completed in less than this time, incurs no usage charge
					"ReservationPeriodMinutes": 15, // How long the car is reserved for the borrower to use before it expires and becomes available for others to reserve
					"RejectionPeriodMinutes": 15, // How long after the car is reserved (or after it is used) can the borrower reject it and not be charged usage fees
					"LateFees": {
						"GracePeriodMinutes": 15 // How long after the maximum usage, that late fees start accumulating
					}
				},
				"Display": {
					"DisplayDurations": "false" // Whether to display the duration of use instead of the costs of use
				}
			}
		}
	},
	"Settings": {
		"SiteUrl": "https://acmeride.hourfleet.com", // URL of your operational site
		"TimeZone": "New Zealand Standard Time", // Timezone of your users
		"Locale": "en-NZ" // Locale of your users
	}
}
~~~

### Support
As a car sharing business, you will need to provide your customers with various support channels. This section defines those channels.

#### LiveChat
This section defines the LiveChat widgets that Hourfleet supports. Currently, FreshDesk.com or Intercom.io.
You will need to signup for an account with either of these providers. 

You cannot configure to have LiveChat for both, chose one or the other or neither.

##### FreshDesk.com
Once you have signed up and selected a plan that includes LiveChat, you will need to provide your: 'ApiKey' and 'Settings', which can be obtained from the 'Admin' console of your freshdesk subscription.

* Login to your freshdesk site: https://yourname.freshdesk.com
* Click on the 'LiveChat' icon

![](images/FreshDesk-Console-LiveChat.png)

* Make sure Live Chat is 'enabled'
* Make sure your app is enabled.
* Click on the 'Edit' button to the right of your app
* Click on the 'Widget Code' tab
* In the javascript they provide, you need to find and extract the value of the URL that looks like this: 'https://xxxxxxxxxxx.cloudfront.net'. The xxxxxxxx part is your 'ApiKey'
* Now, find the value of the 'window.livechat_setting='xxxxxxxxxxxxxxxxxxxxxxxxx....'. The large blob of text between the quotations marks is the value of your 'Settings' (not including the quotation marks).

##### Intercom.io

Once you have signed up and selected a plan that includes Intercom 'Acquire', you need toprovide your 'ApiKey', which can be obtained form the 'App Settings' console of your Intercom subscription.

* Login to Intercom at: https://app.intercom.io
* Click on your avatar (bottom left-hand corner of page) and click 'App Settings'

![](images/Intercom-Console-AppSettings.png)

* Click on the 'API Keys' menu (to the left)
* The 'APP ID" is the value of your 'ApiKey'

### Branding
This section provides the basic look and feel of your Hourfleet operational site, so that it looks and feels like a natural extension of your main website.

#### SEO
All web applications need to provide sufficient metadata for Search Engine Optimization (SEO) for web crawlers such as google to help get your business found. Also, your Hourfleet operational website needs to provide the right metadata so that and when people share their experience with social media applications (like facebook and twitter), the right information is displayed in their post by default.

### Navigation
This section determines how the user navigates between your website and your Hourfleet operational website.

There are many links on the operational site to pages that you need to provide for users of your business, that cannot be provided by the operational site generically. Such as: Terms Of Service, Company information, and legal documentation.


### Business Models

#### Insurance
As a car sharing business, whether your business owns the cars (B2C) or whether you allow your users to own cars (P2P) you are likely to have an insurer cover the cars when in use. If you work with an insurer and the conditions of insurance involve an insured value of the cars in your network, you will need to collect the insured value for each registered car.

In the registration of a car you can declare the Insure value of the car, and you can control the range of that declared value in the configuration. You do this by specifying the `MaxValuedAt` and `MinValuedAt` values.

#### Ownership Models
As a car sharing business, you may support conventional car sharing (B2C) and "Peer-to-Peer" car sharing (P2P). 

Essentially, in a B2C model, the cars are owned by you the Network Operator, and typically there is no revenue sharing. That means that you get 100% of the revenue from your customers using your cars, less any revenue sharing you might have arranged with your insurer.

In a P2P model, the cars are owned by users on your network. Your customers own and manage andd price their own cars. The revenue from  the rental is typically split between you and the car owner, and your insurer.

You will need to support either B2C or P2P or both. You do that by opting into the: `IsSupported` option for the ownership model you will support for your customers.

#### Usage Models
Cars on your network can be rented using either the 'Scheduled' or 'Immediate' usage models. 
Each one has its unique experience and rules. See more about usage models in [How It Works](howitworks.html).

In essence:

* 'Scheduled' is where cars are requested and booked ahead of time by a borrower, and the car owner (either B2C or P2P) has the option to approve and decline bookings depending on how they rate and trust the requesting borrower. Car owners declare when the car is available, the approve who can use it and when, and control how long the car is used for.

* 'Immediate' is where borrowers can walk up to car on the street and use it right away. There is no approval step required by the owner (either B2C or P2P). If the car is physically available it can be used. Borrowers can take the car for as long as they need it, the owner only becomes involved in the process if the car is rejected by the borrower (usually becuase the car is not in a acceptable condition to be used).

In either case, borrowers will be fully verified by you before being able to borrower any cars.

As a Network Operator, you are able to customize the timing parameters for these usage models, and determine their pricing models.
See more details about the Usage Models [How It Works](howitworks.html)
