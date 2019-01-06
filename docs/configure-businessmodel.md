---
layout: default
title: Configure Business Model.
---
# Business Models

These settings decide how your car sharing business will actually operate. 

Supported models, settings, pricing, rules, rates, etc.

```
	"BusinessModel": {
	        "Settings":{
		    "Cars":{
		        "Types":["Car","SUV","Minivan","Truck"] // A list of vehicle types that are supported on the network
			"Licenses":{
				"Jurisdictions":{
					"Primary": "New Zealand" // The default jurisdiction for car license plates
					"Allowed": [
						"New Zealand" // Allowable jurisdictions for car license plates
					]
				},
				"Limits": {
                                    "Min": 6, // Minumum number of alpha-numeric characters (not including spaces)
                                    "Max": 6 // Maximum number of alpha-numeric characters (not including spaces)
                                },
			}
		    },
		    "Drivers":{
		    	"Licenses":{
				"Jurisdictions":{
					"Primary": "New Zealand" // The default jurisdiction for drivers license plates
					"Allowed": [
						"New Zealand" // Allowable jurisdictions for drivers license plates
					]
				}
			}
		    },
		    "Carkits":{
		        "IsSupported": true, // Do you want to support Keyless access on your network? or support only KeyExchange?
			"Enrolment": "ByOwner" // If "ByOwner", then any car owner will be allowed to enrole in fitting a carkit to their car. If "ByOperator", then operators will need to assign specific cars to be allowed to enrole in fitting a carkit.  
		    }
		},
	        "Insurance": {
		    "MaxValuedAt": 50000,
		    "MinValuedAt": 1000,
		},
		"Charges": "PerCar" | "None" // If "PerCar" then each car defines its own (hourly/daily/weekly) pricing. If "None" then there are no charges (booking, usage or overage) to use any car on this network.
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
					},
				},
				"Timing": {
					"FlagFallPeriodMinutes": 15, // A rental completed in less than this time, incurs no usage charge
					"MinimumActionBeforeStartPeriodMinutes": 15, // How soon before the rental starts can it not be manually approved, declined or pended. Auto-approvals can occur right up to the start date.
					"MinimumRequestPeriodMinutes": 30, // Minimum duration of a booking that can be requested
					"MaximumRequestPeriodMinutes": 20160, // Maximum duration of a booking that can be requested
					"UseBeforeStartPeriodMinutes": 15, //How long before the scheduled start time can the borrower start their rental (if the car is available). Also, how soon before the scheduled end time is the borrower allowed to start the booking, if they are late to start the rental. 
					"AutoCompleteAfterNoCompletionPeriodMinutes": 4320, // How long after the car is returned by borrower will it be auto-completed by Hourfleet on behalf of the owner
					"AutoCompleteAfterNoUsePeriodMinutes": 15, //How long before the scheduled end of the booking will it be auto-completed by Hourfleet, if the borrower has not started the rental. (i.e. a 'no show' scenario)
					"LateFees": {
						"GracePeriodMinutes": 15 // How long after the scheduled end time of the booking do late fees start accumulating.
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
					},
				},
				"Timing": {
					"FlagFallPeriodMinutes": 15, // A rental completed in less than this time, incurs no usage charge
					"ReservationPeriodMinutes": 15, // How long the car is reserved for the borrower to use before it expires and becomes available for others to reserve.
					"RejectionPeriodMinutes": 15, // How long after the car is reserved (or after it is used) can the borrower reject it and not be charged usage fees.
					"LateFees": {
						"GracePeriodMinutes": 15 // How long after the maximum usage, do late fees start accumulating.
					}
				}
			}
		}
	},
```

## Settings
These are various settings related to the business model of your car share network.

### Jurisdictions 
These are the licensing jurisdictions for both drivers licenses, and for car license plates. 

In either case, you need to define a 'Primary' (or home) jurisdiction (i.e. Colorado), and define one or more 'allowed' jurisdictions for your users to select from (i.e. any state of the United States).

The following wildcard tokens can be used as shortcuts for the 'Allowed':
* \*Canada - for all 13  provinces of canada
* \*United States - for all 50 states of the United States

### Car License Limits

Across all 'allowed' juridictions you will need to define the number of characters that are supported in its license plates.

### Carkits

Does your network support cars with carkits installed? If so, who has authority to 'enrol' in having a carkit.

Common examples: 
1. If your car share network is B2C, and you own your own cars, you may decide to use carkits, therefore you would only permit enrollment `Enrolement=ByOperator`.
2. If your car share network is P2P, you may allow car owners to register their own vehicles, but you may not permit carkits to be installed (`IsSupported=false`), forcing your borrowers and car owners to use manual 'KeyExchange'. 
3. If your car share network is P2P, you may allow any car owner to register their own carkit in their vehicle `Enrolement=ByOwner`.
4. Hybrids combinations are also possible.

## Insurance
As a car sharing business, whether your business owns the cars (B2C) or whether you allow your users to own cars (P2P) you are likely to have an insurer cover the cars when in use. If you work with an insurer and the conditions of insurance involve an insured value of the cars in your network, you will need to collect the insured value for each registered car.

In the registration of a car you can declare the Insure value of the car, and you can control the range of that declared value in the configuration. You do this by specifying the `MaxValuedAt` and `MinValuedAt` values.

## Ownership Models
As a car sharing business, you may support conventional car sharing (B2C) and "Peer-to-Peer" car sharing (P2P). 

Essentially, in a B2C model, the cars are owned by you the Network Operator, and typically there is no revenue sharing. That means that you get 100% of the revenue from your customers using your cars, less any revenue sharing you might have arranged with your insurer.

In a P2P model, the cars are owned by users on your network. Your customers own and manage and price their own cars. The revenue from  the rental is typically split between you and the car owner, and your insurer.

You will need to support either B2C or P2P or both. You do that by opting into the: `IsSupported` option for the ownership model you will support for your customers.

## Usage Models
Cars on your network can be rented using either the 'Scheduled' or 'Immediate' usage models.
Each one has its unique experience and rules. See more about usage models in [How It Works](howitworks.html).

Each usage model has its own pricing and timing rules. Cars can either be individually priced per hour/day/week or there is no charge for using any car.

In essence:

* 'Scheduled' is where cars are requested and booked ahead of time by a borrower, and the car owner (either B2C or P2P) has the option to approve and decline bookings depending on how they rate and trust the requesting borrower. Car owners declare when the car is available, the approve who can use it and when, and control how long the car is used for.

* 'Immediate' is where borrowers can walk up to car on the street and use it right away. There is no approval step required by the owner (either B2C or P2P). If the car is physically available it can be used. Borrowers can take the car for as long as they need it, the owner only becomes involved in the process if the car is rejected by the borrower (usually because the car is not in a acceptable condition to be used).

In either case, borrowers will be fully verified by you before being able to borrower any cars.

As a Network Operator, you are able to customize the timing parameters for these usage models, and determine their pricing models.
See more details about the Usage Models [How It Works](howitworks.html)

