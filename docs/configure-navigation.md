---
layout: default
title: Configure Navigation.
---
# Navigation

This section determines how the user navigates between your website and your Hourfleet operational website.

There are many links in the app to pages that you will need to provide for users of your business, that cannot be provided by Hourfleet in the app. Such as: Terms Of Service, Privacy Policy, Company information, and legal documentation. These links are provided for your user's convenience.

These links can be seen at the bottom of page in the footer section.

If you don't want a link to be displayed, leave their values blank. The Terms of Service Url and Privacy Url are required.

~~~
	"Navigation": { // URL's that are linked to from your app to your own website 
		"HomeUrl": "http://www.yourcompany.com",
		"AboutUrl": "http://www.yourcompany.com/about",
		"DocsUrl": "http://www.yourcompany.com/docs",
		"TermsOfServiceUrl": "http://www.yourcompany.com/terms",
		"PrivacyUrl": "http://www.yourcompany.com/privacy",
		"FeesUrl": "http://www.yourcompany.com/fees",
		"FaqUrl": "http://www.yourcompany.com/faq",
		"ReturnUrl": "http://www.yourcompany.com",
		"SupportUrl": "http://www.yourcompany.com/support", // If defined (default is undefined), this URL will overide the navigation links to the support page Hourfleet automatically generates for you based on the values supplied in the Support Configuration section. 
		"ShowMobileAppLink": true,
		"UIElements": {
			"Invitation": { // Privacy statement about collecting their invitation data on the invitation page
				"Statement": "YourCompany values your privacy so we do not share this information with anyone else.",
				"DisplayStatement": true
			},
			"CriminalConviction": { // Compliance statement to accompany criminal conviction input.
			    	"Statement": "(other than traffic convictions) not subject to the 'clean slate scheme' under the Criminal Records (Clean Slate) Act 2004, or currently have a pending prosecution for a criminal offence (other than a traffic offence)?" 
				"DisplayStatement": true
			}
		}
	},
~~~

You can see an example of the links in the web app footer section here:

![Page Links](images/Footer.png)
