---
layout: default
title: Data & Security Policies
---

This policy is applied to security and data protection supplied by the Hourfleet platform for data that is managed for the platform and for any data managed on behalf of all Hourfleet network operators.

# Data & Security Policy 

The Hourfleet platform is composed of a number of HTTP services and worker processes hosted in the cloud, or devices deployed into cars. Hourfleet's customers and their end-users, as well as devices, applications and user agents all send data over the internet by using any HTTP client. 

All data is confidential, and is encrypted end to end in transit over secure TLS protocol using HTTPS.

All data that flows between any client and Hourfleet is destined either for the use of the Hourfleet platform (eg. for operation, configuration, management or auditing purposes) or for the use of each tenant on the Hourfleet platform (eg. for car sharing or customer data for operating a car sharing business).

Customers of Hourfleet that license the Hourfleet platform become tenants operating on the Hourfleet platform.

# Data Protection

### Data Stores

Each Hourfleet tenant will have deployed a *dedicated* data store (Azure Storage Account) provisioned for it (in the Microsoft Azure cloud) in a geographic region of the tenants choice. This means that each tenant on the Hourfleet platform has a physically separate data store that is secured by unique access keys only accessible by that tenant, in order to limit any security breaches of any single tenant.

>  Azure Table Storage, Azure Queue Storage and Azure Blob Storage are not centralized databases like say: SQL Server, but rather a distributed data service, that maintains very high scalability and availability in of themselves.

The primary region for the tenancy will be located closest to the main volume of end-users for that tenancy. The choice is largely influenced by the need to reduce network latency between the end users agents and the Hourfleet platform.

