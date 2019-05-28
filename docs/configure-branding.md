---
layout: default
title: Configure Branding
---
# Branding
These settings control the look and feel of your web app, and inlcude **important SEO information** for your customers and for marketing in internet search engines like Google. 
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
			"PrimaryColor": "#03e4ac", // The main highlight color of UI components such as buttons, menus etc
			"LinkColor": "#17c197", // The color of hyperlinks on all pages
			"TextColor": "#232c33", // The color of text on all pages
			"BkColor": "#ecf0f1", // The background color of the main pages
			"FooterBkColor": "#ecf0f1", // The color of the footer section at the bottom of each page.
			"Navigation": {
				"HoverColor": "#03e4ac", // The background color under the mouse in menus
				"BkColor": "#324359" // The background color of menus
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
			"DesktopImageUrl": "http://www.yourcompany.com/Images/logo_navbar.png", // Image at top of every page in desktop sizes, and used in all email notifications. 
			"MobileImageUrl": "http://www.yourcompany.com/Images/logo_navbar_mobile.png", // Image at top of every page in on mobile devices.
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

## SEO (Search Engine Optimization)

All web applications need to provide sufficient metadata for Search Engine Optimization (SEO) for web crawlers such as Google to help get your business found. 

Also, your Hourfleet operational website needs to provide the right metadata so that and when people share their experience with social media applications (like slack, facebook and twitter), the right information is displayed in the preamble of their post by default.

## Images

All images must be hosted on your own web sites, and access to those images must be public (without authentication).

**HTTPS Access:** Prefer links to images that are accessible over HTTPS (https://) to avoid browser imposed issues displaying non-secure images from your secure Hourfleet site.

**Keep Them Small:** Images can be very large in data size (i.e. bytes). We recommend that all images are as close to their minimum sizes (listed below) otherwise they will make your users experience in the App much slower, particularly on mobile phones.
> Note: All image sizes can be provided in higher values as long as their aspect ratios remain the same.

**Contrast:** consider that your images will be presented against the colors that you choose in the 'Styles' section. Use a transparent background, and anti-aliasing for those background colors. We recommend that you test your images on the site and optimize the presentation from there.

### Image Sizes

| Seo                 | Size                                     |
| ---------------------- | ---------------------------------------- |
| ImageUrl (logo.jpeg)              | 200px X 200px                            |



| Images                 | Size                                     |
| ---------------------- | ---------------------------------------- |
| DesktopImageUrl (logo_navbar.png)        | 30px High and at least 30px wide (Image can be wider to include a rectangular logo |
| MobileImageUrl (logo_navbar_mobile.png) | 30px High and at least 30px wide (Image can be wider to include a rectangular logo |
| FavIconUrl (favicon.ico) | 190px X 190px
| BusyInlineUrl (loader_inline.gif) | minimum 50px x 50px. Image must be square but if larger will be sized down |
| BusyPageUrl (loader_page.gif) | minimum 100px x 100px. Image must be square but if larger will be sized down |
| BusyButtonUrl (loader_button.gif) | minimum 50px x 50px. Image must be square but if larger will be sized down |



| Mobile                 | Size                                     |
| ---------------------- | ---------------------------------------- |
| IconUrl (mobile.png)   | 72px X 72px                              |
| Icon???Url             | (self describing)                        |


> Note: You must specify both `Icon192Url` and `Icon512Url` to enable the installable app features for your mobile users
