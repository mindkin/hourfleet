---
layout: default
title: What You Can Configure
---
# What You Can Configure

When you join Hourfleet, you are going to get your own hosted "Operational" car sharing web site at an address like: *https://acmerides.hourfleet.com*.

That site will be customized for your customers to look like your business. But there are a few things you need to tell us so that it looks and works like your business.
You can see this "Operational Site" and the other things you are going to get at [What Is In The Box](inthebox.html)

# What Is A Network Operator?
To Hourfleet you (and your business) are known as a "Network Operator", since you operate a car sharing network on Hourfleet. 
As a Network Operator you are likely to have many things unique to your business, such as: your own brand, your own social media presense, and different rules about how your charge your customers for sharing cars on your network

You probably already have a website for your business that is focused upon capturing new customers and providing front door to your business. You'll want to keep that website, so Hourfleet will extend your website to provide all the tools you and your customers need to run your car sharing business.

But first we need to know some stuff about your business.

## Your Configuration
As a Network Operator, we need to know the following information about your business:

~~~
{
	"Support": {
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
		}
	},
	"Branding": {
		"Name": {
			"Singular": "Acme",
			"Plural": "Acme",
			"Possessive": "Acme's"
		},
		"Seo": {
			"Title": "Acme",
			"ImageUrl": "http://www.acmerides.com/Images/logo.jpeg",
			"Description": "Acme connects people who need a car with people who have a car that's sometimes idle.",
			"SiteName": "Acme Car Sharing",
			"Url": "http://www.acmerides.com"
		},
		"Styles": {
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
		"Images": {
			"DesktopImageUrl": "http://www.acmerides.com/Images/logo_navbar.png",
			"MobileImageUrl": "http://www.acmerides.com/Images/logo_navbar_mobile.png",
			"FavIconUrl": "http://www.acmerides.com/Images/favicon.ico",
			"BusyInlineUrl": "http://www.acmerides.com/Images/loader_inline.gif",
			"BusyPageUrl": "http://www.acmerides.com/Images/loader_page.gif",
			"BusyButtonUrl": "http://www.acmerides.com/Images/loader_button.gif"
		},
		"Mobile": {
			"Ios": {
				"IconUrl": "http://www.acmerides.com/Images/apple-icon.jpg",
				"Icon72Url": "http://www.acmerides.com/Images/apple-icon.jpg",
				"Icon114Url": "http://www.acmerides.com/Images/apple-icon.jpg",
				
			},
			"Android": {
				"Icon72Url": "http://www.acmerides.com/Images/android-icon.jpg",
				"Icon192Url": "http://www.acmerides.com/Images/android-icon.jpg",
				
			}
		}
	},
	"Navigation": {
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
		"Ownership": {
			"P2P": {
				"IsSupported": true,
				"Revenue": {
					"OperatorShareRate": 0.20,
					"Insurer": {
						"ShareRate": 0.2,
						"MinDailyInsurancePremium": 7.20,
						"MinHourlyInsurancePremium": 1.60,
						"MinInsurancePremium": 1.60,
						"MinWeeklyInsurancePremium": 36.0
					}
				}
			},
			"B2C": {
				"IsSupported": false,
				"Revenue": {
					"OperatorShareRate": 0,
					"Insurer": {
						"ShareRate": 0,
						"MinDailyInsurancePremium": 0,
						"MinHourlyInsurancePremium": 0,
						"MinInsurancePremium": 0,
						"MinWeeklyInsurancePremium": 0
					}
				}
			}
		},
		"Usage": {
			"Scheduled": {
				"Pricing": {
					"ReservationFee": 3,
					"LateFees": {
						"MaxLateFeeCap": 500,
						"PerInstance": 50,
						"PerMinute": 1
					}
				},
				"Timing": {
					"FlagFallPeriodMinutes": 15,
					"MinimumActionBeforeStartPeriodMinutes": 15,
					"MinimumRequestPeriodMinutes": 30,
					"UseBeforeStartPeriodMinutes": 15,
					"AutoCompleteAfterNoCompletionPeriodMinutes": 4320,
					"AutoCompleteAfterNoUsePeriodMinutes": 15,
					"LateFees": {
						"GracePeriodMinutes": 15
					}
				}
			},
			"Immediate": {
				"Pricing": {
					"ReservationFee": 0,
					"LateFees": {
						"MaxLateFeeCap": 500,
						"PerInstance": 50,
						"PerMinute": 1
					}
				},
				"Timing": {
					"FlagFallPeriodMinutes": 15,
					"ReservationPeriodMinutes": 15,
					"RejectionPeriodMinutes": 15,
					"LateFees": {
						"GracePeriodMinutes": 15
					}
				}
			}
		}
	},
	"Settings": {
		"SiteUrl": "https://acmeride.hourfleet.com",
		"TimeZone": "New Zealand Standard Time",
		"Locale": "en-NZ"
	}
}
~~~

### Business Models
As a car sharing business, you may support conventional car sharing (B2C) and "Peer-to-Peer" car sharing (P2P). 

Essentially, in a B2C model, the cars are owned by the Network Operator, and typically there is no revenue sharing.

In a P2P model, the cars are owned by users on the network, and revenue is typically shared between the operator and the car owner.

In either model, you may have to revenue share with your insurance company.

You will need to support either B2C or P2P or both. You do that by setting the: `IsSupported` option for the model you will support for your customers.

### Usage Models
Cars on your network can be rented using either the 'Scheduled' or 'Immediate' usage models. 
Each one has its unique flow and rules. See more about usage models in [How It Works](howitworks.html).

'Scheduled' is where cars are booked ahead of time by a borrower, and the car owner (either B2C or P2P) has the option to approve and decline bookings depending on how they rate and trust the requesting borrower.

'Immediate' is where borrowers walk up to cars on the street and 'take' them straight away. There is no pre-approval step.
In either case, borrowers must be pre-verified before being able to borrower cars.

As a Network Operator, you are able to customize the timing parameters for these usage models, and determine their pricing models.
See more details about the Usage Models [How It Works](howitworks.html)
