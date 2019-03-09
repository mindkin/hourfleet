---
layout: default
title: Configure Navigation.
---
# Navigation

This section determines how the user navigates between your marketing website and your Hourfleet car share service.

### Forward - From your marketing site to your Hourfleet Car Share service  
You have complete editorial control over your marketing site. This gives your marketing people plenty of scope to present your brand and proposition is a way that best connects with your target market. As a minimum you'll probably want to publish FAQ's, About Us, Terms of Service and several others. Have a look at the next section ('Reverse') below for clues as to the types of pages you may want to publish.  

In addition, you can send customers and visitors forward into your Hourfleet car share service via a number of urls. They are:
- https://\<yourname\>.hourfleet.com/signin. Used to start a visitor on the signup journey   
- httsp://\<yourname\>.hourfleet.com/invite. Used to direct a customer to the signin page  
- httsp://\<yourname\>.hourfleet.com/search. Used to present a visitor with a map highlighting your car locations  


### Reverse - From your Hourfleet car share service to your marketing site
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