The data stored in the primary region is replicated in a secondary region, generally adjacent to or close to the primary region. See Azure documentation for more details on [GRS cross-regional replication](https://docs.microsoft.com/en-us/azure/storage/common/storage-redundancy-grs).

All access to all data stored in any Azure Storage Account will be securely encrypted via HTTPS, and limited to direct access only by services in the Hourfleet architecture. Access Keys to this storage account are also stored in physically separate key vaults. See [Secrets](#Secrets) below. Direct access to these data stores is permitted via HTTPS to Hourfleet support staff.

All transactional data for the purposes of managing a tenants car sharing network will be stored in these Data Stores.

### Caching

Hourfleet uses numerous caches at various layers in its architecture for storing a variety of transient data, that typically decays with time, and is periodically updated.

There will be a single dedicated in-memory cache provider (Redis Server) per geographic region, shared by all tenants in residence in that region.

All access to all data stored in Redis will be securely encrypted via HTTPS, and limited to direct access by only components in the Hourfleet architecture. Access Keys to this caching service are also stored in physically separate key vaults. See [Secrets](#Secrets) below. Direct access to these data stores is permitted via HTTPS to Hourfleet support staff.

### Configuration

Hourfleet manages a vast collection of configuration for numerous tenants in a single deployment in a single geographic region. It manages the separate configuration of each tenant on the platform with the aid of a collection of configuration for the whole platform.

These configuration sets are stored in a separate data store dedicated to the Hourfleet platform only. There is no access to this store from any tenant on the platform. Direct access to these data stores is permitted to Hourfleet support staff.

All access to all data stored in this dedicated Azure Storage Account will be securely encrypted via HTTPS, and limited to direct access by only components in the Hourfleet architecture. Access Keys to this storage account are also stored in a platform dedicated Azure Key Vault. See [Secrets](#Secrets) below. Direct access to these data stores is permitted via HTTPS to Hourfleet support staff.

### Secrets

Hourfleet maintains a collection of confidential and sensitive configuration data used for the platform and for numerous tenants in a single deployment in a single geographic region. It also manages secure access and connections to numerous 3rd party services, including those within its own internal architecture (i.e. data stores, caches, etc). 

As such, it has to manage numerous secrets (e.g. account credentials) in order to protect the confidentiality of its tenants and any data flowing to and from the Platform.

Hourfleet stores all secrets in dedicated Azure Key Vaults. Data stored in an Azure Key Vault is replicated in a secondary region. See [Azure Key Vault Redundancy](https://docs.microsoft.com/en-us/azure/key-vault/key-vault-disaster-recovery-guidance) for more information.

Each tenant within a geographic region will have provisioned for it a *dedicated* Azure Key Vault in order to limit any security breaches of any single tenant. There is also a dedicated Key Vault for the platforms own exclusive use.

All access to Azure Key Vault will be secured via HTTPS. All access to all secrets by Hourfleet is limited to read-only access to all secrets and keys, from a dedicated account specific to the specific tenant. Direct access to these data stores is permitted via HTTPS to Hourfleet support staff.

### Access to Tenancy Data

All transactional data (i.e user accounts, audits, car sharing data) is permanently stored in dedicated and separate Azure storage accounts for each tenant in any geographic region. That data store is secured by protected access keys.

Access to these stores is necessary for the Hourfleet platform to operate.

Sometimes it becomes necessary for tenants to gain direct access to their data to satisfy internal policies, audits, reporting etc.

Read-only access to these stores will be offered to individual tenants upon written request to support@hourfleet.com. Upon which a read-only time limited key will be issued.

Tenants will not be permitted to change, update, delete or otherwise alter the data in these stores, and so not risk affecting the data integrity of their own tenancy.

## Data Retention

Upon the creation of an Hourfleet tenancy, various Azure components are automatically provisioned and configured. Each of these components has a separate data retention policy applied to it.

Platform Data - With the exception of data stored for individual tenants, all other data will be retained for as long as the platform operates in any specific geographic region. Tenant specific data (i.e. network configuration settings) will be retained for as long as the network remains on the platform.

Tenant Transactional Data - Tenant specific data (including all car sharing data, user accounts, audits, logs etc.) will be retained for as long as the network remains on the platform.

Cached Tenant Data - Any tenant specific cached data required while operating the tenants network, will be retained for as long as the network remains on the platform, or until it expires and is automatically removed from the caches.

## Personally Identifiable Information

Hourfleet captures, transports and stores PII data in various forms.

Examples of PII that Hourfleet captures and stores:

* Email addresses
* Mobile phone numbers
* Drivers licenses
* Profile Photos
* Bank account numbers
* Certificates of road worthiness
* Car license number plates and VIN numbers

All PII data will be captured and transported securely, and will be stored securely in data repositories specific to the tenant where the data was captured.

Hourfleet must sanitize all PII data returned from all API responses so that this confidential information is not inadvertantly revealed unintentionally to any external party, except the owner of the PII data or a trusted recipient of that data for the purposes of operating the car sharing network. 

For example: if a user requests their own user profile from Hourfleet, the response from Hourfleet may contain certain PII data of theirs (i.e. their email address, drivers license). However, if a user requests another users' profile, all unnecessary PII data will be removed from the response. 

> Note: In some cases, certain PII data must be shared between certain users in certain circumstances during normal operations. For example, the email address and phone number of a car owner might need to be shared with the borrower of their car for the purposes of directly contacting them in an emergency situation while using the car. Hourfleet, ensures that this data is kept confidential between these parties. 

### PCI Compliance

Hourfleet is **not** [Payment Card Industry Data Security Standards](https://www.pcisecuritystandards.org/security_standards) (PCI DSS) compliant.

Hourfleet **does not** directly capture nor store credit card information provided by any user.

Hourfleet will integrate with, and delegate to, trusted payment providers such as [Stripe.com](www.stripe.com) to gather and store credit card information on behalf of all users of the platform. Hourfleet will instruct those payment providers to manage and charge all users credit cards.


# Auditing

The Hourfleet platform has been designed for operational monitoring, with a built in capability for detailed diagnostics, and reporting.

All activities in the Hourfleet platform that result in any change in state of *any* data will be logged and those logs stored according to the data retention policy for logs.

Many business critical activities (such as: registering new users, booking cars, etc.) will also be audited separately and stored historically to prevent future repudiation by the initiating party. 

Numerous activities with any interest in security or performance impact will also measured (eg. the number of failed attempts to access an account). Metrics and counters will also collected for measuring usage, and performance, useful for A->B testing and other learning reasons.

Any faults or crashes that are experienced by any tenant on the platform and by the platform itself will also be audited permanently.

Depending on the source of the information, this logged data will either be stored in the tenancy storage where the activity took place, or in platform storage (i.e. crash reports, performance counters etc.) or both.

# Authentication and Administration

Access to all APIs in the Hourfleet backend will be secured via HTTPS.

Access to all API's that identify a specific user will be secured with an OAuth2 bearer token, that contains an OAuth2 `access_token`. The access token will provide the mechanism to identify the user, and the claims that the user has to the entire system. This token must be validated and the contained claims authorized for all access.

## Account Provisioning

All users on the Hourfleet platform will have a registered account, and that account will be secured with a username and password.

User accounts, and passwords will be stored in the data store of each tenancy on the platform.

Authentication of a user account will be performed by the Hourfleet platform using any of the [OAuth2 authorizations flows](https://oauth.net/2/grant-types/) (i.e. Authorization Code Flow, Resource Owner Password Credentials Flow, etc.).

## Account Access Termination

Upon written request from an end-user, a users account will terminated. The users account will be permanently disabled, and any profile information stored for that user will be erased (or replaced with non-personally identifiable values). The user account will remain permanently retained as long as the tenant remains on the platform.

## Password Policy

All passwords will meet the following policy:

* Must be no less than 8 characters in length, and no more than 160 characters in length.
* Can contain: any number, any letter, spaces and any of the following common characters:``~!@#$%:&*()-+={}[]|:;'"<,>.?/`
* Upon reset of a password, the new password cannot be teh same as the previous password.

## Password Reset Policy

As the Hourfleet platform gathers and stores many forms of personally identifiable information, (See [Personally Identifiable Information](#Personally-Identifiable-Information)) it must take appropriate steps to protect that data for all users.

>  Note: Often times, attackers target the 'password reset' back door as an easier way to gain access to users account, because often, the 'back door' is easier to get through than the 'front door'.

The password reset process for Hourfleet must be more rigorous and *adaptive* depending on what PII data is actually stored for any specific users account.

> For example: If all the Hourfleet platform stores for a user is their *email address*, then verifying that the user owns that email address is a reasonable precondition for authenticating that they own the Hourfleet account for which they are attempting to reset the password for. However, if the platform stores more sensitive PII data stored for the user, then just authenticating the user based upon their email address is not sufficient protection.

At a minimum, for user accounts that only have *email address* captured (the minimum PII data needed to create an account on the Hourfleet platform) the password reset process must challenge that the user is the owner of the email address. This will be done by sending a password reset link in an email to that address.

For user accounts that hold more PII data, the password reset process must go much further to challenge the user to verify a subset of their stored PII data, in order to reset their password. This question-answer process will also start with an email challenge as the first step in the process. Following that, the user will be asked to provide confirmation of existing PII they already have provided the platform, until the user has provided sufficient evidence that they own the account.

The password reset process will time-bombed from the moment it starts to completion. The password reset process must complete within a reasonable period of time once initiated. No less than 15mins, no more than 60mins.

A user must have no more than **4** failed attempts to answer all challenges, after which their account will become permanently locked out.

## Account Lockout Policy

All Hourfleet user accounts can become permanently or temporarily locked out. During that time, the user will not gain any access to the platform.

The user's account will become permanently locked out if either the network operator manually locks them out or if they initiate and fail to reset their password successfully.

A users account will become temporarily locked out for **5** mins if they fail to authenticate with their credentials (username/password) more than **5** times.

# Disaster Recovery

Hourfleet is built upon the Azure Cloud platform, and its main system components are built upon commonly available services provided by Azure.

The following Azure components will each have their own DR processes:

* Tenant Storage Accounts:
  * Replication: All tenant storage accounts will be replicated across two regions using [GRS replication](https://docs.microsoft.com/en-nz/azure/storage/common/storage-redundancy-grs) 
* Azure Key Vault:
  * Replication: All tenant secrets will be replicated across two regions using [Azure Key Vault replication](https://docs.microsoft.com/en-us/azure/key-vault/key-vault-disaster-recovery-guidance)
* Redis Cache:
  * There is no requirement for the caches to be replicated for high availability. If the cache is unavailable a degradation in performance is experienced during the outage, but the platform must continue to operate. The cache will be rebuilt automatically and performance will be restored when the cache is brought back up.

# Incident Response

The current and historical availability of the Hourfleet platform is displayed at: https://status.hourfleet.com, where subscribers can opt in to watch a change in status.

When an outage is detected, the status of the platform and its various sub systems will be updated to reflect the incident.

The incident will be updated as soon as the status changes, and at least once after 60mins, then at least once every full day the incident is still active.

After the incident is closed, within a reasonable timeframe a post mortem will e performed and communicated on the incident at: https://status.hourfleet.com

# References

[Terms of Service](https://www.wix.hourfleet.com/terms)

[Privacy Policy](https://www.wix.hourfleet.com/privacy)

Service Level Agreements
