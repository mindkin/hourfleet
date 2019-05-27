---
layout: default
title: Configure Branding.
---
# Branding
These settings control the look and feel of your web app, and important SEO information for your customers and marketing in internet search engines like Google. 
~~~	
	"Branding": {
		"Name": {
			"Singular": "Acme", // The name used all over the App
			"Plural": "Acme",
			"Possessive": "Acme's"
		},
		"Seo": { // used primarily in SEO attributes, and for open graph information (http://ogp.me/)
			"Title": "Acme",
			"ImageUrl": "http://www.yourcompany.com/Images/logo.jpeg",
			"Description": "Acme connects people who need a car with people who have a car that's sometimes idle.",
			"SiteName": "Acme Car Sharing",
			"Url": "http://www.yourcompany.com"
		},
		"Styles": { // The colors used to brand your app
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
				"Url": "https://www.facebook.com/yourcompany/"
			},
			"Twitter": {
				"Url": "https://twitter.com/yourcompany"
			},
			"LinkedIn": {
				"Url": "https://www.linkedin.com/company/yourcompany"
			},
			"Instagram": {
				"Url": "https://www.instagram.com/yourcompany"
			},
			"Blog": {
				"Url": "https://yourcompany.wordpress.com"
			},
			"Other": {
				"Url": ""
			}
		},
		"Images": {
			"DesktopImageUrl": "http://www.yourcompany.com/Images/logo_navbar.png", // Image at top of every page in desktop sizes
			"MobileImageUrl": "http://www.yourcompany.com/Images/logo_navbar_mobile.png", // Image at top of every page in mobile sizes
			"FavIconUrl": "http://www.yourcompany.com/Images/favicon.ico",
			"BusyInlineUrl": "http://www.yourcompany.com/Images/loader_inline.gif", // Used to display progress for individual actions
			"BusyPageUrl": "http://www.yourcompany.com/Images/loader_page.gif", // Used to display progress for whole pages
			"BusyButtonUrl": "http://www.yourcompany.com/Images/loader_button.gif" // Used to display progress on certain buttons
		},
		"Mobile": { // Images used to create a native app on your iPhone/Android home screen from the progressive web app. You will need to define at least the Icon192Url and Icon512Url to enable these features for your users
			"IconUrl": "http://www.yourcompany.com/Images/mobile.png", // used by iPhone 
			"Icon72Url": "http://www.yourcompany.com/Images/mobile72x72.png", // used by iPhone and Android
			"Icon114Url": "http://www.yourcompany.com/Images/mobile114x114.png", // used by iPhone 
			"Icon192Url": "http://www.yourcompany.com/Images/mobile192x192.png", // used by Android
			"Icon256Url": "http://www.yourcompany.com/Images/mobile256x256.png", // used by Android
			"Icon384Url": "http://www.yourcompany.com/Images/mobile384x384.png", // used by Android
			"Icon512Url": "http://www.yourcompany.com/Images/mobile512x512.png", // used by Android
		}
	},
~~~

## Image Sizes
All images can be provided in higher values as long as their aspect ratios remain the same.

| Seo                 | Size                                     |
| ---------------------- | ---------------------------------------- |
| logo.jpeg              | 200px X 200px                            |

| Images                 | Size                                     |
| ---------------------- | ---------------------------------------- |
| logo_navbar.png        | 30px High and at least 30px wide (Image can be wider to include a rectangular logo |
| logo_navbar_mobile.png | 30px High and at least 30px wide (Image can be wider to include a rectangular logo |
| favicon.ico | 190px X 190px
| loader_inline.gif | minimum 50px x 50px. Image must be square but if larger will be sized down |
| loader_page.gif | minimum 100px x 100px. Image must be square but if larger will be sized down |
| loader_button.gif | minimum 50px x 50px. Image must be square but if larger will be sized down |

| Mobile                 | Size                                     |
| ---------------------- | ---------------------------------------- |
| mobile.png             | 72px X 72px                              |
| Other images           | (self describing)                        |

> Note: You must specify both `Icon192Url` and `Icon512Url` to enable the installable app features for your mobile users

## SEO
All web applications need to provide sufficient metadata for Search Engine Optimization (SEO) for web crawlers such as Google to help get your business found. Also, your Hourfleet operational website needs to provide the right metadata so that and when people share their experience with social media applications (like facebook and twitter), the right information is displayed in their post by default.
